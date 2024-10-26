Aqui está a tradução para o README.md do projeto **Shop Golang Microservices**.

---

[![CI](https://github.com/meysamhadeli/shop-golang-microservices/actions/workflows/ci.yml/badge.svg?branch=main&style=flat-square)](https://github.com/meysamhadeli/shop-golang-microservices/actions/workflows/ci.yml)
![Versão do Go](https://img.shields.io/badge/go%20version-%3E=1.21-61CFDD.svg?style=flat-square)
# 📍 Shop Golang Microservices

> **Um microserviço prático e fictício para implementar uma infraestrutura para execução de sistemas distribuídos com as mais recentes tecnologias e arquiteturas, como Arquitetura de Slice Vertical, Arquitetura Orientada a Eventos, CQRS, Postgres, RabbitMq em Golang.** 🚀

> 💡 **Este projeto não é orientado a negócios e o foco principal foi na parte técnica para implementar um sistema distribuído com um projeto de exemplo. Nele, implementei alguns conceitos em microserviços, como Mensageria, Rastreamento, Arquitetura Orientada a Eventos, Arquitetura de Slice Vertical e CQRS.**

<a href="https://gitpod.io/#https://github.com/meysamhadeli/shop-golang-microservices"><img alt="Abrir no Gitpod" src="https://gitpod.io/button/open-in-gitpod.svg"/></a>

# Índice

- [Objetivos do Projeto](#objetivos-do-projeto)
- [Plano](#plano)
- [Tecnologias - Bibliotecas](#tecnologias---bibliotecas)
- [Domínio e Contexto Delimitado - Limites de Serviço](#domínio-e-contexto-delimitado---limites-de-serviço)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Como Executar](#como-executar)
    - [Docker-Compose](#docker-compose)
    - [Compilação](#compilação)
    - [Execução](#execução)
    - [Teste](#teste)
- [APIs de Documentação](#apis-de-documentação)
- [Suporte](#suporte)
- [Contribuição](#contribuição)

## Objetivos do Projeto

- :sparkle: Uso da `Arquitetura de Slice Vertical` para `nível de arquitetura`.
- :sparkle: Uso do `Rabbitmq` para `Arquitetura Orientada a Eventos` entre os microserviços com a biblioteca `streadway/amqp`.
- :sparkle: Uso de `gRPC` para `comunicação interna` entre microserviços com a biblioteca `grpc/grpc-go`.
- :sparkle: Uso de `CQRS` com a biblioteca `mehdihadeli/Go-MediatR`.
- :sparkle: Uso de `Postgres` como `banco de dados` dos microserviços com a biblioteca `go-gorm/gorm`.
- :sparkle: Uso de `go-playground/validator` para `validação de dados` nas chamadas REST.
- :sparkle: Uso de `OpenTelemetry` para `rastreamento distribuído` com base no `Jaeger`.
- :sparkle: Uso de `OAuth2` para implementar `autenticação` e `autorização` com a biblioteca `go-oauth2/oauth2`.
- :sparkle: Uso do `framework Echo` para API RESTFul.
- :sparkle: Uso de `Swagger` com a biblioteca `swaggo/swag` para documentação da API.
- :sparkle: Uso da biblioteca `uber-go/fx` para `injeção de dependência`.
- :sparkle: Uso de `Viper` para `gerenciamento de configuração`.
- :sparkle: Uso de `logrus` como `logger estruturado`.
- :sparkle: Uso de `Testes Unitários`, `Testes de Integração` e `Testes de Ponta a Ponta`.
- :sparkle: Uso de `Docker-Compose` como mecanismo de `deploy`.
- :construction: Uso de `OpenTelemetry` para `monitoramento` com base em `Prometheus` e `Grafana`.
- :construction: Uso de `MongoDB` para o lado de leitura com o `mongo-driver`.
- :construction: Uso de `Domain Driven Design` (DDD) para implementar todos os processos de `negócio` em microserviços.
- :construction: Uso de `Padrão Inbox` para garantir idempotência de mensagens no receptor e `Entrega Exata uma Vez`.
- :construction: Uso de `Padrão Outbox` para garantir que nenhuma mensagem seja perdida e que haja `Entrega pelo Menos Uma Vez`.

## Plano

> 🌀 Este projeto está em andamento e novas funcionalidades serão adicionadas com o tempo. 🌀

Vou tentar registrar objetivos futuros e novas adições na seção [Issues](https://github.com/meysamhadeli/shop-golang-microservices/issues) deste repositório.

## Tecnologias - Bibliotecas

- ✔️ **[`labstack/echo`](https://github.com/labstack/echo)** - Framework web de alto desempenho e minimalista em Go.
- ✔️ **[`go-gorm/gorm`](https://github.com/go-gorm/gorm)** - Biblioteca ORM para Go.
- ✔️ **[`sirupsen/logrus`](https://github.com/sirupsen/logrus)** - Logrus é um logger estruturado para Go.
- ✔️ **[`streadway/amqp`](https://github.com/streadway/amqp)** - Cliente RabbitMQ para Go.
- ✔️ **[`spf13/viper`](https://github.com/spf13/viper)** - Biblioteca de configuração para Go.
- ✔️ **[`swaggo/echo-swagger`](https://github.com/swaggo/echo-swagger)** - Middleware para gerar documentação da API RESTful automaticamente.
- ✔️ **[`mehdihadeli/Go-MediatR`](https://github.com/mehdihadeli/Go-MediatR)** - Implementação do Padrão Mediador em Go.
- ✔️ **[`go-playground/validator`](https://github.com/go-playground/validator)** - Implementa validação de campos e structs em Go.
- ✔️ **[`open-telemetry/opentelemetry-go`](https://github.com/open-telemetry/opentelemetry-go)** - Implementação do OpenTelemetry para rastreamento distribuído.
- ✔️ **[`meysamhadeli/problem-details`](https://github.com/meysamhadeli/problem-details)** - Manipulador de erros para mapeamento padronizado de erro.
- ✔️ **[`go-resty/resty`](https://github.com/go-resty/resty)** - Biblioteca HTTP e cliente REST para Go.
- ✔️ **[`grpc/grpc-go`](https://github.com/grpc/grpc-go)** - Implementação do gRPC em Go.
- ✔️ **[`go-oauth2/oauth2`](https://github.com/go-oauth2/oauth2)** - Protocolo aberto para autorização segura.
- ✔️ **[`stretchr/testify`](https://github.com/stretchr/testify)** - Ferramenta com assertivas e mocks que funciona bem com a biblioteca padrão.
- ✔️ **[`uber-go/fx`](https://github.com/uber-go/fx)** - Sistema de injeção de dependência para Go.
- ✔️ **[`cenkalti/backoff`](https://github.com/cenkalti/backoff)** - Porta Go do algoritmo de backoff exponencial.
- ✔️ **[`testcontainers/testcontainers-go`](https://github.com/testcontainers/testcontainers-go)** - Biblioteca para criação e limpeza de contêineres em testes automatizados.
- ✔️ **[`avast/retry-go`](https://github.com/avast/retry-go)** - Biblioteca de mecanismo de retry em Go.
- ✔️ **[`ahmetb/go-linq`](https://github.com/ahmetb/go-linq)** - Capacidade de LINQ em Go.

## Domínio e Contexto Delimitado - Limites de Serviço

![](./assets/shop-golang-microservices.png)

## Estrutura do Projeto

Neste projeto, usei [Arquitetura de Slice Vertical](https://jimmybogard.com/vertical-slice-architecture/) e [estrutura de pastas de funcionalidade](http://www.kamilgrzybek.com/design/feature-folders/) para organizar os arquivos.

Utilizei o [RabbitMQ](https://github.com/rabbitmq) como MessageBroker para comunicação assíncrona entre microserviços com o mecanismo de consistência eventual.

Cada solicitação é tratada como um caso de uso ou slice distinto, encapsulando e agrupando todas as preocupações de front-end até o back.

![](./assets/vertical-slice-architecture.png)

Para comunicação entre endpoints e handlers, uso o [Go-MediatR](https://github.com/mehdihadeli/Go-MediatR) para desacoplar diretamente, criando endpoints finos e limpos. A separação do código em slices verticais ajuda a minimizar o acoplamento entre slices e maximizar dentro de cada slice.

Utilizei CQRS para decompor as funcionalidades, deixando o código mais escalável e fácil de manter, facilitando a adição de novas funcionalidades.

## Como Executar

> ### Docker-Compose

Para executar a `infraestrutura` com `docker`, utilize o arquivo [infrastructure.yaml](./deployments/docker-compose/infrastructure.yaml) no diretório raiz do app:

```bash
docker-compose -f ./deployments/docker-compose/infrastructure.yaml up -d


```

> ### Compilação

```bash
make build
```

> ### Execução

```bash
make run
```

> ### Teste

```bash
make test
```

## APIs de Documentação

> #### Swagger UI
Após iniciar a aplicação, você pode acessar o Swagger UI em [http://localhost:8080/swagger/index.html](http://localhost:8080/swagger/index.html).

## Suporte

- Repositório: [https://github.com/meysamhadeli/shop-golang-microservices](https://github.com/meysamhadeli/shop-golang-microservices)
- Email: [meysam.hadeli@gmail.com](mailto:meysam.hadeli@gmail.com)
  
## Contribuição

Contribuições são bem-vindas!
