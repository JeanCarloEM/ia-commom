# Converter prompt em `skill` e normatizar estrutura/subroteamento de `agents`

Transforme o **prompt fornecido em anexo** em uma `skill` para `agents`, preservando **integralmente requisitos, intenção, regras, exceções, precedências, exemplos normativos, restrições, nuances e comportamento esperado**, mas reestruturando-o para ficar **tecnicamente rigoroso, determinístico, sintaticamente correto e tão enxuto quanto possível sem qualquer perda semântica**.

A tarefa inclui também:

* normatizar e materializar no repositório as raízes canônicas de `skills` e `subagents`;
* estabelecer no `agents.local.md` o **subroteamento explícito, cirúrgico, contextual e sob demanda** desses artefatos;
* impedir que `skills` ou `subagents` sejam carregados indiscriminadamente, evitando consumo desnecessário de tokens/contexto.

## 1. Inspeção obrigatória

Antes de editar:

1. leia integralmente o prompt anexo;
2. inspecione a estrutura real do repositório;
3. localize e leia as normas aplicáveis, especialmente `AGENTS.md`, `agents.local.md` e equivalentes;
4. identifique `skills`, `subagents`, rotas contextuais, convenções, schemas, frontmatter, loaders, registradores ou mecanismos análogos já existentes;
5. determine o formato de `skill` efetivamente aceito pelos `agents` deste projeto/ambiente;
6. identifique como `agents.local.md` atualmente roteia instruções especializadas;
7. identifique conflitos, redundâncias ou mecanismos concorrentes antes de criar, mover ou normatizar arquivos.

NÃO presuma formato, schema, nome de arquivo, metadados, loader ou mecanismo de descoberta que possa ser comprovado por inspeção.

Se já existir convenção compatível, **preserve-a e especialize-a**; NÃO crie arquitetura concorrente.

## 2. Estrutura normativa

Passe a considerar como convenção oficial do repositório:

```text
./skills/
./subagents/
```

### `./skills/`

`./skills/` passa a ser a **raiz padrão e canônica para skills locais**.

Toda nova `skill`, salvo exceção normativa explícita, DEVE permanecer nessa árvore.

### `./subagents/`

`./subagents/` passa a ser a **raiz padrão e canônica para subagents locais** futuramente solicitados.

Nesta tarefa:

* crie/normatize o diretório;
* registre sua finalidade na governança aplicável;
* estabeleça seu mecanismo de subroteamento;
* NÃO invente subagents inexistentes;
* NÃO crie implementação funcional de subagent sem solicitação específica.

## 3. `agents.local.md` como roteador cirúrgico

O `agents.local.md` DEVE ser explicitamente normatizado como **roteador contextual de baixo custo**, e NÃO como agregador de conteúdo integral de `skills` ou `subagents`.

Sua função DEVE ser identificar **quando** e **qual** artefato especializado precisa ser consultado.

### 3.1. Princípio de carregamento mínimo

Por padrão:

```text
agent
  → lê governança mínima aplicável
  → identifica o contexto/tarefa
  → resolve a rota específica
  → lê somente a skill/subagent necessário
```

É PROIBIDO adotar:

```text
agent
  → carrega todas as skills
  → carrega todos os subagents
  → decide posteriormente o que precisava
```

O objetivo normativo é **minimizar leitura, tokens, contexto irrelevante e interferência cruzada**.

### 3.2. Subroteamento explícito

O `agents.local.md` DEVE conter regras curtas e inequívocas que permitam mapear:

```text
contexto/necessidade → artefato especializado
```

Por exemplo conceitual:

```text
se <condição A> → consultar ./skills/<skill-A>/...
se <condição B> → consultar ./skills/<skill-B>/...
se <necessidade futura C> → delegar/consultar ./subagents/<subagent-C>/...
```

Esses exemplos indicam o **modelo de roteamento**, NÃO nomes a serem inventados.

Cada rota DEVE definir somente o mínimo necessário para decidir:

* quando carregar;
* o que carregar;
* quando NÃO carregar;
* eventual precedência/dependência necessária.

O conteúdo especializado propriamente dito DEVE permanecer no arquivo roteado.

### 3.3. Roteamento positivo e negativo

Sempre que útil para impedir leitura indevida, a rota DEVE delimitar:

* **gatilho positivo**: condição em que o artefato DEVE ser consultado;
* **gatilho negativo**: contexto semelhante em que ele NÃO DEVE ser consultado.

A similaridade temática isolada NÃO é condição suficiente para carregar uma skill ou subagent.

A decisão DEVE decorrer da **necessidade material da tarefa**.

### 3.4. Granularidade

As rotas DEVEM ser suficientemente específicas para evitar carregamento amplo.

NÃO use instruções vagas como:

```text
Leia as skills quando necessário.
```

ou:

```text
Consulte ./skills/ para tarefas relacionadas.
```

Prefira regras determinísticas que permitam resolver diretamente o arquivo pertinente sem explorar toda a árvore.

### 3.5. Descoberta sem varredura integral

O `agents.local.md` DEVE permitir que um agente descubra o artefato correto **sem precisar abrir todos os arquivos de `./skills/` ou `./subagents/`**.

Para isso, PODE manter um índice/roteador compacto contendo, por artefato:

* identificador/nome;
* finalidade em uma linha;
* gatilho de uso;
* caminho relativo.

Inclua apenas metadados suficientes para roteamento.

NÃO replique regras internas da skill/subagent no índice.

### 3.6. Custo de contexto como requisito

Considere desperdício de contexto uma regressão arquitetural.

O roteamento DEVE buscar:

```text
mínimo de arquivos lidos
+
mínimo de tokens carregados
+
máxima precisão contextual
```

Sempre que duas soluções forem semanticamente equivalentes, prefira a que permita **carregamento mais localizado e tardio**.

### 3.7. Carregamento sob demanda

Skills e subagents DEVEM ser consultados:

* somente após a tarefa exigir seu domínio;
* somente durante o contexto em que forem relevantes;
* preferencialmente apenas no nível necessário para executar a tarefa atual.

NÃO imponha leitura preventiva “por garantia”.

### 3.8. Composição

Quando uma tarefa exigir mais de um artefato especializado:

* carregue somente os efetivamente necessários;
* respeite precedências;
* evite carregar dependências transitivas sem necessidade;
* NÃO trate coexistência temática como dependência automática.

Se uma skill puder resolver integralmente a tarefa, NÃO carregue outra apenas porque pertence ao mesmo domínio.

## 4. Conversão do prompt em `skill`

Converta o prompt anexo para uma `skill` válida, utilizando a sintaxe e estrutura efetivamente exigidas pelo sistema de `agents`.

A conversão DEVE:

* preservar integralmente o comportamento normativo do prompt;
* eliminar redundâncias reais;
* fundir regras semanticamente equivalentes;
* centralizar regras comuns;
* reduzir texto cerimonial ou explicativo sem função operacional;
* manter exemplos quando necessários para delimitar comportamento;
* distinguir claramente obrigação, permissão e proibição;
* usar linguagem normativa precisa (`DEVE`, `NÃO DEVE`, `PODE`, `É PROIBIDO`);
* eliminar ambiguidades;
* tornar critérios executáveis e verificáveis;
* permanecer autossuficiente quando carregada;
* evitar instruções duplicadas ou contraditórias;
* preservar explicitamente precedências, exceções e condições.

A redução de tamanho DEVE ocorrer **somente por compactação semântica**.

É PROIBIDO reduzir tokens mediante perda de:

* requisito;
* nuance;
* restrição;
* exceção;
* exemplo necessário;
* contexto operacional;
* comportamento esperado;
* critério de aceite;
* força normativa.

## 5. Formato da `skill`

A `skill` DEVE ser um `.md` sintaticamente correto e adequado ao mecanismo real utilizado.

Se o formato exigir:

* frontmatter;
* nome;
* descrição;
* triggers;
* escopo;
* instruções;
* exemplos;
* restrições;
* metadados;

inclua **somente os campos efetivamente suportados ou normativamente exigidos**.

NÃO invente schema.

O nome do diretório/arquivo DEVE:

* ser curto;
* ser semanticamente claro;
* seguir convenção existente ou, na ausência, convenção simples e determinística;
* evitar duplicidade com skill equivalente.

A estrutura preferencial, **somente se compatível com o mecanismo real**, é:

```text
./skills/<skill>/
└── SKILL.md
```

Se o projeto utilizar outra estrutura comprovada, preserve a implementação real e normatize `./skills/` como raiz canônica sem quebrar o loader.

## 6. Relação entre roteador e skill

Após criar a skill, o `agents.local.md` DEVE receber **somente a rota mínima necessária para alcançá-la**.

NÃO copie para `agents.local.md`:

* corpo da skill;
* exemplos internos;
* regras especializadas;
* procedimentos;
* validações detalhadas;
* conteúdo que só seja necessário depois de a rota ser acionada.

O roteador DEVE responder apenas:

```text
quando preciso disto?
onde está?
```

A skill responde:

```text
como executar?
quais regras se aplicam?
```

Essa separação é obrigatória para evitar duplicação normativa e carregamento desnecessário de tokens.

## 7. Governança

Atualize a governança aplicável para estabelecer explicitamente:

```text
skills    → ./skills/
subagents → ./subagents/
roteador  → ./agents.local.md
```

O `agents.local.md` DEVE:

* atuar como índice/roteador contextual;
* apontar pontualmente para skills/subagents;
* NÃO incorporar seu conteúdo;
* NÃO exigir leitura global das respectivas árvores;
* permitir seleção do artefato pela intenção/contexto da tarefa.

A governança DEVE ainda deixar claro que:

* `./skills/` é a raiz padrão para skills locais;
* `./subagents/` é a raiz padrão para subagents locais;
* especializações PODEM existir abaixo dessas raízes;
* exceções somente PODEM existir quando explicitamente justificadas por requisito técnico ou norma de maior precedência;
* arquivos futuros DEVEM seguir essas raízes por padrão;
* cada novo artefato especializado relevante DEVE receber rota explícita no `agents.local.md`, quando necessário para descoberta;
* essa rota DEVE ser adicionada sem transformar o roteador em documentação extensa.

NÃO altere versão, cabeçalho, estrutura ou governança não relacionada além do mínimo necessário.

## 8. Criação e migração de diretórios

Crie, quando inexistentes:

```text
./skills/
./subagents/
```

Se já existirem estruturas equivalentes em outro local:

1. inspecione dependências e referências;
2. determine se a migração é segura;
3. migre somente quando compatível;
4. atualize referências necessárias;
5. preserve retrocompatibilidade quando houver consumidores existentes;
6. NÃO duplique conteúdo funcional apenas para satisfazer a nova convenção.

Se a migração direta puder quebrar loaders, scripts, documentação ou automações, adapte a transição de forma compatível em vez de realizar movimentação destrutiva.

## 9. Subagents futuros

Embora nenhum subagent funcional deva ser inventado nesta tarefa, a arquitetura e governança DEVEM ficar preparadas para que futuras solicitações utilizem:

```text
./subagents/<subagent>/
```

ou a especialização compatível comprovada pelo ambiente.

Quando um subagent for futuramente criado:

* sua rota DEVE ser adicionada cirurgicamente ao `agents.local.md`;
* o roteador DEVE carregar/delegar a ele somente quando seu escopo for realmente necessário;
* NÃO se deve introduzir leitura global dos demais subagents;
* NÃO se deve duplicar no roteador a especificação interna do subagent.

## 10. Arquivos e referências

Após criar/converter a `skill`:

* atualize referências internas necessárias;
* atualize documentação normativa pertinente;
* ajuste caminhos antigos somente quando realmente substituídos;
* preserve links válidos;
* NÃO deixe referências órfãs;
* NÃO mantenha duas fontes normativas concorrentes para a mesma skill sem necessidade de compatibilidade comprovada;
* adicione/ajuste a rota correspondente no `agents.local.md`.

Caso o prompt original permaneça necessário apenas como histórico ou fonte, preserve-o conforme a governança existente; caso sua função passe integralmente à `skill`, NÃO mantenha duplicação normativa ativa sem justificativa.

## 11. Compatibilidade

A alteração NÃO PODE:

* quebrar carregamento de agents;
* invalidar configuração existente;
* remover comportamento do prompt original;
* alterar escopo material da instrução;
* criar dependência técnica desnecessária;
* inventar loader, registrador ou automação não exigida;
* modificar outras skills sem necessidade;
* criar subagents antecipadamente;
* transformar `agents.local.md` em arquivo monolítico;
* tornar obrigatória a leitura de artefatos especializados irrelevantes à tarefa corrente.

Se houver conflito entre esta solicitação e norma superior existente, preserve a norma superior e adapte a implementação, registrando a incompatibilidade somente se ela impedir o cumprimento integral.

## 12. Validação

Valide, conforme aplicável:

* sintaxe Markdown;
* frontmatter/schema da `skill`;
* descoberta/carregamento pelo mecanismo real;
* caminhos relativos;
* referências documentais;
* ausência de links quebrados;
* ausência de duplicação normativa;
* equivalência semântica entre prompt original e skill;
* existência de `./skills/`;
* existência de `./subagents/`;
* governança atualizada;
* rota da nova skill presente no `agents.local.md`;
* capacidade de localizar a skill sem varrer toda `./skills/`;
* ausência de exigência de leitura de skills não relacionadas;
* capacidade futura de subrotear `./subagents/` pelo mesmo princípio;
* ausência de regressões em agents/skills existentes.

### 12.1. Validação específica de eficiência contextual

Faça uma inspeção estática/lógica do fluxo esperado e confirme que uma tarefa que **não necessite** da nova skill:

```text
NÃO → carrega seu conteúdo
```

e uma tarefa que **necessite** dela:

```text
contexto
→ agents.local.md
→ rota específica
→ skill necessária
```

sem exigir:

```text
→ leitura das d
```
