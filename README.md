# Shop Golang Microservices

Um microserviço prático e fictício para implementar uma infraestrutura para execução de sistemas distribuídos.

Este projeto não é orientado a negócios e o foco principal foi na parte técnica para implementar um sistema distribuído com um projeto de exemplo.

## Objetivos do Projeto

- Implementação de uma arquitetura de microserviços.
- Implementação de automação devops com Amazon EKS.
- Implementação de observabilidade com Elastic Search.

## Diagrama de Arquitetura da Solução

![](./assets/shop-golang-microservices.png)

### Docker-Compose
```bash
docker-compose -f ./deployments/docker-compose/infrastructure.yaml up -d
```
## APIs de Documentação

#### Swagger UI

Após iniciar a aplicação, você pode acessar o Swagger UI em [http://localhost:8080/swagger/index.html](http://localhost:8080/swagger/index.html).

