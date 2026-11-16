# Alexandria

[![CI](https://github.com/LauanMO/Alexandria/actions/workflows/ci.yml/badge.svg)](https://github.com/LauanMO/Alexandria/actions/workflows/ci.yml)

App mobile de biblioteca pessoal: busca de livros na Open Library, status de leitura,
avaliações, comentários e perfil com foto, com recuperação de senha por código enviado
por e-mail.

Projeto de TCC em equipe na UNIFOR. Este é o meu fork do repositório do time,
[Dragoneto/Alexandria](https://github.com/Dragoneto/Alexandria), com uma CI de testes a mais.

## Stack

| Parte | Tecnologias |
| --- | --- |
| `mobile/` | React Native (Expo), Expo Router, TypeScript |
| `backend/` | Node.js, Express, PostgreSQL, JWT, bcrypt, Nodemailer |
| Deploy | API no Railway |

## Rodando localmente

API, dentro de `backend/`:

```sh
npm ci
cp .env.example .env   # troque o JWT_SECRET; DB_MODE=local salva em arquivo, sem PostgreSQL
npm run dev
```

A API sobe em `http://localhost:3000`.

App, dentro de `mobile/`:

```sh
npm ci
npm start
```

O `npm start` aponta para a API local. Emulador, celular físico e o backend no Railway
estão explicados em [mobile/README.md](mobile/README.md).

## Testes

```sh
cd backend && npm test
cd mobile && npm run typecheck && npm test
```

A CI deste fork roda esses comandos, o lint do app e um teste de fumaça da API a cada
push e pull request na `main` e na `dev`.

## Minha parte

Sou o líder do back-end. Fiz a recuperação de senha com código de 6 dígitos (da API às
telas do app) e o envio do código pelo Gmail, as rotas de leitura das avaliações, a
camada de dados dos comentários, o tratamento das falhas da busca na Open Library e o
workflow do GitHub Actions que faz o merge automático das PRs aprovadas no Git Flow.
