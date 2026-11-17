# Cerne

> Anote com suas próprias palavras. Organize sem perder a autoria. Estude no seu caderno.

<!-- Badge de CI: ativar quando o workflow existir (Fase 0). Conferir o nome do arquivo do workflow.
[![CI](https://github.com/biaslima/cerne/actions/workflows/ci.yml/badge.svg)](https://github.com/biaslima/cerne/actions/workflows/ci.yml)
-->

O **Cerne** é um caderno digital de estudos que nasce da captura ativa de aula. Durante a aula, você anota com as próprias palavras (pista + explicação), trabalha em blocos de foco cronometrados e "estaciona" pensamentos que o distraem. Depois, as anotações podem ser organizadas por IA em páginas de um caderno que é seu, exportáveis em Markdown.

```
capturar (aula)  →  organizar (IA, opcional)  →  guardar e revisar (caderno)  →  exportar (.md)
```

## Princípios

- **Autoria do aluno em primeiro lugar:** a IA organiza, nunca sobrescreve suas notas.
- **Funciona sem IA e sem conta:** os dados ficam no seu dispositivo (local-first).
- **Formato aberto:** Markdown para páginas e exportação.

## Status

🚧 **Em desenvolvimento: Fase 0 (Fundação).** Ainda não há versão utilizável.

O projeto parte de um protótipo em HTML único e está sendo reconstruído como um projeto estruturado. O roadmap completo, o escopo e as decisões estão em [`docs/documento-de-abertura.md`](docs/documento-de-abertura.md).

## Stack

- Vue 3 (Composition API) + TypeScript + Vite
- Pinia e Vue Router
- Vitest e Vue Test Utils (unitários e componentes); Playwright (fluxos principais)
- ESLint, Prettier e Conventional Commits
- GitHub Actions para CI/CD

## Como rodar

Requisitos: Node.js 22.18 e npm.

```bash
npm install
npm run dev     # servidor de desenvolvimento (http://localhost:5173)
npm run build   # build de produção
```

## Desenvolvimento assistido por IA

Este projeto é desenvolvido com apoio de IA em chats, sob supervisão e responsabilidade do autor. A IA ajuda a propor código, revisar e explicar alternativas; nada entra no repositório sem que o autor entenda e consiga explicar. O contexto usado nessas conversas está em [`docs/CONTEXTO-IA.md`](docs/CONTEXTO-IA.md).

## Documentação

- [Documento de abertura](docs/documento-de-abertura.md): visão, escopo, requisitos, arquitetura, roadmap e riscos
- [Contexto para IA](docs/CONTEXTO-IA.md): resumo usado no início de cada conversa

## Licença

[AGPL v3](LICENSE)
