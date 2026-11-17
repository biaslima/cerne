<!-- src/storage/README.md -->

# Storage

Camada de persistência de dados. Define a interface `Repository` e suas implementações concretas (`localStorage`, IndexedDB e, na Fase 6, sincronização remota).

**Regra:** Nenhum componente, view ou store deve acessar APIs de armazenamento do navegador diretamente; todo acesso passa por aqui.
