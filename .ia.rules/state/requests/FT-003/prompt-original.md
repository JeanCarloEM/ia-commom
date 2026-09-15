# Migrar e reforçar normas de TTS e edição redacional

Acesse **somente em modo leitura** o repositório externo:

```text
D:\trampo\jeancarloem.com.blog\
```

Leia o RCF, normas e diretrizes aplicáveis a **TTS** e **edição/tratamento de conteúdo redacional** e, a partir deles, crie no repositório atual **uma ou mais TO-DOs autossuficientes** para recriar essas capacidades, preservando integralmente requisitos, nuances, exceções, precedências, exemplos normativos e força obrigatória, mas adaptando-as à arquitetura real do destino e incorporando os ajustes abaixo.

O repositório externo é **fonte somente-leitura**: É PROIBIDO modificá-lo.

## 1. Destino e forma de implementação

O destino é o **repositório construtor de `agents.md`**.

Antes de definir arquitetura, inspecione a governança e o estado real do destino. As capacidades migradas DEVEM ser implementáveis, conforme melhor adequação técnica, como uma ou combinação mínima de:

- script puro;
- `SKILL`;
- `SubAgent`;
- `Scenario`/cenário;
- mecanismo equivalente já normatizado.

NÃO imponha forma arquitetural sem evidência.

Em qualquer caso, a solução DEVE ser **hookable**:

- possuir contrato/entrypoint claro para futura invocação por hook;
- funcionar integralmente sem hook;
- ser testável/executável de forma independente;
- não depender de acoplamento oculto ao mecanismo chamador.

```text
hookable ≠ hook obrigatório
```

## 2. Resultado

Crie a **menor quantidade de TO-DOs** capaz de manter responsabilidades coesas e autossuficientes.

Cada TO-DO DEVE:

- usar raiz `- [ ] ...`;
- conter contexto suficiente para implementação sem nova reconstrução da análise;
- distinguir regras herdadas da origem dos aperfeiçoamentos deste prompt;
- exigir inspeção do destino quando o estado real não estiver comprovado;
- definir requisitos, restrições, validações e critérios de aceite;
- preservar rastreabilidade suficiente para reconsulta da origem;
- evitar duplicação normativa e carregamento desnecessário de contexto.

O texto final das TO-DOs DEVE ser devolvido em **arquivo `.md` para download**.

---

# 3. Edição de conteúdo redacional/autoral

## 3.1. Preservação de estilo autoral

Toda edição de conteúdo autoral/redacional DEVE preservar rigorosamente o **estilo linguístico, autoral e redacional do autor humano original**, incluindo, quando característicos:

- vocabulário;
- ritmo;
- estrutura sintática;
- pontuação;
- cadência;
- intensidade;
- escolhas estilísticas;
- formas recorrentes de argumentação;
- marcas de oralidade/escrita;
- nível de formalidade;
- construções idiomáticas.

A edição DEVE parecer ter sido realizada pelo próprio autor.

O critério de qualidade é forte: **mesmo sob avaliação técnica especializada, a intervenção da IA/agente NÃO DEVE ser perceptível como mudança de autoria ou estilo**.

É PROIBIDO:

- homogeneizar o texto para um “estilo de IA”;
- sofisticar artificialmente o vocabulário;
- neutralizar peculiaridades autorais válidas;
- trocar pontuação característica sem necessidade;
- alterar voz, personalidade ou intenção;
- introduzir tom corporativo, publicitário ou excessivamente acadêmico quando não existir no original.

Correções gramaticais, ortográficas, semânticas e de fluidez DEVEM ocorrer **dentro do estilo do autor**, não substituindo-o.

## 3.2. Acessibilidade linguística obrigatória

Toda edição DEVE priorizar linguagem **máxima e genuinamente acessível**, visando compreensão inclusive por pessoas com:

- escolaridade equivalente à 4ª série do ensino fundamental;
- baixa proficiência de leitura;
- possível analfabetismo funcional;
- dificuldade de interpretação textual.

Isso NÃO autoriza:

- infantilização;
- redução indevida do conteúdo;
- perda de rigor;
- simplificação conceitual incorreta;
- tom condescendente;
- eliminação de nuances.

O objetivo é:

```text
máximo rigor intelectual
+
máxima inteligibilidade
```

## 3.3. Vocabulário complexo

Palavras/expressões rebuscadas ou tecnicamente complexas:

- NÃO são proibidas;
- DEVEM ser evitadas quando houver equivalente simples igualmente preciso;
- DEVEM ser mantidas quando necessárias ao rigor, precisão ou domínio técnico.

Quando uma palavra/expressão complexa for necessária, sua **primeira ocorrência** DEVE ser seguida imediatamente por explicação curta entre parênteses, em linguagem direta e simples, suficiente para que uma pessoa com dificuldade interpretativa compreenda o significado e consiga interpretar ocorrências posteriores.

Exemplo estrutural:

```text
termo complexo (explicação simples e direta)
```

A explicação DEVE ser:

- curta;
- objetiva;
- semanticamente correta;
- não circular;
- sem usar outro termo igualmente obscuro.

NÃO repita a explicação em todas as ocorrências.

Nova explicação PODE ocorrer apenas quando:

- o texto for suficientemente longo para tornar provável o esquecimento;
- houver mudança relevante de sentido/contexto;
- a ausência de reforço prejudicar a compreensão.

## 3.4. Complexidade sintática

Mesmo com palavras simples, construções podem ser difíceis.

Portanto, DEVE-SE evitar, quando possível:

- períodos excessivamente longos;
- excesso de orações subordinadas;
- encadeamento de abstrações;
- múltiplas negações;
- ambiguidades referenciais;
- combinações lexicais desnecessariamente complexas;
- densidade conceitual sem apoio contextual.

Quando o assunto for complexo, reestruture a explicação para facilitar compreensão **sem reduzir rigor, conteúdo, nuance ou precisão**.

Essa regra DEVE ficar **expressa, forte e bem delimitada** nas normas e modus operandi resultantes.

---

# 4. Arquitetura de TTS

O TTS DEVE possuir etapa explícita de **normalização semântico-fonética para pt-BR antes da síntese**:

```text
conteúdo editorial original
→ detecção/interpretação contextual
→ representação própria para fala
→ TTS
```

O conteúdo editorial original NÃO DEVE ser alterado permanentemente para compensar limitações do sintetizador.

A normalização DEVE ser:

- adequada ao português brasileiro;
- contextual quando houver ambiguidade;
- determinística quando possível;
- extensível;
- testável;
- preferencialmente desacoplada do engine TTS.

Regex PODE auxiliar detecção, mas NÃO DEVE substituir interpretação contextual quando o significado depender do contexto.

---

# 5. `vs`, `vs.` e `x`

Quando usados semanticamente como confronto/comparação, independentemente de caixa:

```text
vs
vs.
VS
Vs.
x
X
```

DEVEM ser pronunciados como:

```text
versus
```

A conversão NÃO PODE ser cega.

Especialmente `x` DEVE ser distinguido de:

- multiplicação;
- dimensão;
- variável;
- identificador;
- símbolo técnico;
- outros significados legítimos.

Somente o uso real de confronto/comparação DEVE produzir `versus`.

---

# 6. Algarismos romanos

O normalizador DEVE reconhecer e verbalizar corretamente **algarismos romanos contextualmente válidos**.

Considere, entre outros:

- séculos;
- capítulos;
- volumes;
- enumerações;
- reis/papas;
- títulos históricos;
- outros usos editoriais legítimos.

É PROIBIDO converter cegamente qualquer sequência de `I`, `V`, `X`, `L`, `C`, `D`, `M`.

A implementação DEVE:

1. validar o numeral romano;
2. avaliar contexto;
3. escolher leitura cardinal/ordinal quando aplicável;
4. impedir falsos positivos em siglas, identificadores e texto comum.

---

# 7. Aspas e leitura de citações

Em leitura oral de livros, revistas e conteúdo redacional, aspas PODEM exigir verbalização explícita para tornar clara a existência de uma citação.

Quando isso for semanticamente adequado, o TTS DEVE poder produzir forma natural em pt-BR, preferindo algo como:

```text
citação ... fim da citação
```

em vez de formulações mais pesadas como:

```text
início da citação ... fim da citação
```

quando ambas forem semanticamente equivalentes.

A verbalização NÃO DEVE ser aplicada cegamente a toda ocorrência de aspas: preserve os contratos/contextos já existentes na origem e evite transformar realce, ironia ou usos não citacionais em citações formais.

---

# 8. Referências `<sup>` / notas

Quando um modo de TTS determinar que referências `<sup>` ou equivalentes devem ser pronunciadas, **NUNCA leia apenas o número isolado**.

Exemplo inadequado:

```html
texto<sup>32</sup>
```

→ `texto, trinta e dois`

Isso pode fazer `32` parecer parte da própria frase.

A referência DEVE ser semanticamente marcada, por exemplo:

```text
nota trinta e dois
```

ou expressão equivalente definida pela norma.

## 8.1. Referências consecutivas

Quando múltiplas referências estiverem adjacentes/agregadas, por exemplo:

```text
[32][15][18]
```

DEVEM ser verbalizadas como **um único conjunto natural de notas**, preservando todos os identificadores e sua ordem.

Preferir algo equivalente a:

```text
notas trinta e dois, quinze e dezoito
```

em vez de gerar frases independentes ou repetir desnecessariamente `nota` para cada referência.

Se a origem já possuir modos diferentes para:

- citar;
- resumir;
- ignorar;
- expandir;

preserve-os. Esta correção aplica-se **nos modos em que a referência for efetivamente pronunciada**.

---

# 9. Referências bíblicas

Referências bíblicas DEVEM possuir tratamento dedicado.

É **TERMINANTEMENTE PROIBIDO** interpretar:

```text
Mateus 3:22
```

como horário.

A leitura básica DEVE ser equivalente a:

```text
Mateus, três, vinte e dois
```

e o modo explícito/completo a:

```text
Mateus, capítulo três, versículo vinte e dois
```

A norma DEVE contemplar, conforme os formatos efetivamente suportados:

- livro;
- livros numerados;
- capítulo;
- versículo;
- intervalos;
- múltiplos versículos;
- múltiplos capítulos;
- abreviações reconhecidas;
- demais sintaxes bíblicas presentes na origem.

A classificação DEVE distinguir referência bíblica de horário real:

```text
Mateus 3:22 → referência bíblica
15:30       → pode continuar sendo horário
```

A normalização DEVE ocorrer antes da síntese.

---

# 10. Preservação das normas da origem

Além dos ajustes acima, extraia e preserve integralmente as regras reais de TTS e edição redacional existentes na origem, incluindo, quando aplicáveis:

- modos;
- precedências;
- limites;
- exceções;
- tratamento de citações;
- referências;
- Markdown/HTML;
- regras editoriais;
- contratos de transformação;
- validações;
- comportamento de build;
- demais requisitos normativos.

NÃO suponha que “edição redacional” autoriza reescrita livre.

NÃO copie bugs conhecidos como requisitos.

Quando este prompt corrigir deficiência da origem, **prevalece a correção**, preservando os demais contratos compatíveis.

---

# 11. Separação de responsabilidades

Avalie se TTS e edição redacional devem usar:

- capacidade comum;
- `SKILL`s distintas;
- `SubAgent`;
- `Scenario`;
- scripts compartilhados;
- combinação mínima desses mecanismos.

Prefira:

```text
regra comum → implementação comum
especialização → componente especializado
```

Evite:

- monólito desnecessário;
- duplicação;
- carregar regras de TTS em tarefas exclusivamente redacionais;
- carregar regras redacionais completas em normalização técnica simples.

Respeite a governança vigente de **roteamento cirúrgico e economia de tokens/contexto** do repositório construtor.

---

# 12. Testes obrigatórios

As TO-DOs DEVEM exigir testes positivos, negativos e regressivos para, no mínimo:

### Edição redacional
- preservação do estilo autoral;
- preservação da pontuação característica;
- correção sem mudança de voz/autoria;
- simplificação lexical sem perda de precisão;
- termo complexo com explicação na primeira ocorrência;
- ausência de repetição desnecessária da definição;
- reexplicação apenas quando justificável;
- simplificação sintática de período difícil;
- preservação de rigor acadêmico/conceitual;
- compreensão por leitor de baixa proficiência sem infantilização.

### TTS
- `vs`;
- `vs.`;
- variações de caixa;
- `x` como versus;
- `x` não equivalente a versus;
- romanos válidos;
- falsos positivos de romanos;
- citação literal;
- `<sup>` único;
- múltiplos `<sup>` consecutivos;
- referência bíblica simples;
- referência bíblica em modo completo;
- referência bíblica nunca interpretada como horário;
- horário real preservado;
- combinações desses recursos na mesma frase.

Use exemplos reais da origem quando forem úteis, sem hardcode específico.

---

# 13. Validação de TTS

Teste de regex ou transformação textual isolada NÃO é suficiente.

Quando tecnicamente viável, valide:

```text
texto original
→ normalização
→ texto efetivamente enviado ao sintetizador
→ pronúncia esperada
```

Quando houver infraestrutura apropriada, inclua validação auditiva/amostral.

---

# 14. Compatibilidade e regressão

É PROIBIDO corrigir os casos deste prompt causando regressão em:

- datas;
- horários reais;
- números comuns;
- unidades;
- abreviações;
- HTML/Markdown;
- notas;
- citações;
- conteúdo editorial;
- estilo autoral;
- demais modos de TTS;
- demais regras editoriais válidas.

A solução DEVE preservar comportamentos válidos da origem.

---

# 15. Rastreabilidade

Cada TO-DO DEVE distinguir de forma compacta:

- regra herdada da origem;
- correção/aperfeiçoamento introduzido por este prompt;
- decisão dependente da arquitetura real do destino;
- eventual regra da origem considerada obsoleta/incompatível, com justificativa verificável.

NÃO transforme caminhos ou detalhes de implementação da origem em contratos obrigatórios do destino sem necessidade.

---

# 16. Critérios absolutos de aceite

A tarefa somente estará concluída quando:

1. `D:\trampo\jeancarloem.com.blog\` permanecer integralmente inalterado;
2. RCF e normas relevantes de TTS/edição tiverem sido inspecionados;
3. uma ou mais TO-DOs autossuficientes tiverem sido produzidas;
4. o resultado tiver sido entregue em arquivo `.md` para download;
5. a solução respeitar a arquitetura/governança real do repositório construtor;
6. todas as capacidades forem `hookable`, mas funcionarem independentemente de hook;
7. regras válidas da origem forem preservadas sem regressão;
8. edição redacional preservar rigorosamente estilo, pontuação e identidade autoral;
9. linguagem resultante permanecer acessível inclusive a leitores de baixa proficiência;
10. termos complexos necessários forem explicados na primeira ocorrência de forma simples e direta;
11. complexidade sintática desnecessária for reduzida sem perda de rigor;
12. `vs`, `vs.` e `x` forem tratados contextualmente;
13. algarismos romanos forem corretamente identificados/verbalizados;
14. citações forem verbalizadas de forma natural quando aplicável;
15. `<sup>` pronunciado for explicitamente identificado como nota/referência;
16. múltiplos `<sup>` consecutivos forem agrupados naturalmente;
17. referências bíblicas nunca forem verbalizadas como horário;
18. modos curto/completo de leitura bíblica forem preservados/definidos quando aplicáveis;
19. conteúdo editorial original permanecer semanticamente preservado;
20. testes positivos, negativos e regressivos estiverem especificados;
21. nenhuma decisão material depender de contexto não registrado;
22. outra IA puder implementar as TO-DOs sem reconstruir esta análise.

## Saída

Entregue **somente um arquivo `.md` para download** contendo as TO-DOs finais.

Use a **menor quantidade de TO-DOs necessária**, sem perder coesão, autonomia, rastreabilidade, detalhes, nuances, rigor ou força normativa.
