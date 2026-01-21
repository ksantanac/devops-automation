
# Post-Mortem: Erro `ImagePullBackOff` no `java-api-deployment`

- **Data:** 21 de Janeiro de 2026
- **Status:** Resolvido
- **Autores:** Gemini

## Resumo

No dia 21 de Janeiro de 2026, um pod do deployment `java-api-deployment` entrou em estado `ImagePullBackOff`. A investigação revelou que a causa raiz era um erro de digitação no nome da imagem do contêiner especificada no arquivo de deployment. O problema foi rapidamente resolvido corrigindo o nome da imagem e aplicando a atualização no deployment.

## Impacto

Um dos pods do `java-api-deployment` não estava funcional, o que poderia ter levado a uma redução na capacidade de resposta da aplicação, embora, neste caso, os outros pods tenham conseguido lidar com a carga. Nenhum impacto direto ao usuário final foi observado.

## Causa Raiz

A análise do pod com falha, utilizando o comando `kubectl describe pod`, revelou que o Kubernetes não conseguiu baixar a imagem `iesodias/jav-api:latest`. A mensagem de erro "repository does not exist or may require authorization" indicou que o nome ou a tag da imagem estavam incorretos.

A causa raiz foi identificada como um erro de digitação no nome da imagem: `jav-api` em vez de `java-api`.

## Resolução

A correção foi aplicada diretamente no cluster Kubernetes, sem a necessidade de editar o arquivo de manifesto. O comando `kubectl set image` foi utilizado para atualizar o deployment com o nome correto da imagem.

```bash
kubectl set image deployment/java-api-deployment java-api=iesodias/java-api:latest
```

Após a execução do comando, o Kubernetes iniciou um novo pod com a imagem correta, e o pod com falha foi terminado. O status do deployment voltou ao normal, com todos os pods em estado de `Running`.

## Linha do Tempo

- **13:32 (horário local):** O usuário relata um problema de `ImagePullBackOff` em um dos pods do `java-api-deployment`.
- **13:33:** Início da investigação. O pod com falha (`java-api-deployment-89948b764-w66rm`) é identificado.
- **13:34:** A análise do pod revela um erro de digitação no nome da imagem (`iesodias/jav-api:latest`).
- **13:35:** A correção é aplicada utilizando `kubectl set image`.
- **13:36:** O status do deployment é verificado, e todos os pods são confirmados como `Running`.

## Lições Aprendidas

1.  **Validação de Nomes de Imagens:** A importância de validar nomes e tags de imagens de contêineres antes de aplicar as configurações no cluster.
2.  **Diagnóstico Rápido:** A eficácia do comando `kubectl describe pod` para diagnosticar rapidamente a causa raiz de falhas em pods.
3.  **Correções Diretas:** A utilidade de comandos como `kubectl set image` para aplicar correções rápidas em deployments sem a necessidade de modificar os arquivos de manifesto.

## Itens de Ação

- **[ ] Implementar Validação de Pré-deployment:** Adicionar um passo de validação nos pipelines de CI/CD para verificar a existência de imagens de contêineres no registro antes de aplicar as configurações no cluster.
- **[ ] Revisar Processo de Atualização:** Revisar e documentar o processo de atualização de imagens de deployments para incluir uma etapa de verificação do nome da imagem.
