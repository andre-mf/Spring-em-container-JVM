# Projeto Spring Java em ambiente de desenvolvimento executado em um container JVM

### ☕ Configuração para execução de um projeto Java em máquinas que não possuem uma JVM instalada, utilizando docker-compose para carregamento.

```yml
version: '3.3'

services:

  spring:
    image: openjdk:17-alpine
    volumes:
      - '${PWD}:/app'
      - '~/.m2:/root/.m2'
    working_dir: /app
    expose:
      - 8080
    ports:
      - 8080:8080
    command: ./mvnw spring-boot:run
```