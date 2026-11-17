# Cerne — Documento de Abertura do Projeto

| | |
|---|---|
| **Projeto** | Cerne |
| **Versão do documento** | 0.2 (rascunho) |
| **Data** | 16/11/2026 |
| **Responsável** | _[seu nome]_ |
| **Status** | Em definição |
| **Licença** | AGPL v3 (ver D6) |
| **Repositório** | _[link a definir]_ |

> Este documento marca o início formal do projeto. Itens marcados com **[A CONFIRMAR]** são suposições ou decisões ainda abertas e devem ser revistos antes da Fase 1.

---

## 1. Resumo

O **Cerne** é um caderno digital de estudos que nasce da captura ativa de aula. O aluno anota durante a aula com as próprias palavras (pista + explicação), trabalha em blocos de foco cronometrados e "estaciona" pensamentos que o distraem. Ao final, as anotações podem ser organizadas por IA em páginas de um **caderno iniciado e mantido pelo aluno**, exportáveis em Markdown.

O produto é um **web app pensado primeiro para telas de desktop**. A visão de longo prazo é oferecer o mesmo produto como aplicativo de desktop e como versão online, com conta e sincronização para acessar o histórico em outros computadores, no estilo do que o Notion faz. O MVP (Fases 0 a 5) continua local-first e sem conta.

O projeto parte de um protótipo funcional em arquivo HTML único, criado pelo autor para uso próprio, e será reconstruído como um projeto de software estruturado, que também servirá como peça de portfólio.

**Fluxo central do produto:**

```
capturar (aula)  →  organizar (IA, opcional)  →  guardar e revisar (caderno)  →  exportar (.md)
```

## 2. Contexto e problema

**Contexto.** Em aula, é comum copiar o que o professor diz ou o que está no slide sem processar o conteúdo, e perder o foco por pensamentos soltos. Ferramentas existentes tendem a ser ou cronômetros (sem conteúdo) ou editores de notas genéricos (sem estrutura de estudo).

**Problemas que o Cerne quer atacar:**

1. **Cópia passiva.** Anotar sem compreender.
2. **Dispersão.** Pensamentos alheios à aula interrompem a atenção.
3. **Atrito pós-aula.** Anotações brutas ficam soltas; organizá-las exige copiar para outra ferramenta, e o resultado se perde fora do app.

## 3. Visão e proposta de valor

> Anote com suas próprias palavras. Organize sem perder a autoria. Estude no seu caderno.

**Diferenciais:**

- Método de anotação ativa (pista + explicação própria) com perguntas de reflexão.
- Blocos de foco integrados ao ato de anotar.
- Caderno que preserva a autoria: a IA organiza, não substitui.
- Funciona sem IA e sem conta; dados sob controle do usuário.
- A longo prazo: o mesmo caderno em qualquer computador, por meio de conta e sincronização **opcionais**.

## 4. Objetivos

### 4.1 Objetivos do produto

- **O1.** Oferecer captura de aula com timer de foco, anotações e "estacionamento" de pensamentos (paridade com o protótipo).
- **O2.** Oferecer um caderno de páginas em Markdown, criado e editado pelo aluno.
- **O3.** Permitir gerar páginas do caderno a partir das anotações de uma aula, com apoio de IA.
- **O4.** Permitir exportar páginas, cadernos e backup completo.
- **O5.** Funcionar offline e sem cadastro (MVP).
- **O6.** *(Longo prazo, Fase 6)* Permitir acessar o mesmo histórico em outros computadores por meio de conta e sincronização opcionais.
- **O7.** *(Longo prazo, Fase 7)* Oferecer o produto também como aplicativo de desktop, a partir da mesma base de código web.

### 4.2 Objetivos de aprendizado e portfólio

- **P1.** Praticar arquitetura de front-end organizada (separação entre domínio, persistência e interface).
- **P2.** Escrever regras de negócio testáveis sem DOM (timer, geração de páginas).
- **P3.** Integrar uma API de IA com tratamento de erro, privacidade e custo.
- **P4.** Publicar com CI/CD, documentação e histórico de commits que contem a evolução do projeto.
- **P5.** Construir com acessibilidade e responsividade desde o início.

## 5. Princípios de design

1. **Autoria do aluno em primeiro lugar.** Notas originais nunca são sobrescritas. Páginas geradas guardam referência às notas de origem.
2. **A IA é opcional e plugável.** O app é completo sem ela.
3. **Local-first.** Dados ficam no dispositivo por padrão. Conta e sincronização, quando existirem, são opcionais e nunca condição para usar o app.
4. **Simples e rápido.** Sem enfeite; baixa fricção para anotar em plena aula.
5. **Transparência com IA.** O usuário sabe o que é enviado, para onde, e o que é conteúdo gerado.
6. **Formato aberto.** Markdown como formato interno e de exportação; sem aprisionamento.
7. **Preparado para crescer.** Decisões de hoje (identificadores, datas, acesso a dados por interface) não podem impedir sincronização e empacotamento desktop no futuro.

## 6. Público-alvo

- **Primário:** estudantes de graduação, técnico e cursos livres que anotam durante aulas (presenciais ou remotas), usando principalmente computador.
- **Secundário:** autodidatas que estudam com videoaulas.

**Plataforma:** navegador moderno em desktop como prioridade. Uso em celular deve funcionar, mas é refinado depois do MVP de desktop.

**Persona de referência (o próprio autor):** estudante de tecnologia que perde o foco durante aulas e tem dificuldade em transformar anotações soltas em material de estudo.

## 7. Escopo

### 7.1 Dentro do escopo

| Prioridade | Itens |
|---|---|
| **Must** | Timer de foco/pausas; sessões de aula (uma ativa por vez); anotações (pista + explicação) com edição inline; estacionamento de pensamentos; resumo da aula; caderno com páginas em Markdown; exportação `.md`; tema claro/escuro; persistência local |
| **Should** | Geração de páginas por IA; matérias como entidade; busca; PWA offline; notificação de fim de bloco; timer resistente a recarga e a aba em segundo plano; backup/importação JSON |
| **Could** | Estatísticas de foco; tags; revisão espaçada das pistas; editor de Markdown mais rico; internacionalização |
| **Futuro (fora do MVP)** | Contas e sincronização (Fase 6); aplicativo de desktop (Fase 7) |

### 7.2 Fora do escopo do MVP (Fases 0 a 5)

- Contas de usuário e sincronização na nuvem (previstas para a Fase 6).
- Aplicativo de desktop empacotado (previsto para a Fase 7).
- Colaboração e compartilhamento entre alunos.
- Aplicativo móvel nativo.
- Gravação ou transcrição de áudio da aula.

## 8. Requisitos de alto nível

### 8.1 Funcionais

**Timer**
- RF01 Alternar entre foco, pausa curta e pausa longa, com durações configuráveis.
- RF02 Iniciar, pausar, reiniciar e pular bloco.
- RF03 Avançar automaticamente ou apenas avisar ao fim do bloco.
- RF04a O tempo restante é calculado pelo timestamp de término (`endsAt`), sem dessincronizar com a aba em segundo plano. *(Fase 1)* **[A CONFIRMAR: divisão do RF04]**
- RF04b O timer em andamento sobrevive a recarga da página. *(Fase 4)* **[A CONFIRMAR: divisão do RF04]**

**Captura**
- RF05 Criar, editar (inline) e excluir anotações com pista e explicação.
- RF06 Exibir pergunta de reflexão, com opção de trocar.
- RF07 Escrever resumo da aula ao final.
- RF08 Guardar pensamento avulso em um clique e revê-lo depois.

**Aulas**
- RF09 Criar, salvar automaticamente, reabrir e excluir aulas. Só pode haver uma aula ativa por vez.
- RF10 Associar aula a uma matéria.
- RF11 Buscar texto nas aulas e páginas.

**Caderno**
- RF12 Criar cadernos e páginas em Markdown, com edição e pré-visualização.
- RF13 Criar página manualmente ou a partir de uma aula.
- RF14 Gerar página a partir das anotações de uma aula usando IA, com opção de regenerar.
- RF15 Manter vínculo entre a página e as notas de origem, sem alterar as notas.

**Exportação e dados**
- RF16 Exportar página, caderno ou aula em `.md`.
- RF17 Exportar e importar todos os dados em JSON.

**Preferências**
- RF18 Tema, som, durações e configuração da IA.

**Futuro (requisitos preliminares, serão detalhados antes das Fases 6 e 7)**
- RF19 Criar conta, entrar e sair. *(Fase 6)*
- RF20 Sincronizar aulas, cadernos e páginas entre dispositivos, com resolução de conflitos. *(Fase 6)*
- RF21 Usar o app sem conta e vincular os dados locais a uma conta depois. *(Fase 6)*
- RF22 Instalar o Cerne como aplicativo de desktop com os mesmos dados e funções da versão web. *(Fase 7)*

### 8.2 Não funcionais

- **RNF01 Offline:** todas as funções, exceto a geração por IA, funcionam sem conexão.
- **RNF02 Privacidade:** no MVP, nada é enviado a terceiros sem ação explícita do usuário e a interface informa o que será enviado. Com a Fase 6, a sincronização é opcional, exige consentimento explícito e a política de privacidade deve ser publicada antes do lançamento (inclui adequação à LGPD).
- **RNF03 Desempenho:** interação imediata e carga inicial inferior a 1 s em rede comum **[A CONFIRMAR: meta medida via Lighthouse]**.
- **RNF04 Acessibilidade:** navegação por teclado, contraste AA, timer anunciado a leitores de tela, respeito a `prefers-reduced-motion`.
- **RNF05 Responsividade:** layout pensado primeiro para desktop; funcional em telas menores, com refinamento para celular após o MVP.
- **RNF06 Confiabilidade:** nenhuma anotação é perdida por recarga ou falha de armazenamento; falhas são comunicadas.
- **RNF07 Manutenibilidade:** lógica de domínio testável sem DOM; cobertura mínima definida na Fase 0 **[A CONFIRMAR]**.
- **RNF08 Idioma:** pt-BR, com textos isolados para permitir tradução.
- **RNF09 Preparação para sincronização:** todas as entidades usam identificador UUID gerado no cliente, `updatedAt` e exclusão lógica (`deletedAt`); todo acesso a dados passa pela interface `Repository`.

## 9. Modelo de domínio preliminar

**Campos comuns a todas as entidades persistidas** (necessários para a futura sincronização, ver RNF09):

```ts
BaseEntity {
  id: string,          // UUID gerado no cliente (nunca autoincremento)
  createdAt: string,   // ISO 8601
  updatedAt: string,   // ISO 8601, atualizado a cada alteração
  deletedAt?: string   // exclusão lógica; null/ausente = ativo
}
```

```ts
Subject       extends BaseEntity { name, color? }

Session       extends BaseEntity { subjectId?, title, summary,
                status: "active" | "finished",
                startedAt, endedAt? }                 // a "aula"

Note          extends BaseEntity { sessionId, cue, body }   // pista + explicação

ParkedThought extends BaseEntity { sessionId, text, resolvedAt? }

FocusBlock    extends BaseEntity { sessionId,
                kind: "focus" | "short_break" | "long_break",
                plannedSeconds, startedAt, endedAt?,
                outcome: "completed" | "skipped" | "reset" }

Notebook      extends BaseEntity { title, subjectId? }

Page          extends BaseEntity { notebookId, sessionId?, title,
                content,                 // Markdown, fonte da verdade
                origin: "ai" | "manual",
                sourceNoteIds: [] }      // rastreabilidade

Settings      { theme, soundOn, autoAdvance,
                durations: { focus, shortBreak, longBreak },
                blocksBeforeLongBreak, ai: { ... } }    // preferências; fora do esquema de sync por ora
```

**Relações:** Subject 1—N Session; Session 1—N Note, ParkedThought, FocusBlock; Notebook 1—N Page; Page N—N Note (origem).

**Estado vivo do timer** (rodando, término previsto `endsAt`) é mantido separado de `FocusBlock`, que registra apenas o histórico.

### Máquina de estados do timer

```
idle ─start→ running ─pause→ paused ─resume→ running
                │
                └─ fim do bloco ─→ autoAdvance ligado? 
                       sim: próximo bloco em running
                       não: awaiting_next (avisa e espera o usuário)

Sequência: foco → pausa curta → foco → ... → (a cada N focos) pausa longa
```

## 10. Regras de negócio preliminares

- **Só pode existir uma `Session` com status `active`.** Iniciar outra exige finalizar a atual.
- Pausa longa após **N** focos concluídos (N = 4, configurável) **[A CONFIRMAR]**.
- Pular ou reiniciar um foco não conta como ciclo concluído.
- Anotação totalmente vazia não é criada.
- Excluir uma entidade é lógico (`deletedAt`); a remoção definitiva é uma ação separada e explícita **[A CONFIRMAR: quando purgar]**.
- Notas originais são imutáveis pela geração de páginas; regenerar cria nova versão ou substitui **apenas a página**, nunca as notas **[A CONFIRMAR: versionar ou substituir]**.
- Excluir matéria não exclui aulas; elas ficam sem matéria.
- A IA deve organizar e estruturar o conteúdo do aluno; dúvidas anotadas permanecem como dúvidas, e qualquer conteúdo que não esteja nas notas deve ser sinalizado como sugestão.

## 11. Arquitetura e tecnologia (proposta)

| Aspecto | Proposta | Situação |
|---|---|---|
| Linguagem | TypeScript | Proposta |
| Interface | Vue 3 (Composition API, `<script setup>`) + Vite | **Decidido** |
| Estado | Pinia | Proposta |
| Rotas | Vue Router | Proposta |
| Persistência | Interface `Repository`; IndexedDB para aulas e cadernos (via Dexie ou `idb`); `localStorage` para preferências | **[A CONFIRMAR]** (D3) |
| Markdown | `markdown-it` (ou `marked`) + `DOMPurify` para sanitizar a saída | Proposta |
| Testes | Vitest + Vue Test Utils (unitários e componentes); Playwright (fluxos principais) | Proposta |
| Qualidade | ESLint, Prettier, Conventional Commits | Proposta |
| CI/CD | GitHub Actions; deploy estático (Vercel, Netlify ou GitHub Pages) | Proposta |
| PWA | Service worker + manifesto | Fase posterior |
| IA | Módulo isolado atrás de uma interface (`NoteOrganizer`) | Decidido |
| Contas e sincronização | Implementação remota da interface `Repository` + serviço de autenticação | Fase 6, a definir (D9, D10) |
| App de desktop | Empacotamento da mesma base web (Tauri ou Electron) | Fase 7, a definir (D11) |

**Organização em camadas:**

```
src/
  domain/         regras puras (timer, geração de página, tipos)
  storage/        interface Repository + implementações (IndexedDB, localStorage; futuramente remota)
  ai/             interface do organizador + provedor(es)
  stores/         stores Pinia (ligam domínio, storage e interface)
  composables/    lógica reativa reutilizável (ex.: useTimer)
  components/     componentes de interface
  views/          telas, uma por rota
  router/         definição de rotas
```

O domínio não depende de Vue, DOM, armazenamento nem IA. O `useTimer` é apenas uma casca reativa sobre a máquina de estados do domínio, que continua testável sozinha.

**Caminho para sincronização e desktop.** Como todo acesso a dados passa pelo `Repository` e todas as entidades têm UUID, `updatedAt` e `deletedAt`, a Fase 6 adiciona uma implementação remota (e uma camada de sincronização) ao lado da local, sem reescrever o domínio nem a interface. Como a base é web, a Fase 7 empacota o mesmo código para desktop em vez de manter dois projetos.

### Integração com IA — decidido: backend próprio

| Opção | Vantagens | Desvantagens |
|---|---|---|
| **A. Backend próprio** (função serverless que guarda a chave) | Boa experiência; chave protegida; demonstra full stack | Exige hospedagem, controle de custo e limites; quebra o "100% local" |
| **B. Chave do próprio usuário (BYOK)** | Sem servidor; custo do usuário; privacidade maior | Barreira para não técnicos; chave guardada no dispositivo |

**Decisão:** opção A. A interface `NoteOrganizer` fica no front-end e a implementação chama uma função serverless própria, que guarda a chave e fala com o provedor de IA. O app permanece funcional sem IA. Como o MVP não tem contas, o endpoint é público; por isso a proteção contra abuso (D8) é requisito da Fase 3. Com a chegada das contas (Fase 6), o endpoint poderá passar a exigir autenticação. Hospedar front-end e função no mesmo provedor (Vercel, Netlify ou Cloudflare) simplifica o deploy desde a Fase 0. A opção B (chave do usuário) fica como possível extensão.

## 12. Roadmap por fases

| Fase | Nome | Entregas | Critério de conclusão |
|---|---|---|---|
| **0** | Fundação | Repositório, tooling, CI, estrutura de pastas, README inicial, licença AGPL v3, esses documentos em `docs/` | CI verde com lint e um teste; deploy de "hello" publicado |
| **1** | Paridade | Timer (cálculo por `endsAt`), anotações, estacionamento, resumo, histórico, tema, exportação `.md` — em TypeScript, com o domínio testado | Tudo que o protótipo HTML faz funciona; timer com testes e sem dessincronização |
| **2** | Caderno | Notebook/Page, editor Markdown com pré-visualização, criação manual e a partir de aula, exportação | Aluno cria caderno e páginas sem usar IA |
| **3** | IA | Interface `NoteOrganizer`, primeiro provedor, tratamento de erro, regenerar, vínculo com notas de origem, avisos de privacidade, proteção do endpoint (D8) | Página gerada de uma aula real, com tratamento de falha e rastreabilidade |
| **4** | Robustez e alcance | PWA offline, notificações, timer persistente entre recargas (RF04b), busca, backup JSON, acessibilidade auditada | Lighthouse (PWA/A11y) com metas definidas; funciona offline |
| **5** | Extensões | Estatísticas, tags, revisão espaçada, editor rico, i18n | Conforme prioridade |
| **6** | Contas e sincronização | Autenticação, `Repository` remoto, sincronização com resolução de conflitos, vínculo de dados locais a uma conta, política de privacidade | Mesmo histórico acessível em dois computadores; app continua útil sem conta |
| **7** | Aplicativo de desktop | Empacotamento (Tauri ou Electron), atualização automática, integração com o sistema | Instalador funcional com paridade em relação à versão web |

Cada fase encerra com uma versão (tag) e nota de lançamento no repositório. As Fases 6 e 7 só serão detalhadas (requisitos e issues) quando a Fase 4 estiver concluída.

## 13. Riscos e mitigações

| # | Risco | Impacto | Mitigação |
|---|---|---|---|
| R1 | Aluno passa a depender da IA e deixa de anotar | Alto (fere a tese do produto) | Notas imutáveis; página gerada só após captura; rastreabilidade; texto de orientação no app |
| R2 | Exposição da chave de API | Alto | Nunca embutir chave no front-end; backend (A) ou chave do usuário (B) |
| R3 | Custo e abuso da IA no backend próprio | Médio | Limite por IP, tamanho máximo de entrada, teto de gasto configurado no provedor, modelo econômico; autenticação após a Fase 6; BYOK como alternativa futura |
| R4 | Privacidade das anotações | Médio | Envio só sob ação explícita; aviso claro; app útil sem IA |
| R5 | Perda de dados no armazenamento do navegador | Alto | IndexedDB, backup/importação JSON, tratamento de erro visível |
| R6 | Escopo crescer além do que o autor consegue entregar | Alto | Fases com critério de conclusão; Must/Should/Could; entregas pequenas |
| R7 | Resposta da IA de baixa qualidade ou alucinada | Médio | Prompt que restringe a organizar; sinalizar sugestões; regenerar; sempre manter as notas |
| R8 | Dessincronização do timer em segundo plano | Médio | Calcular por timestamp de término (`endsAt`), não por contagem de ticks |
| R9 | Projeto abandonado por perder o propósito | Médio | Continuar usando o app nas próprias aulas; melhorias nascem de dores reais |
| R10 | Injeção de HTML/scripts (XSS) ao renderizar Markdown vindo da IA ou importado | Alto | Sanitizar toda saída renderizada com DOMPurify; nunca usar `v-html` com conteúdo não sanitizado |
| R11 | Código gerado por IA que o autor não compreende, gerando dívida técnica e fragilidade em entrevistas | Alto | Regras de desenvolvimento assistido (14.1): entender antes de aceitar, testes como rede de segurança, revisão própria |
| R12 | A visão de longo prazo (contas, sync, desktop) invade o MVP e atrasa a entrega | Alto | Fases 6 e 7 só detalhadas após a Fase 4; no MVP, apenas a preparação barata (UUID, `updatedAt`, `deletedAt`, `Repository`) |
| R13 | Sincronização gera conflitos e perda de dados; dados na nuvem trazem obrigações de privacidade (LGPD) | Alto | Estratégia de conflitos decidida antes da Fase 6 (D10); exclusão lógica; backup JSON; política de privacidade e consentimento explícito |
| R14 | Licença escolhida não protege contra clone hospedado ou afasta contribuidores | Médio | AGPL v3 agora; autor único detém o copyright e pode relicenciar; exigir CLA antes de aceitar contribuições externas |

## 14. Premissas e restrições

**Premissas**
- O autor desenvolve sozinho, em tempo parcial.
- O uso principal é em navegador moderno, em desktop (celular em segundo plano).
- O projeto será público, sob licença **AGPL v3**, com a possibilidade de reavaliar antes de aceitar contribuições externas ou lançar o serviço com contas (D6).
- O autor é o único detentor do copyright do código no momento.

**Restrições**
- Custo de infraestrutura próximo de zero na fase inicial.
- No MVP (Fases 0 a 5), o projeto não armazena nada fora do dispositivo do usuário, salvo o que for enviado à IA por ação dele. Essa restrição será revista na Fase 6.

### 14.1 Método de desenvolvimento assistido por IA

O projeto será desenvolvido com IA em chats, sob supervisão do autor, que é o responsável pelo resultado. Para que isso reforce o aprendizado e o portfólio em vez de enfraquecê-los, valem estas regras:

1. **O autor é o responsável pelo código.** Nada entra no repositório sem que ele consiga explicar o que faz e por que foi feito assim. "Supervisionar" significa entender, não apenas aprovar.
2. **Tarefas pequenas e delimitadas.** Uma issue, um módulo ou uma função por conversa; evitar pedir "o app inteiro".
3. **Contexto fixo e versionado.** Manter um arquivo (ex.: `docs/CONTEXTO-IA.md`) com visão, stack, estrutura de pastas, convenções e decisões, para colar no início de cada conversa e manter respostas consistentes.
4. **Testes antes ou junto do código.** Especialmente no domínio (timer, geração de página); os testes são a rede de segurança contra erros sutis.
5. **Revisar, não apenas colar.** Ler o diff, rodar lint e testes, e questionar escolhas. Pedir à IA que explique alternativas e trade-offs.
6. **Verificar afirmações.** APIs e versões de bibliotecas sugeridas pela IA devem ser conferidas na documentação oficial.
7. **Escrever à mão o que for núcleo do aprendizado.** Por exemplo, a máquina de estados do timer e a camada de persistência.
8. **Commits pequenos, com mensagens próprias**, que contem a evolução do projeto.
9. **Transparência.** Registrar no README, de forma breve, que houve desenvolvimento assistido por IA e como foi usado; isso é visto como maturidade, não como fraqueza.
10. **Teste da explicação.** Antes de fechar uma issue, o autor deve conseguir explicar o código novo sem a conversa aberta. Se não conseguir, a issue não está concluída.

## 15. Critérios de sucesso

- **Uso real:** o autor usa o Cerne nas próprias aulas durante ao menos um período letivo/mês contínuo **[A CONFIRMAR: meta]**.
- **Qualidade técnica:** domínio com testes, CI verde, sem regressões nos fluxos principais.
- **Portfólio:** repositório com README claro (GIF/capturas, decisões técnicas, roadmap), demo publicada e histórico de commits legível.
- **Produto:** o ciclo completo (capturar → gerar página → exportar) funciona de ponta a ponta.

## 16. Decisões

### Tomadas
1. O Cerne evolui de captura de aula para **caderno de estudos**.
2. Páginas do caderno são **Markdown** e há exportação `.md`.
3. **Notas originais nunca são sobrescritas** pela IA.
4. A IA é um **módulo opcional e isolado**; o app funciona sem ela.
5. Abordagem **local-first**; contas ficam fora do MVP.
6. Interface em **Vue 3 + TypeScript + Vite**.
7. O desenvolvimento será **assistido por chats de IA**, sob as regras da seção 14.1.
8. A IA será chamada por um **backend próprio** (função serverless que guarda a chave). A chave nunca vai para o front-end.
9. **D4:** só uma aula (`Session`) ativa por vez.
10. **D6:** licença **AGPL v3**, podendo ser reavaliada antes de aceitar contribuições externas ou lançar o serviço com contas. Se houver contribuições externas, exigir CLA.
11. **D7:** o nome do projeto é **Cerne**. Falta conferir disponibilidade como repositório, pacote npm e domínio.
12. **Contas e sincronização** entram como **Fase 6**; o MVP segue local-first. Desde já: UUID no cliente, `updatedAt`, `deletedAt` e acesso por `Repository`.
13. **Aplicativo de desktop** entra como **Fase 7**, empacotando a mesma base web. O MVP é um web app pensado primeiro para desktop.

### Em aberto
| # | Decisão | Opções | Prazo |
|---|---|---|---|
| D3 | Persistência | Recomendação: acesso via interface `Repository`; começar com `localStorage` e migrar para IndexedDB (Dexie) até a Fase 2 | Decisão final até o fim da Fase 1 |
| D5 | Regeneração de página | Versionar × substituir | Antes da Fase 3 |
| D8 | Proteção do endpoint de IA (sem contas, o endpoint é público) | Limite por IP, tamanho máximo de entrada, teto de gasto no provedor, chave de acesso simples | Antes da Fase 3 |
| D9 | Backend de contas e sincronização | Serviço gerenciado (ex.: Supabase, Firebase) × backend próprio | Antes da Fase 6 |
| D10 | Estratégia de resolução de conflitos na sincronização | Última escrita vence (por `updatedAt`) × mesclagem por campo × CRDT | Antes da Fase 6 |
| D11 | Tecnologia do app de desktop | Tauri × Electron (verificar versões e requisitos na documentação oficial) | Antes da Fase 7 |
| D12 | Purga de itens excluídos logicamente | Manual × automática após N dias | Antes da Fase 1 |

## 17. Glossário

- **Aula (Session):** período de captura, com anotações, pensamentos guardados e blocos de foco.
- **Pista (cue):** termo ou pergunta-chave da anotação.
- **Explicação (body):** o que o aluno escreveu com as próprias palavras.
- **Estacionamento de pensamentos:** lista rápida de distrações a rever depois.
- **Bloco de foco:** intervalo cronometrado de concentração.
- **Caderno (Notebook):** coleção de páginas iniciada pelo aluno.
- **Página (Page):** documento em Markdown, escrito à mão ou gerado a partir de notas.
- **BYOK:** "bring your own key", isto é, o usuário fornece a própria chave de API.
- **Local-first:** os dados vivem primeiro no dispositivo do usuário; a nuvem, quando existe, é complemento.
- **Exclusão lógica (soft delete):** marcar um registro como excluído (`deletedAt`) em vez de apagá-lo, o que permite sincronizar a exclusão.
- **AGPL v3:** licença de código aberto que exige abrir o código de versões modificadas, inclusive quando oferecidas como serviço na web.
- **CLA:** acordo de licença de contribuidor, que permite ao autor relicenciar o projeto mesmo com contribuições externas.

## 18. Próximos passos

1. Conferir a disponibilidade do nome Cerne (GitHub, npm, domínio).
2. Criar o repositório com a licença AGPL v3.
3. Salvar este documento e os requisitos em `docs/`.
4. Criar `docs/CONTEXTO-IA.md` com visão, stack Vue, estrutura de pastas e convenções (ver 14.1).
5. Escrever os requisitos refinados das Fases 0 e 1, com critérios de aceite, e converter em épicos e issues.
6. Montar o GitHub Project (campos Fase, Prioridade e Estimativa; templates de issue).
7. Prototipar as telas da Fase 1 em baixa fidelidade, com foco em desktop.
8. Configurar tooling e CI (Fase 0): Vite, Vue 3, TypeScript, ESLint, Prettier, Vitest.
9. Escrever a máquina de estados do timer em `domain/`, com testes, como primeiro módulo.

---

## Histórico de versões

| Versão | Data | Mudanças |
|---|---|---|
| 0.1 | 30/09/2026 | Rascunho inicial |
| 0.2 | 16/11/2026 | Fecha D4 (uma aula ativa), D6 (AGPL v3) e D7 (nome Cerne). Adiciona Fase 6 (contas e sincronização) e Fase 7 (desktop). Plataforma passa a ser desktop-first. Adiciona UUID, `updatedAt` e `deletedAt` ao modelo (RNF09). Atualiza princípios, escopo, RNF02 e RNF05, premissas e restrições. Divide o RF04 em RF04a (Fase 1) e RF04b (Fase 4). Adiciona riscos R12 a R14 e decisões D9 a D12. Reforça 14.1 com a regra 10. |

_Este documento é vivo: registre mudanças de decisão e de escopo no histórico do repositório._
