# DiboaNews — estudo de infraestrutura web

Projeto de aprendizado inspirado no TabNews, com Next.js e PostgreSQL. A versão atual concentra-se na infraestrutura da API, migrações e testes de integração; ainda não é uma plataforma de publicação de notícias completa.

## Implementado

- `GET /api/v1/status`: estado da aplicação e informações de conexão do PostgreSQL.
- `GET /api/v1/migrations`: consulta de migrações pendentes.
- `POST /api/v1/migrations`: execução de migrações.
- Cliente de banco em `infra/database.js`, PostgreSQL via Docker Compose e testes Jest para os endpoints.

## Executar

Use a versão Node.js indicada em `.nvmrc`, npm e Docker Compose. A partir da raiz:

```sh
npm ci
npm run dev
```

O script sobe os serviços de `infra/compose.yaml` e inicia o Next.js em http://localhost:3000. Revise as variáveis `POSTGRES_*` no arquivo local `.env.development`, usando somente um banco de desenvolvimento.

Para aplicar migrações pelo terminal, use `npm run migration:up`. Com aplicação e banco disponíveis, execute `npm test`. `npm run lint:check` verifica a formatação.

## Limitações

Os endpoints de migração não implementam autenticação nesta versão. Não exponha o mecanismo de alteração do banco em uma demonstração pública sem restringi-lo. Não há fluxo de cadastro, feed ou comentários implementado. Não houve execução da aplicação ou da suíte nesta revisão documental.
