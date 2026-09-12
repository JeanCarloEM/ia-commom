# Roteamento local

## Convenção

- `./skills/` é a raiz canônica das skills locais.
- `./subagents/` é a raiz canônica dos subagents locais.
- `./agents.local.md` é somente o índice contextual de baixo custo dessas raízes.
- Exceções exigem requisito técnico ou norma de maior precedência explícitos.

Resolver primeiro a necessidade material da tarefa; então consultar somente o caminho exato indicado por uma rota aplicável. É PROIBIDO varrer ou carregar preventivamente as árvores, inferir dependência por similaridade temática ou copiar para este arquivo o conteúdo dos artefatos. Se mais de uma rota for indispensável, carregar apenas as necessárias e respeitar a precedência aplicável.

## Rotas

### `gerar-artefatos-tecnicos`

- **Carregar quando:** for necessário criar, converter ou reestruturar uma solicitação em prompt, issue do GitHub, RCF, lista TO-DO ou artefato técnico equivalente pronto para outra IA.
- **NÃO carregar quando:** a tarefa pedir execução direta da implementação, análise ou relatório sem geração desse artefato, mera redação sem finalidade técnica, ou apenas execução de artefato já pronto.
- **Caminho:** `./skills/gerar-artefatos-tecnicos/SKILL.md`.

## Novos artefatos

Cada skill ou subagent futuro que precise ser descoberto DEVE ficar sob sua raiz canônica e receber aqui uma rota curta com gatilhos positivo e negativo e caminho exato. Até existir subagent funcional solicitado, `./subagents/` permanece apenas materializado e NÃO possui rota de carregamento ou delegação.
