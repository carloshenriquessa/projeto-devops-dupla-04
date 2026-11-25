# Projeto DevOps: dupla-04

**Site:** https://carloshenriquessa.github.io/projeto-devops-dupla-04/  
**Status:** https://carloshenriquessa.github.io/projeto-devops-dupla-04/status.html

**Imagem Docker:** `ghcr.io/carloshenriquessa/projeto-devops-dupla-04`

## O fluxo completo

O desenvolvedor realiza as alterações no projeto e envia os arquivos para o GitHub utilizando o comando `git push`.

O GitHub Actions executa automaticamente os testes configurados no projeto.

Se os testes forem aprovados, o fluxo continua com a construção da imagem Docker.

A imagem recebe uma versão e é publicada no GitHub Container Registry (GHCR).

Depois, podemos baixar essa imagem e executar a aplicação em um contêiner Docker.

## Linha do tempo

- **v1:** primeira versão da API publicada e funcionando.
- **v2:** alteração da porta da aplicação para 5005, causando problema no acesso pela porta esperada.
- **v3:** correção realizada utilizando `git revert`, restaurando a configuração anterior e publicando uma nova versão.

## O que os testes não pegaram

Os testes automatizados não identificaram que a aplicação estava utilizando uma porta diferente da esperada. Por isso, a versão v2 passou pelo fluxo de testes, mas apresentou problema quando executada. Para evitar esse tipo de situação, seria importante testar também a aplicação em execução, iniciando o contêiner e acessando a rota `/saude` pela porta configurada.

## Quem fez o quê

### Aluno A — Carlos Henrique Souza Sá

Como Aluno A, participei das etapas de versionamento, publicação e testes da aplicação. Acompanhei a execução do GitHub Actions e testei as imagens Docker. Durante a atividade, identificamos o problema causado pela alteração da porta na versão v2. Para corrigir, utilizamos o comando `git revert`, publicamos a versão v3 e verificamos se a API estava funcionando corretamente. Com essa atividade, aprendi melhor como funciona o processo de integração contínua, publicação de imagens Docker e reversão de alterações utilizando o Git.

### Aluno B — Kauan da Silva Saturnino

Como Aluno B, participei dos testes das versões da aplicação utilizando Docker. Durante a atividade, executei a versão v2, verifiquei o problema de acesso causado pela mudança da porta e consultei os logs do contêiner para identificar o erro. Também participei do rollback operacional, executando a versão v1 para confirmar que o serviço voltava a funcionar. Com essa experiência, aprendi a importância de testar a aplicação em execução, analisar logs e utilizar versões anteriores para recuperar um serviço com problemas.