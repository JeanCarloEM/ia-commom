- [ ] criar um texto de uma ou multiplas TO-DO(s), conforme a necessidade, utilizando a skill `gerar-pedidos-ia`, de forma criteriosa:
  - CONTEXTO:
    - Skills e Subagents no contexto de Agents Engineering — pesquisa na Web, em sites bem conceituados e, em especial, em artigos acadêmicos disponíveis publicamente e recentes, sobre as melhores práticas, melhores métodos e melhores formas. Uma tabela conceitual, mas simplória, de comparativo entre Agente e Skill, segue abaixo:

      ##

      | Dimensão Analítica           | [ AGENTE ] <br> A Abordagem Padrão                            | [ SKILL ] <br> A Habilidade Injetada                             |
      | :--------------------------- | :------------------------------------------------------------ | :--------------------------------------------------------------- |
      | **Natureza do Processo**     | Probabilística / "YOLO". Resolve no improviso.                | Determinística. Previsibilidade estrutural.                      |
      | **Padrão de Execução**       | Explora, deduz e tenta descobrir caminhos desconhecidos.      | Segue um rigoroso roteiro operacional (SOP) passo a passo.       |
      | **Risco de Alucinação**      | Moderado/Alto se a tarefa for complexa e o contexto inchado.  | Quase nulo (o modelo é forçado a um trilho estreito).            |
      | **Carga Cognitiva (Tokens)** | Dinâmica e expansiva.                                         | Focada e contida ao escopo.                                      |
      | **Regra de Ouro (Uso)**      | O caminho é desconhecido ou requer profunda análise criativa. | O caminho é conhecido e exige consistência corporativa absoluta. |

    - Os mesmos critérios e diretivas exigidos/requeridos pelo agents.md na confecção de normas DEVEM se aplicar;
    - O objetivo do resultado é uma TO-DO que editará o agents.md diretamente no repositório upstream de origem.
      - NÃO é para executar as solicitações, APENAS criar a TO-DO, que será inserida no repositório construtor do agents.md.
      - O target `agents.md` para edição no repositório construtor é o `./src/`, exceto o RCF e sub-RCFs, que devem ser atualizados.

  - SOLICITAÇÕES:
    - Aplique, sem perder os detalhes, nuances, rigor técnico, intensidade, força e explicitude já existentes no agents.md e RCF, neste apenas chamado de normas.
    - O conceito de SKILL e de SubAgents DEVE ser introduzido de forma explícita e utilizar, obrigatoriamente, o conceito de roteamento para inclusão de subarquivos (as SKILLs e SubAgents) APENAS quando efetivamente necessários.
    - O arquivo principal, agents.md, DEVE ter no máximo 400 tokens.
    - Conceitos óbvios para a IA, que não necessitem de pesquisa externa nem de leitura de novos tokens, NÃO DEVEM ser explicitados:
      - Mero exemplo: "soma-se 2 mais 4". Esta frase demonstra um conceito muito básico (de nível de ensino fundamental), que se espera que a IA saiba, sem precisar ler novos tokens, sem precisar pesquisar conteúdo externo e sem demandar processamento adicional; é diferente, por mero exemplo, de outra frase, como "visando mitigar o fluxo de commodities que poderiam impactar a demanda local e, ao mesmo tempo, em uma tentativa frívola de incentivar o desenvolvimento da produção nacional, mesmo diante de altas taxas de impostos", que pode ser uma frase que, apesar de uma aparente lógica, exija conhecimentos mais específicos da área.
      - Assim sendo, SOMENTE SE, e APENAS SE, for plenamente possível e for inequivocamente compreensível que o termo NÃO será mal compreendido, a omissão de explicitude poderá ocorrer, mas com uma ressalva.
      - PREFERIR: sempre que tecnicamente possível, simplificar drasticamente a sentença em vez de simplesmente omitir ou remover a explicitude, que PROVAVELMENTE foi intencionalmente adicionada para evitar falso positivo ou falso negativo diante de testes anteriores. Por simplificar, NÃO interpretar como reducionismo da intensidade ou força, mas como algo análogo a asserções que utilizem uma quantidade significativamente reduzida de tokens, no estilo matemático de sentenças, evitando as dificuldades naturais da língua/idioma.
      - Portanto, a remoção e a omissão são permitidas, mas não incentivadas. E, quando ocorrerem, DEVEM ocorrer com extrema cautela, GARANTINDO que a obviedade não deixe dúvidas nem margem para má interpretação, dubiedade e outros problemas.
      - No passado, os Agents/IA comumente editaram o agents.md dos seus próprios repositórios, ou do repositório upstream, e até mesmo violaram outras diretrizes do agents.md, justamente pela ausência de explicitude e força normativa. Assim sendo, embora a omissão ou eliminação possa ocorrer, ela é considerada temerosa e DEVE ser feita com extrema cautela. Havendo inequívoca possibilidade, pode ocorrer, mas prefira — eu reitero, e desejo que isso seja reiterado no resultado da TO-DO — um resumo ultrassucinto e agressivo da frase, mas que ainda mantenha a explicitude, sem dubiedade ou má interpretação; contudo, eu não faço disso uma proibição.
    - Revisões de texto já existente nas normas PODEM ser feitas, desde que haja justificativa técnica plausível que aprimore e evolua o rigor técnico, elimine dubiedades, reduza tokens e más interpretações, gere ganho de desempenho e otimize a leitura pela IA, sem perda de sentido, conceito, ideia e objetivo. Ou seja, refinamento de aprimoramento.
    - Pesquise na Web, em sites bem conceituados e, em especial, em artigos acadêmicos disponíveis publicamente e recentes (último ano), sobre as melhores práticas, melhores métodos e modelos, e melhores formas no desenvolvimento de `agents.md` e seus subarquivos, seus testes e diretrizes. Embora não seja para aplicá-las à revelia, SE, e SOMENTE SE, elas NÃO infringirem as preocupações cautelares quanto à regressão, potencial omissão ou redução, criando lacunas ou espaços para má interpretação, perda de intensidade, rigor ou força, ainda que paulatinamente, então PODEM ser aplicadas. Contudo, se houver estimativa de potencial prejuízo, faça uma breve explicação "do que", "como", prós e contras e "onde", para que o dev decida. Valide apenas o que realmente vale a pena sugerir antes de propor uma melhoria.
    - Os roteamentos DEVEM permanecer sendo realizados por meio de tabelas e, se for conveniente e otimizar, PODEM ser separados em múltiplas tabelas conforme contexto/escopo.
    - O conceito e uso de microtexto/microconceitos DEVE ser reforçado, aprimorado e usado de forma contínua, SEMPRE que permitir ganho em alguma rota.
    - Agents.md já implementa vários e diversos scripts; crie, para os scripts que forem apropriados, Skills ou, quando conveniente, SubAgents, que agrupem vários desses scripts que, em geral ou comumente, seriam executados em conjunto e sob a supervisão de uma IA, visando otimizar ainda mais a atuação do agent principal.
    - Muitos scripts ou verificações, como, por mero exemplo, a verificação de um código implementado (sua execução), bem como uma avaliação de um aplicativo ou site, podem demorar bem mais do que se projeta, e isso toma muito tempo do agent principal e tem alto potencial de consumir tokens ou tempo de processamento. Em muitas situações, o agent ou a IA fica verificando regularmente a saída ou o resultado de uma execução em um intervalo muito curto, incompatível com a duração real daquele comando, mesmo que já tenha aprendido antes, ou mesmo que já se lembre de que aquele comando demora, o que ocasiona desperdício de recursos: isso nunca pode ocorrer. O agent/IA DEVE atuar de forma proativa diante de cada tipo de execução, evitando consumir tokens ou tempo de processamento desnecessariamente, em especial quando sabe que dado comando ou tipo de verificação pode demorar muito tempo.
    - Implemente o arquivo `memory.md` com localização no mesmo diretório do `continue.ia`. Enquanto o `continue.ia` DEVERÁ preservar todos os conteúdos relacionados ao estado atual de processamento para retomada, DEVENDO ser atualizado continuamente, a cada passo ou etapa, por menores que sejam, o `memory.md` visa ser um arquivo de aprendizado do Agent/IA quanto ao projeto como um todo: o que dá certo e o que não dá certo; em que condições ou em que computador dá certo e em que condições ou computador não dá certo (deve-se considerar que um mesmo projeto pode, mesmo pelo mesmo dev, ser aberto em múltiplos computadores); quais tentativas já foram feitas; o que falhou; o que demora muito e compensa esperar mais antes de ficar verificando; entre outras coisas já amplamente consolidadas no mercado e que são úteis de serem colocadas e armazenadas no `memory.md`.
      - O `memory.md` tem foco 100% para IA; portanto, a redução de tokens e a densidade informacional devem ser agressivamente otimizadas para a leitura por IA, e não por humanos, evitando tokens de que humanos precisariam para compreender.
      - O `memory.md` deve ser ultrassucinto, mas isso não significa eliminar informação necessária ao bom desempenho dos Agents/IA.
      - O `memory.md` DEVE ser lido obrigatoriamente, exceto, e apenas se, houver justificativa técnica plausível, como, por mero exemplo, um procedimento totalmente mecânico — neste caso, um script puro DEVE ser preferido à IA/Agent.
      - Mover de `continue.ia` para `memory.md` qualquer diretriz/funcionalidade que seja compatível com a definição atual de `memory.md`, exceto a função que fica preservada ao `continue.ia` de preservar o estado atual de cada FT e o estado atual em que o projeto/repositório parou ou foi interrompido.
      - Mover: interpreta-se que algumas das características de `memory.md` estavam presentes/definidas para `continue.ia` e, agora, DEVE-SE segregar o que cada arquivo faz, e NÃO eliminar as funções deles, suas necessidades e finalidades.
    - Skills e SubAgents do repositório construtor de agents.md têm uma finalidade totalmente diferente da deste repositório atual: ele visa ser generalista, funcionar para qualquer cenário possível e para múltiplos tipos de repositório; portanto, a especialização não é tolerada. O conceito de hookable atualmente aplicável tanto ao agents.md quanto aos scripts também DEVE ser aplicável às SKILLS e SubAgents criadas nele e DEVE permanecer como algo opcional a ser fornecido — ou seja, as SKILLs, SubAgents e scripts DEVEM ser totalmente funcionais independentemente do fornecimento desses hooks, tanto quanto tecnicamente viável.
      - Regras de manifesto para fornecimento de informações sobre os hooks e diretrizes aos repositórios DEVEM ser obedecidas e criadas para cada um deles.
      - Com muita cautela, rigor técnico e cuidado para não regredir, verificar se algum roteamento de cenário, atualmente preexistente em agents.md e não identificado como SKILL ou SubAgent, seria melhor enquadrado NÃO como cenário (ou o equivalente atualmente nomeado), mas como SKILL ou SubAgent, e se sua função, finalidade e procedimento são de fato aplicáveis. Se for, cirurgicamente, para cada um deles, faça a conversão.
      - Skills e SubAgents DEVEM ter diretórios próprios, bem nomeados e bem definidos, dentro de `.ia.rules/`, este dentro de `src/`, que é de fato o local de edição.
    - NENHUMA edição pode regredir ou reduzir a força normativa, a intensidade, explicitude ou rigor técnico, ou ainda remover features, ainda que expressamente autorizada. Sempre que algo for compreendido na solicitação como tal, DEVE ser relido e conciliado como uma integração de aprimoramento, e NÃO de revogação ou involução. Se não houver possibilidade lógica de coexistência, então questione obrigatoriamente o desenvolvedor. Se a coexistência, mesmo que tolerável do ponto de vista lógico, ocasionar fragilidades inequívocas, também questione o desenvolvedor. Em ambos os casos: "do que", "como", prós e contras e "onde", para que o dev decida.
  - Um novo cenário, ou SKILL ou SubAgents DEVE ser criado em `agents.md` contendo, de forma aprimorada e ultra rigorosa, sem perder detanhes e nuances, as normativas para a execução do `TODO.ia.md`. Tal diretrizes normas, senão me angano já existem, e devem ser agregadas (somadas) com o texto abaixo - é claro, aprimorando e ajustando sua total integração:

    ```markdown
    # RCF — Governança da TO-DO

    Esta seção de governança DEVE permanecer no topo do arquivo, NÃO PODE ser removida nem editada e rege todas as TO-DOs posteriores até o marcador explícito de início das TO-DOs operacionais.

    O arquivo TODO.ia.md não pode ser removido.

    ## 1. Estrutura normativa do arquivo

    Este arquivo constitui uma lista normativa e operacional de TO-DOs convergentes.

    Todo item de topo DEVE:

    - iniciar exatamente com `- [ ]` ou `- [x]`;
    - começar sem indentação;
    - representar uma frente autônoma subordinada às normas deste RCF.

    Todo conteúdo imediatamente posterior a um item de topo, enquanto não houver outro item iniciado sem indentação por `- [ ]` ou `- [x]`, DEVE ser interpretado como subordinado ao item de topo imediatamente anterior.

    A forma interna dessa subordinação é livre: PODE conter subtítulos, subitens, regras em estilo RCF, ordens, critérios, listas de afazeres, etapas, notas ou estruturas equivalentes. A semântica hierárquica prevalece sobre a forma.

    A formatação do arquivo DEVE preservar indentação visual coerente e inequívoca de todo conteúdo subordinado. Títulos, listas, blocos e demais conteúdos pertencentes a um item de topo DEVEM permanecer visualmente aninhados a ele.

    ## 2. Status, andamento e conclusão

    Cada item/subitem DEVE usar **apenas um emoji como marcador de status**, substituindo integralmente o checkbox do GitHub. **O nome ou a descrição do status NÃO DEVE acompanhar a tarefa**; existem apenas nesta legenda.

    Exemplo: `⏳ Implementar suporte a YAML` — e NÃO `⏳ Em desenvolvimento: Implementar suporte a YAML`.

    - ⬜ **Não iniciada:** na fila, aguardando início.
    - 📌 **Registrada:** possui **FT (Frente de Trabalho)** equivalente criada.
    - 📜 **Normatizada:** revisada, alinhada aos requisitos técnicos e incorporada ao RCF ou norma equivalente.
    - ⚖️ **Equalizada:** compatibilizada com as demais TO-DOs, podendo ter sido ajustada/adaptada para eliminar conflitos, redundâncias ou inconsistências.
    - ⏳ **Em desenvolvimento:** implementação em andamento.
    - 🔄 **Retomada:** retornou ao desenvolvimento após feedback ou correção de bugs solicitada pelo dev.
    - 🔎 **A revisar:** já percorreu uma ou mais etapas, mas exige reavaliação frente a novas demandas, TO-DOs ou revisões do projeto quanto à **adequação, pertinência, atualidade e ajustes necessários**.
    - ✅ **Concluída — pendente de validação:** implementação finalizada, aguardando aprovação humana (Code Review/QA).

    > ⚠️ **Regras:** o **emoji, isoladamente, identifica o status** e DEVE substituir qualquer checkbox ou indicação textual equivalente no item/subitem. Nem toda tarefa precisa percorrer todos os estados; apenas **⬜ Não iniciada**, **⏳ Em desenvolvimento** e **✅ Concluída** integram obrigatoriamente o ciclo mínimo, enquanto os demais aplicam-se quando pertinentes. Após validação e aprovação efetiva pelo dev, a tarefa DEVE ser **removida integralmente da lista**. ✅ significa **implementada**, não **aprovada/encerrada**.

    ## 3. Regra perene de convergência

    - [ ] Equalizar e executar as TO-DOs como frentes convergentes de um único objetivo
      - Este item rege todas as demais TO-DOs. Cada uma DEVE ser tratada como frente complementar de uma única execução, conciliada com as demais e convergente ao objetivo principal do projeto.

      - Contradições aparentes DEVEM ser presumidas como imprecisão redacional e resolvidas por equalização, sem perda de intenção, requisito, restrição ou nuance. Havendo conflito material não solucionável pelas normas e pelo contexto, o desenvolvedor DEVE ser consultado.

      - Considerações, comparações ou solicitações PODEM não ser plenamente aderentes ao projeto, especialmente quando previamente processadas por IA. Salvo dúvida material, a IA DEVE interpretá-las conforme o contexto já normatizado no RCF e no `README.md`; persistindo ambiguidade ou incompatibilidade, DEVE consultar o desenvolvedor antes de prosseguir.

      - O `AGENTS.md` prevalece absolutamente; o RCF vigente prevalece sobre as demais fontes subordinadas. Toda alteração DEVE aprimorar o projeto, ampliar capacidades e recursos, preservar compatibilidade e força normativa e NÃO PODE introduzir regressão.

      - Antes de executar qualquer TO-DO, a IA DEVE:
        1. ler integralmente todas as TO-DOs e normas aplicáveis;
        2. equalizar objetivos, requisitos, dependências, precedências e terminologia;
        3. resolver incompatibilidades, ambiguidades, sobreposições e lacunas;
        4. adaptar, consolidar, desmembrar, reordenar ou eliminar itens somente quando isso aumentar a coerência sem reduzir o objetivo material.

      - Toda TO-DO DEVE ser separada em fases:
        - **Normatização (RCF):** atualização de RCFs, contratos, precedências e documentação normativa necessária;
        - **Implementação:** código, migrações, testes, validações e alterações funcionais.

      - Após a equalização, a IA DEVE iniciar e concluir imediatamente a **Normatização RCF de todas as TO-DOs**, mantendo rastreabilidade entre cada regra e sua implementação futura.

      - Concluída a normatização, a IA DEVE INTERROMPER antes de qualquer implementação e solicitar autorização expressa do desenvolvedor, informando sucintamente:
        - implementações pendentes;
        - dependências e ordem recomendada;
        - impedimentos materiais identificados.

      - Somente quando aplicável ao contexto do repositório, toda alteração que modifique o modo de codificar Markdown DEVE ser documentada no respectivo modo de uso.

      - Este item e toda a seção `# RCF — Governança da TO-DO` são perenes: NÃO PODEM ser marcados como concluídos, removidos ou alterados. Sua contabilização somente é necessária enquanto existir ao menos uma TO-DO por eles regida.

      - Sempre que a Execução da TODO.ia.md for solicitada, e não meramente "continuada", então, este item "Equalizar" DEVE ser o primeiro a ser executado como sendo o primeiro item da TO-DO.
    ```

    - Especificamente quanto ao título `## 2. Status, andamento e conclusão` do texto acima, ele passa a ser regra de notação para itens de todo RCF, TODO.ia.md e continue.ia e outro que implique em lista de afazares (e status dos afazeres), relacionados diretamente a estes.

  - Se, e SOMENTE SE, algo equivalente não existir, DEVE ser criado um arquivo `.md` (mas se existir as diretrizes devem ser atualizadas para evoluir), ultrassucinto, para conter o histórico de correções solicitadas. Este arquivo DEVE seguir estilo e diretrizes similares, naquilo que couber, aos do `memory.md` e do `continue.md`. Ele DEVE estar localizado no mesmo diretório desses arquivos e, caso já exista algum equivalente, este DEVE ser migrado para cá e renomeado. Sugiro fortemente o nome `fix.md` ou algum nome mais sugestivo para a finalidade. Seu objetivo é armazenar, de forma ultrassucinta, toda reclamação ou solicitação de correção que o dev tenha feito quanto a qualquer implementação que não tenha resultado naquilo que, de fato, ele havia pedido, ainda que parcialmente, incluindo bugs, falhas visuais e outros. Ele DEVE ser focado 100% na leitura por IA/máquinas, ser supercurto e PODE conter sub-roteamento para outros arquivos, evitando alta densidade de leitura de tokens desnecessariamente.
    - Ele DEVE conter, nesse roteamento, o que foi reclamado de forma ultrassucinta, mas suficiente para a compreensão do contexto pela IA (incluindo o que, em que situação e sob quais circunstâncias), quais eram a(s) FT(s), TO-DO(s) e análogos envolvidos, bem como os commits envolvidos. Ele DEVE indicar, em caso de roteamento, o arquivo com maiores detalhes e, em caso de não roteamento, todos os arquivos vinculados: o texto principal da solicitação, seja issue, TO-DO ou prompt; possíveis evidências vinculadas a ele; entre outros que subsidiem o rastreio pela IA, para avaliar de forma rápida e fácil o que, como e por que ocorreu e, dessa forma, aprender e evoluir, por meio do `agents.local.md` e do `memory.md`, para evitar erros semelhantes.
    - Ele próprio DEVE ser bem resumido, minimamente suficiente para o Agent/IA ser capaz de decidir se deve ou não seguir aquela rota.
    - Ele também DEVE ser usado para EVITAR regressões sempre que uma solicitação futura tiver potencial de interferir justamente no mesmo contexto.
    - Um arquivo, que sugiro chamar de `FT.implementados.md`, análogo ao de todas as FTs, com texto ultrassucinto, sem etapas e subetapas, DEVE conter, de forma ultrassucinta, para permanecer extremamente pequeno e DEVENDO ser sub-roteado por contexto e, talvez, por subcontexto (caso o número de FTs cresça), a fim de melhorar o desempenho e reduzir a leitura de tokens; deve conter o contexto um resumo ultra curto do que foi pedido e feito, de forma ultrassucinta. Ele DEVE apontar para o pedido original — seja correção, evidências, FT, TO-DO, issue ou o conjunto delas — que o gerou, contendo a explicação original. Mas ele próprio DEVE ser bem resumido, minimamente suficiente para o Agent/IA ser capaz de decidir se deve ou não seguir aquela rota.
    - O `fix.md` pode e DEVE, ser isso economizar consumo de tokens pela IA, convertir para os mesmos destinos de `FT.implementados.md`, mantendo a distinção de escopo que cada arquivo tem, enquanto um, agrupa todas as FT, o outro agrupa apenas os fixs.
  - Toda skill e subagents criado, pelo repositório construtor ou por repositório consumidores, DEVEM ser automaticamente configurados e de forma autônoma, no arquivo de configuração pertinente ao ambiente e IA usado, para garantgir que ambos sejam invocados perfeitamente.
    - Script e hoock DEVEM ser criados e disponibilizados pelo construtor no agents.md
    - um arquivo de configuração pertinente, para cada tipo de ambiente IA, DEVE ser fornecido no release, entretanto ELE não pode estar localizado dentro do zip, em local, que se copiado, substitua o arquivo destino de forma imediata, já que o arquivo destino pode e provavelmente conterá outras configurações, assim sendo, o SCRIPT e hook, de atualização DEVEM ser plenamente capazes de mesclar a nova configuração com a antiga, sem quebrar o repositório destino, sem falhar: sendo totalmente fail safe (não no sentido de não falhar ou não travar), mas de efetivamente concluir a atualização, garantindo que ela ocorra, ainda que, para isso precise fazê-lo por mdiferentes meios até conseguir concluir. A falha somente pode ocorrer quando, multiplas dentativas, multuplas formas, e multiplos modelos, foram tentatos para a mesma coisa, e falharam, e não existe solução técnica conhecida na comunidade para aquele problema, ou quando aquele problema foge do esocpo resolvivel pela computador (por exemplo, um ausência real de internet, que não depende de uma configuração).
  - Foi verificado perda ou redução significativa de rigor ou desempenho técnico no desenvolvimento de projetos visuais. Simplesmente explicar algum conceito ou correção deixou de ser suficiente. Depois, mesmo desenhando sobre capturas de tela, e acrescentando texto explicativo, verificou-se que os agents/IA não são capazes de comprender ou entender a solicitação visual, o diagrama, e o que se pretende de fato. Isso é um ponto crítico, pois as explicações, foram passadas por prompt de IA, para melhorar o texto da solicitação; as imagens de captura foram tratadas no photoshop, para indicar setas, localizações e trechos com problemas e, em muitos casos, fora indicados na própria imagem ou na imagem exportada como PDF para preservar o texto escrito, o que estava errado, como estava errado e porque estava errado, e o que deveria ser, fazendo vinculo adicional com o texto de prompt tratato pela IA de forma separada. Ou seja, após tudo isso: o texto estava explicativo, revisado e as imagens bem detalhadas e diagramadas, e mesmo assim, o agents/IA não foi capaz de cumprir a solicitação e quando chegou perto ainda entregou algo insuficiente, significativamente fora da solicitação.
    - Agents.md e seus associados DEVEM ser ajustados pontualmente, quando for apropriado e SE houve o que fazer a respeito, para tornar a IA e os agents ainda mais certeiros quando lerem PDF ou imagens que apontem ou indiquem erros, problemas ou falhas, e que indiquem melhorias visuais.
    - Também, DEVE indicar precisão visual arbitrária, mas com isso, é importante salientar que, em especial em contexto WEB, nem sempre é bom usar a unidade `px` ou `pt`, justamente por ser uma unidade que pode NÃO ser aderente a responsividade (por ser arbitrárias), e pode criar distorções, portanto, EXCETO SE estritamente necessário e tecnicamente justificável, a PRIORIDADE e preferência ao desenvolver qualquer leyout, em especial os WEB é utilizar as unidades relativas, como "em", "rem", "vh", "vw" e análogos.
      - SKill e subagents de terceiros, generalistas, mas amplamente conceituadas, mantidas e opensource, podem e DEVEM ser usados se, e SOMENTE SE, representarem evolução no desempenho e qualidade dos resultados; desde que não violem ou confrontem as diretrizes estabelecidas nas normas, ou seja, eles DEVEM se submeter, e NUNCA se sobrepor as normas do agents.md.
      - MCU podem ser e DEVEM ser usadas, de igual forma, generalistas, mas amplamente conceituadas, mantidas e opensource (ou freeware), podem e DEVEM ser usados se, e SOMENTE SE, representarem evolução no desempenho e qualidade dos resultados; desde que não violem ou confrontem as diretrizes estabelecidas nas normas, ou seja, eles DEVEM se submeter, e NUNCA se sobrepor as normas do agents.md.
        - Se, não houver alternativa boa o suficiente e uma MCU paga for altamente recomendadas, então, sugira ao ao DEV, mas não tome uma decisão sem expressa autorização do DEV.
