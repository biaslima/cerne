# Cerne — Contexto para conversas com IA

> Cole este arquivo no início de cada conversa. Fonte de verdade completa: `docs/documento-de-abertura.md`. Se algo aqui contradiz o documento, vale o documento (e este arquivo deve ser corrigido).

## Estado atual

**Fase atual: Fase 0 (Fundação).**
Issue em andamento: _[#número e título]_

## Visão

Cerne é um caderno digital de estudos que nasce da captura ativa de aula: o aluno anota com as próprias palavras (pista + explicação), trabalha em blocos de foco cronometrados e "estaciona" pensamentos que o distraem. Depois, a IA (opcional) pode organizar as anotações em páginas de um caderno em Markdown, mantido pelo aluno.

Fluxo central: `capturar → organizar (IA, opcional) → guardar e revisar → exportar (.md)`

- Web app **desktop-first**, local-first e sem conta no MVP (Fases 0 a 5).
- Contas/sincronização (Fase 6) e app de desktop (Fase 7) são futuro: não implementar agora.
- É também peça de portfólio: o autor precisa entender e conseguir explicar todo o código.

## Stack

- Vue 3 (Composition API, `<script setup>`), TypeScript, Vite
- Pinia (estado), Vue Router (rotas)
- Markdown: `markdown-it` (ou `marked`) + DOMPurify
- Testes: Vitest + Vue Test Utils; Playwright para fluxos principais
- Qualidade: ESLint, Prettier, Conventional Commits
- CI/CD: GitHub Actions; deploy estático
- IA: função serverless própria (guarda a chave), atrás da interface `NoteOrganizer`

> Versões de bibliotecas e comandos: conferir na documentação oficial antes de usar.

## Camadas

```
src/
  domain/       regras puras (timer, geração de página, tipos)
  storage/      interface Repository + implementações
  ai/           interface NoteOrganizer + provedor(es)
  stores/       stores Pinia (ligam domínio, storage e interface)
  composables/  lógica reativa reutilizável (ex.: useTimer)
  components/   componentes de interface
  views/        telas, uma por rota
  router/       definição de rotas
```

- `domain/` não depende de Vue, DOM, armazenamento nem IA.
- `useTimer` é só uma casca reativa sobre a máquina de estados do domínio.
- Todo acesso a dados passa por `Repository`. Nunca `localStorage`/IndexedDB direto em componentes.

## Regras inegociáveis

1. Notas originais do aluno nunca são sobrescritas pela IA. Páginas geradas são documentos separados, com referência às notas de origem (`sourceNoteIds`).
2. Todo Markdown renderizado é sanitizado com DOMPurify. Nunca `v-html` com conteúdo não sanitizado.
3. O app continua útil sem IA e sem conexão (exceto a geração por IA).
4. Lógica de domínio é testável sem DOM. O timer usa timestamp de término (`endsAt`), não contagem de ticks.
5. Acessibilidade desde o início: teclado, contraste AA, `aria-live` no timer, `prefers-reduced-motion`.
6. Textos da interface em pt-BR, isolados do código para permitir tradução futura.
7. Nenhuma chave de API no front-end, nunca.

## Modelo de dados (resumo)

Toda entidade persistida tem: `id` (UUID gerado no cliente), `createdAt`, `updatedAt` (ISO 8601) e `deletedAt?` (exclusão lógica). Isso prepara a sincronização futura (RNF09).

Entidades: `Subject`, `Session` (a "aula"), `Note` (pista + explicação), `ParkedThought`, `FocusBlock`, `Notebook`, `Page`, `Settings`.
Detalhes completos na seção 9 do documento de abertura.

## Regras de negócio-chave

- Só pode existir uma `Session` com status `active`.
- Pular ou reiniciar um foco não conta como ciclo concluído.
- Anotação totalmente vazia não é criada.
- Excluir é lógico (`deletedAt`); remoção definitiva é ação separada e explícita.
- Excluir matéria não exclui aulas.
- A IA organiza e estrutura o conteúdo do aluno; dúvidas continuam como dúvidas; o que não está nas notas é sinalizado como sugestão.

## Decisões em aberto (não assumir)

- D3: persistência (recomendação: `Repository`, começar com `localStorage`, migrar para IndexedDB até a Fase 2)
- D5: regenerar página (versionar × substituir)
- D8: proteção do endpoint de IA
- D12: purga de itens excluídos logicamente
- D9 a D11: contas, conflitos de sync e app de desktop (Fases 6 e 7)

## Como trabalhar (regras de desenvolvimento assistido)

- Passos pequenos: uma tarefa, módulo ou arquivo por vez.
- Explicar o porquê e citar alternativas com trade-offs.
- Testes junto com o código, principalmente no domínio.
- Pedir confirmação antes de nova dependência, mudança de estrutura ou do modelo de dados.
- Não aumentar o escopo: ideias fora da fase atual viram ideia futura registrada.
- Núcleo de aprendizado escrito à mão (ex.: máquina de estados do timer): a IA guia com perguntas, esqueleto e revisão, salvo pedido explícito da solução.
- O autor só fecha uma issue se conseguir explicar o código sem a conversa aberta.

## Convenções

- Commits: Conventional Commits (`feat:`, `fix:`, `docs:`, `test:`, `chore:`, `refactor:`), pequenos, com mensagens do próprio autor.
- Idioma: documentação e interface em pt-BR; identificadores de código em inglês **[A CONFIRMAR]**.
- Datas em ISO 8601; ids sempre UUID.
- Lint e testes passando antes de cada commit.

## Fora do escopo do MVP

Contas e sincronização, app de desktop, colaboração, app móvel nativo, gravação/transcrição de áudio.
