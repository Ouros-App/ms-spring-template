# ms-spring-template

<!-- REPO-METADATA:START -->
<div align="center">

[![Repo Size](https://img.shields.io/github/repo-size/Ouros-App/ms-spring-template?style=flat-square&label=REPO%20SIZE)](https://github.com/Ouros-App/ms-spring-template)
[![Languages](https://img.shields.io/github/languages/count/Ouros-App/ms-spring-template?style=flat-square&label=LANGUAGES)](https://github.com/Ouros-App/ms-spring-template/languages)
[![Forks](https://img.shields.io/github/forks/Ouros-App/ms-spring-template?style=flat-square&label=FORKS)](https://github.com/Ouros-App/ms-spring-template/network/members)
[![Issues](https://img.shields.io/github/issues/Ouros-App/ms-spring-template?style=flat-square&label=ISSUES)](https://github.com/Ouros-App/ms-spring-template/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/Ouros-App/ms-spring-template?style=flat-square&label=PULL%20REQUESTS)](https://github.com/Ouros-App/ms-spring-template/pulls)

</div>
<!-- REPO-METADATA:END -->

Template de uma API REST com Spring Boot e Gradle.

## Status e escopo

A aplicação atual é um esqueleto funcional com:

- `GET /`, que retorna a mensagem `Spring REST API com Gradle pronta para evoluir.`.
- `GET /health`, que retorna `{"status":"ok"}`.
- teste de contexto Spring em `SpringTemplateApplicationTests`.
- execução configurada para a porta `8000` por padrão.

## Principais componentes

- `SpringTemplateApplication.java`: ponto de entrada da aplicação.
- `controller/HomeController.java`: rota raiz.
- `controller/HealthController.java`: health check.
- `src/main/resources/application.properties`: nome da aplicação e porta.
- Gradle Wrapper: `gradlew` e `gradlew.bat`.
- `Dockerfile` e `docker-compose.yml`: execução em container.

## Pré-requisitos

Para execução local, o projeto usa Java 21 e o Gradle Wrapper. O build também declara:

- Spring Boot `3.4.0`;
- plugin de gerenciamento de dependências `1.1.6`;
- plugin JaCoCo;
- plugin SonarQube `6.2.0.5505`;
- Gradle Wrapper `8.14.4`.

## Configuração

O arquivo `.env.example` contém:

```dotenv
SERVER_PORT=8000
```

Para os fluxos Docker, crie `.env`:

```bash
cp .env.example .env
```

A propriedade `server.port` usa `SERVER_PORT`, com fallback para `8000`.

## Instalação e execução

Com o wrapper incluído no repositório:

```bash
./gradlew bootRun
```

No Windows:

```powershell
.\\gradlew.bat bootRun
```

A aplicação fica em `http://localhost:8000`. As rotas disponíveis são:

- `GET http://localhost:8000/`
- `GET http://localhost:8000/health`

## Testes e build

Execute o teste de contexto e o build:

```bash
./gradlew test
./gradlew build
```

A tarefa de teste usa JUnit Platform e gera o relatório JaCoCo configurado no `build.gradle`.

## Docker

O Compose publica `localhost:8080` para a porta `8000` do container:

```bash
cp .env.example .env
docker compose up --build
```

O `Dockerfile` usa uma etapa de build com Gradle 8.14.4/JDK 21 e uma imagem final JRE 21.

## Estrutura do projeto

```text
.
├── src/
│   ├── main/
│   │   ├── java/com/ourosapp/springtemplate/
│   │   │   ├── SpringTemplateApplication.java
│   │   │   └── controller/
│   │   │       ├── HealthController.java
│   │   │       └── HomeController.java
│   │   └── resources/application.properties
│   └── test/java/com/ourosapp/springtemplate/
│       └── SpringTemplateApplicationTests.java
├── build.gradle
├── docker-compose.yml
├── gradlew
├── gradlew.bat
└── settings.gradle
```

## Contribuição

Faça alterações em uma branch própria e use os templates de pull request disponíveis em `.github/PULL_REQUEST_TEMPLATE`.

## Licença

Este projeto está sob a licença MIT. Consulte o arquivo [LICENSE](LICENSE).


## Principais contribuidores

<!-- CONTRIBUTORS:START -->
- [@Nicolas25vlad](https://github.com/Nicolas25vlad) — 12 contribuições
<!-- CONTRIBUTORS:END -->

> Atualizado automaticamente semanalmente pelo workflow de metadados do README.
