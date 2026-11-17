<!-- src/domain/README.md -->

# Domain

Regras de negócio puras, entidades e tipos do Cerne (ex.: máquina de estados do timer, modelos de Aula, Nota, Caderno e Página).

**Regra inegociável:** Este diretório não depende de Vue, DOM, armazenamento (`localStorage`/IndexedDB) nem provedores de IA. Tudo aqui deve ser 100% testável em isolamento com Vitest.
