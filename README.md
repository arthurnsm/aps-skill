# DEV-SYSTEMS-ANALYSIS

Skill para auxiliar na **Análise e Projeto de Sistemas**, utilizando as aulas e materiais fornecidos como base para orientar a elaboração de requisitos, casos de uso, classes e diagramas.

A skill é especialmente adequada para trabalhos acadêmicos que precisam seguir uma **metodologia específica ensinada em aula**, evitando que regras genéricas de UML substituam o que foi apresentado pelo professor.

---

## Estrutura

A skill utiliza apenas duas pastas:

```text
/data
├── references/
└── assets/
```

### `references/`

Coloque aqui as aulas e demais materiais de referência:

* PDFs das aulas;
* slides;
* apostilas;
* materiais complementares;
* documentos fornecidos pelo professor;
* referências utilizadas na disciplina;
* enunciados e orientações.

Não é necessário separar os arquivos por tipo.

Exemplo:

```text
references/
├── Aula 01.pdf
├── Aula 02.pdf
├── Aula 03.pdf
├── Análise de Requisitos.pdf
├── UML.pdf
└── Trabalho.pdf
```

### `assets/`

Utilize para materiais visuais e modelos:

* exemplos de casos de uso;
* diagramas;
* modelos de classes;
* arquivos `.drawio`;
* imagens;
* templates;
* outros exemplos visuais.

Exemplo:

```text
assets/
├── caso-de-uso-exemplo.png
├── diagrama-classes.png
├── modelo-caso-de-uso.drawio
└── exemplo-diagrama.pdf
```

---

# Como a skill funciona

A skill consulta os materiais disponíveis para entender **como a disciplina aborda o assunto** antes de auxiliar na elaboração do trabalho.

Por exemplo, em vez de simplesmente criar um diagrama de classes seguindo uma convenção genérica de UML, ela pode verificar nas aulas:

* quais elementos são utilizados;
* quais nomes são adotados;
* como os relacionamentos são representados;
* como os casos de uso são documentados;
* quais critérios foram apresentados pelo professor.

Os arquivos em `references/` servem principalmente para **entender a metodologia**.

Os arquivos em `assets/` servem principalmente como **exemplos e referências visuais**.

---

# Como começar

Depois de adicionar as aulas e materiais, peça para a skill analisar o conteúdo.

### Exemplo

```text
@dev-systems-analysis analise todas as referências disponíveis e me explique quais são as principais regras da metodologia ensinada para este trabalho.
```

A partir disso, você pode começar o desenvolvimento do projeto.

---

# Fluxo recomendado

Um trabalho normalmente pode ser desenvolvido nesta ordem:

```text
Entender o projeto
      ↓
Levantar requisitos
      ↓
Validar requisitos
      ↓
Definir casos de uso
      ↓
Documentar casos de uso
      ↓
Modelar classes
      ↓
Criar/validar diagramas
      ↓
Revisar o trabalho
```

Não é necessário executar todos os passos de uma única vez. A skill pode acompanhar o projeto progressivamente.

---

# 1. Entender o projeto

Comece fornecendo o enunciado ou explicando a ideia do sistema.

### Exemplo

```text
@dev-systems-analysis
Vou desenvolver um sistema para uma clínica veterinária.
O sistema deverá permitir cadastrar animais, tutores e consultas.

Antes de criar qualquer requisito, analise as referências e me diga quais informações você precisa levantar para entender corretamente o sistema.
```

A skill pode identificar informações que ainda precisam ser definidas antes da modelagem.

---

# 2. Levantar requisitos

Depois de explicar o funcionamento do sistema:

```text
@dev-systems-analysis
Com base no que já definimos sobre o sistema, faça o levantamento inicial dos requisitos funcionais, não funcionais e regras de negócio.
```

Você também pode fornecer informações aos poucos:

```text
@dev-systems-analysis
Adicione aos requisitos que o veterinário pode consultar o histórico médico de cada animal.
Verifique se isso altera algum requisito existente.
```

---

# 3. Revisar requisitos

Antes de avançar para os casos de uso:

```text
@dev-systems-analysis
Revise os requisitos atuais seguindo a metodologia das referências.
Procure ambiguidades, duplicidades, inconsistências e informações que ainda precisam ser definidas.
```

Também é possível pedir uma análise específica:

```text
@dev-systems-analysis
Verifique se todos os requisitos funcionais estão suficientemente claros para serem transformados em casos de uso.
```

---

# 4. Fixar os requisitos

Quando estiver satisfeito com o levantamento:

```text
@dev-systems-analysis
Considere os requisitos atuais como a versão aprovada do sistema e utilize-os como base para os próximos artefatos.
```

A partir desse ponto, novos elementos devem ser comparados com os requisitos definidos.

---

# 5. Criar atores e casos de uso

Depois dos requisitos:

```text
@dev-systems-analysis
Com base nos requisitos aprovados, identifique os atores e proponha os casos de uso do sistema.
Explique a relação entre cada caso de uso e os requisitos correspondentes.
```

Para revisar:

```text
@dev-systems-analysis
Revise os atores e casos de uso atuais e verifique se existe algum requisito sem cobertura ou algum caso de uso sem justificativa.
```

---

# 6. Documentar casos de uso

Quando os casos de uso estiverem definidos:

```text
@dev-systems-analysis
Documente o caso de uso "Realizar Consulta" seguindo o modelo utilizado nas referências.
```

Ou vários:

```text
@dev-systems-analysis
Documente todos os casos de uso definidos anteriormente utilizando o padrão apresentado nas aulas.
```

Se houver um modelo específico nos `assets/`, a skill pode utilizá-lo como referência:

```text
@dev-systems-analysis
Use os exemplos disponíveis em assets como referência visual e siga a metodologia das referências para documentar os casos de uso.
```

---

# 7. Modelar classes

Para começar a análise das classes:

```text
@dev-systems-analysis
A partir dos requisitos e casos de uso aprovados, identifique as classes de análise do sistema.
Explique a justificativa de cada classe.
```

Depois:

```text
@dev-systems-analysis
Revise as classes de análise e verifique se elas estão coerentes com os requisitos e casos de uso.
```

Para classes de projeto:

```text
@dev-systems-analysis
Agora transforme o modelo de análise em um modelo de classes de projeto seguindo a metodologia apresentada nas aulas.
```

---

# 8. Analisar diagramas

Você pode anexar um diagrama e pedir uma revisão.

```text
@dev-systems-analysis
Analise o diagrama de classes anexado.
Compare-o com a metodologia das referências e com os requisitos e classes que já definimos.
Aponte os problemas e explique como corrigir cada um.
```

Para um diagrama de casos de uso:

```text
@dev-systems-analysis
Analise o diagrama de casos de uso anexado.
Verifique atores, casos de uso e relacionamentos conforme as aulas.
```

A análise pode considerar tanto o conteúdo do diagrama quanto os exemplos existentes em `assets/`.

---

# 9. Comparar com um modelo

Se você possui um exemplo fornecido pelo professor:

```text
@dev-systems-analysis
Compare meu diagrama anexado com o modelo disponível em assets.
Identifique diferenças relevantes e diga quais delas representam erros segundo a metodologia das aulas.
```

Isso permite diferenciar uma **diferença visual** de uma **diferença metodológica**.

---

# 10. Verificar o trabalho completo

Quando todos os artefatos estiverem prontos:

```text
@dev-systems-analysis
Faça uma revisão completa do meu trabalho.
Verifique requisitos, casos de uso, documentação, classes e diagramas.
Procure inconsistências entre os artefatos e indique tudo que precisa ser corrigido antes da entrega.
```

Para uma revisão focada na metodologia:

```text
@dev-systems-analysis
Faça uma auditoria final considerando principalmente as regras apresentadas nas referências e os modelos disponíveis em assets.
```

---

# Consultar a metodologia

Você não precisa saber em qual aula determinada informação está.

Basta perguntar:

```text
@dev-systems-analysis
Como as aulas definem um requisito funcional?
```

```text
@dev-systems-analysis
Qual é a forma de representar esse relacionamento de classes segundo as aulas?
```

```text
@dev-systems-analysis
O que as referências dizem sobre include e extend?
```

```text
@dev-systems-analysis
Como deve ser documentado um caso de uso segundo o material?
```

A skill utiliza os materiais disponíveis para responder conforme a metodologia encontrada.

---

# Atualizar as referências

Novas aulas ou materiais podem ser adicionados a qualquer momento.

Por exemplo:

```text
/data/references/
├── Aula 01.pdf
├── Aula 02.pdf
├── Aula 03.pdf
└── Aula 04.pdf
```

Depois de adicionar o novo material:

```text
@dev-systems-analysis
Adicionei uma nova aula em references.
Analise o material e me diga se ele acrescenta ou altera alguma regra relevante para o trabalho que estamos desenvolvendo.
```

Não é necessário reorganizar os arquivos.

---

# Usar imagens e modelos

Você pode adicionar modelos visuais em `assets/` e pedir que a skill os utilize como referência.

### Exemplo

```text
@dev-systems-analysis
Analise os exemplos de diagramas disponíveis em assets e identifique o padrão utilizado para os diagramas de classes.
```

Ou:

```text
@dev-systems-analysis
Utilize os modelos disponíveis em assets como referência para revisar o diagrama que anexei.
```

Os modelos servem para ajudar na comparação visual e metodológica, mas a regra ensinada nas referências continua sendo a principal fonte para determinar o que está correto.

---

# Trabalhar de forma incremental

Não é necessário fornecer todo o projeto de uma vez.

Você pode trabalhar em pequenas etapas:

```text
@dev-systems-analysis
Vamos começar somente pelos requisitos.
```

Depois:

```text
@dev-systems-analysis
Agora vamos validar os requisitos.
```

Depois:

```text
@dev-systems-analysis
Com os requisitos aprovados, vamos criar os casos de uso.
```

E posteriormente:

```text
@dev-systems-analysis
Agora vamos trabalhar nas classes.
```

A skill pode utilizar o contexto já estabelecido para manter a consistência entre as etapas.

---

# Quando houver dúvida ou informação faltando

A skill deve ser utilizada também para descobrir o que ainda precisa ser definido.

Exemplo:

```text
@dev-systems-analysis
Analise o estado atual do projeto e me diga quais informações ainda estão faltando para podermos criar os casos de uso corretamente.
```

Ou:

```text
@dev-systems-analysis
Existe alguma decisão importante sobre o sistema que ainda não foi definida e que pode afetar o diagrama de classes?
```

Isso evita preencher lacunas arbitrariamente.

---

# Comandos rápidos

| Objetivo                 | Exemplo                                                             |
| ------------------------ | ------------------------------------------------------------------- |
| Analisar referências     | `@dev-systems-analysis analise as referências disponíveis`          |
| Consultar metodologia    | `@dev-systems-analysis como as aulas tratam requisitos funcionais?` |
| Levantar requisitos      | `@dev-systems-analysis faça o levantamento dos requisitos`          |
| Validar requisitos       | `@dev-systems-analysis revise os requisitos atuais`                 |
| Definir atores           | `@dev-systems-analysis identifique os atores`                       |
| Criar casos de uso       | `@dev-systems-analysis crie os casos de uso`                        |
| Documentar UC            | `@dev-systems-analysis documente o caso de uso X`                   |
| Criar classes            | `@dev-systems-analysis modele as classes de análise`                |
| Criar classes de projeto | `@dev-systems-analysis modele as classes de projeto`                |
| Auditar diagrama         | `@dev-systems-analysis analise o diagrama anexado`                  |
| Comparar modelos         | `@dev-systems-analysis compare com os exemplos de assets`           |
| Revisar projeto          | `@dev-systems-analysis faça uma revisão completa`                   |
| Atualizar referências    | `@dev-systems-analysis analise o novo material`                     |

---

# Resumo

A utilização da skill pode ser reduzida a três elementos:

### 1. Coloque o conhecimento da disciplina em:

```text
references/
```

### 2. Coloque modelos e exemplos visuais em:

```text
assets/
```

### 3. Chame a skill conforme a etapa do trabalho:

```text
@dev-systems-analysis
[descreva o que você precisa fazer]
```

A partir daí, a skill utiliza as referências disponíveis para auxiliar na construção, revisão e validação dos artefatos do projeto, mantendo a metodologia da disciplina como principal referência.
