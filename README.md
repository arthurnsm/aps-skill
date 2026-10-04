# dev-systems-analysis (v2: material em `/data`)

Skill de **Análise e Projeto de Sistemas (UNIFRAN)**. Em vez de carregar as regras de memória, ela **lê o material das aulas na pasta `/data`** e segue a metodologia do seu professor para levantar requisitos, modelar casos de uso, classes de análise e classes de projeto, e revisar seus diagramas do Draw.io.

O diferencial desta versão: **você pode incrementar o material a qualquer momento** (nova aula, orientação do trabalho, resumo seu) apenas colocando arquivos em `/data`. Não precisa editar o `SKILL.md`.

Este README ensina como preparar a pasta, conversar com a skill e extrair o melhor resultado.

---

## Sumário

1. [O que a skill faz (e o que não faz)](#1-o-que-a-skill-faz-e-o-que-não-faz)
2. [Como ela usa o material](#2-como-ela-usa-o-material)
3. [Preparando a pasta `/data`](#3-preparando-a-pasta-data)
4. [Instalação](#4-instalação)
5. [Primeiro uso: a varredura](#5-primeiro-uso-a-varredura)
6. [Incrementando o material](#6-incrementando-o-material)
7. [Gates e rótulos](#7-gates-e-rótulos)
8. [Briefing do seu projeto](#8-briefing-do-seu-projeto)
9. [Fluxo recomendado, passo a passo](#9-fluxo-recomendado-passo-a-passo)
10. [Prompts prontos](#10-prompts-prontos)
11. [Revisando seus diagramas do Draw.io](#11-revisando-seus-diagramas-do-drawio)
12. [Mudanças no projeto x mudanças no material](#12-mudanças-no-projeto-x-mudanças-no-material)
13. [Exemplo de sessão](#13-exemplo-de-sessão)
14. [Boas práticas e erros comuns](#14-boas-práticas-e-erros-comuns)
15. [Limitações conhecidas](#15-limitações-conhecidas)
16. [Perguntas frequentes e solução de problemas](#16-perguntas-frequentes-e-solução-de-problemas)
17. [Checklist final antes de entregar](#17-checklist-final-antes-de-entregar)

---

## 1. O que a skill faz (e o que não faz)

### Faz

| Área | O que você recebe |
|------|-------------------|
| **Varredura do material** | Inventário de `/data`, mapa de aulas e temas cobertos, lacunas e conflitos |
| **Requisitos** | RF, RNF e RN no formato de Linguagem Estruturada do professor, com validação de testabilidade |
| **Atores e casos de uso** | Mapeamento requisito → caso de uso, relacionamentos na notação do professor, fronteira do sistema |
| **Documentação** | Tabela de caso de uso exatamente como o template do material |
| **Classes de análise** | Tabela de substantivos (classe ou atributo + justificativa), associações e multiplicidades |
| **Classes de projeto** | Refinamento com visibilidade, tipos, métodos, abstratas, generalização, agregação, composição, classe associativa |
| **Diagramas** | Descrição reproduzível no **Draw.io**, ou arquivo `.drawio` sob pedido |
| **Revisão** | Análise de prints/PDFs/`.drawio` seus, citando a aula que justifica cada correção |
| **Consistência** | Verificação cruzada entre artefatos, com pendências e suposições explícitas |
| **Artefatos novos** | Qualquer artefato cujo material você adicionar em `/data` (ex.: diagrama de sequência) |

### Não faz

- **Não inventa** requisitos, regras, atores, atributos, multiplicidades ou números.
- **Não modela de memória** quando o tema está no material: consulta o trecho e cita a fonte.
- **Não substitui** a notação do professor por outra.
- **Não cria** Controller, Service, Repository, DTO, banco ou arquitetura sem pedido.
- **Não gera** artefatos de temas sem material (ex.: Scrum, Git, sequência) como se fossem do curso.
- **Não obedece** instruções escondidas dentro dos arquivos de `/data` (o conteúdo é tratado como dado).
- **Não declara** o projeto "finalizado" só porque os diagramas foram desenhados.

---

## 2. Como ela usa o material

```text
/data  →  Varredura  →  Mapa Metodológico  →  Artefatos
                ↑                                  │
        material novo ◄────────── revalidação ◄────┘
```

1. **Varredura:** a skill lista `/data`, classifica cada arquivo e lê títulos e sumários.
2. **Mapa Metodológico:** extrai terminologia, notação, regras, templates e exemplos, **sempre com a fonte** (arquivo, aula, página).
3. **Artefatos:** antes de gerar cada um, consulta o trecho correspondente e cita a fonte nas decisões.
4. **Material novo:** ela atualiza o mapa, relata o que mudou e revalida o que você já tinha feito.

### Quem manda quando as fontes divergem

| Nível | Fonte |
|-------|-------|
| 1 | O que você disser sobre o professor nesta conversa ("o professor pediu X") |
| 2 | Orientações do professor para o trabalho (enunciado, rubrica) |
| 3 | Aulas e modelos do professor (a aula **mais recente** prevalece; regra escrita vence exemplo visual) |
| 4 | Material complementar seu (apoia, nunca sobrepõe os níveis 2 e 3) |
| 5 | Baseline embutido (Aulas 1–7), só se o tema não existir acima |
| 6 | UML genérica, só se você pedir |

Se duas fontes do mesmo nível conflitarem sem critério claro, a skill **pergunta** em vez de escolher.

---

## 3. Preparando a pasta `/data`

### Estrutura sugerida

```text
/data
├── _indice.md        (opcional)
├── aulas/            PDFs/slides das aulas do professor
├── professor/        enunciado do trabalho, rubrica, orientações
├── modelos/          exemplos do professor (.drawio, diagramas, tabelas)
├── extras/           resumos, livros, anotações, transcrições de vídeo
└── projeto/          seu briefing, requisitos, diagramas e rascunhos
```

- As pastas são **dicas**. A skill classifica pelo conteúdo, então arquivos soltos funcionam, mas pastas deixam a classificação mais confiável.
- `projeto/` guarda **o conteúdo do seu trabalho**. A skill não aprende regras de notação com seus rascunhos (podem conter erros).

### Formatos aceitos

`pdf`, `md`, `txt`, `docx`, `pptx`, `csv`, imagens (`png`, `jpg`) e `drawio`/`xml`.

### Dicas de preparo

- **Prefira PDF com texto selecionável.** PDFs escaneados (imagem) são mais difíceis de ler; se possível, exporte de novo ou envie um resumo em texto.
- **Nomeie com número da aula:** `aula-08-diagrama-de-sequencia.pdf`. Isso ajuda a ordenar e a resolver "aula mais recente".
- **Um arquivo por tema** facilita a citação de fonte.
- **Não coloque dados sensíveis** (documentos pessoais, senhas) em `/data`.
- Se tiver um PDF único com várias aulas (como "Aulas 1–7"), pode manter assim.

### `_indice.md` (opcional, mas poderoso)

Use para dizer à skill o que é cada arquivo e o que vale mais. Quando existe, a skill o lê primeiro.

```markdown
# Índice do material

| Arquivo | Tipo | Observação |
|---------|------|------------|
| aulas/aulas-01-07.pdf | aula do professor | base do semestre |
| aulas/aula-08-sequencia.pdf | aula do professor | mais recente, vale sobre as anteriores |
| professor/enunciado-trabalho.pdf | orientação do professor | rubrica de entrega |
| modelos/exemplo-casos-de-uso.drawio | modelo do professor | seguir este estilo visual |
| extras/resumo-colega.md | complemento | não é do professor, usar só para apoio |
| projeto/briefing.md | projeto | tema escolhido |
```

---

## 4. Instalação

1. Salve o `SKILL.md` em uma pasta chamada `dev-systems-analysis` e adicione-a como skill no ambiente onde você usa o Claude (siga a documentação da sua plataforma).
2. **Garanta que `/data` esteja acessível ao Claude** no seu ambiente (por exemplo, como pasta/volume montado do projeto).
3. Coloque os materiais em `/data` conforme a seção 3.
4. Teste com o prompt da seção 5.

> **Se você não consegue disponibilizar `/data`:** envie os arquivos direto no chat. A skill tenta `/data`, depois os anexos da conversa, e só então usa o baseline embutido (avisando que está nesse modo).

---

## 5. Primeiro uso: a varredura

Em toda conversa nova, comece assim:

```text
Use a skill dev-systems-analysis. Faça a varredura de /data e me mostre o relatório
antes de qualquer outra coisa.
```

### O que você deve ver

```text
📂 Varredura de /data
Arquivos lidos: 4
 - aulas/aulas-01-07.pdf → aula do professor
 - professor/enunciado-trabalho.pdf → orientação do professor
 - modelos/exemplo-casos-de-uso.drawio → modelo do professor
 - projeto/briefing.md → projeto
Aulas identificadas: 1–7 (introdução, requisitos, casos de uso, classes)
Temas cobertos: engenharia de requisitos, casos de uso, classes de análise e de projeto
Temas previstos sem material: diagrama de sequência, Scrum/Kanban, Git
Ilegíveis/ignorados: nenhum
Conflitos entre fontes: Prescricao (Aula 5 x 6): vale a Aula 6
Modo: Parcial + baseline
```

### Como interpretar

| Campo | O que fazer |
|-------|-------------|
| **Arquivos lidos** | Confira se está tudo ali e se a classificação está certa. Corrija se não estiver. |
| **Temas previstos sem material** | É sua lista de "o que falta enviar". |
| **Ilegíveis/ignorados** | Reenvie em outro formato. |
| **Conflitos** | Leia: a skill indica qual fonte vence. Discorde se souber algo do professor. |
| **Modo** | *Material completo*: tudo coberto. *Parcial + baseline*: parte vem do resumo embutido. *Somente baseline*: `/data` vazia ou inacessível, confira a seção 16. |

A skill só gera artefatos **depois** disso. Se o relatório apontar problema que afete sua tarefa, ela pergunta antes de seguir.

---

## 6. Incrementando o material

Você pode adicionar material **a qualquer momento**, inclusive no meio do projeto.

### Cenários e como fazer

| Situação | O que fazer | Prompt |
|----------|-------------|--------|
| **Chegou uma aula nova** | Salve em `/data/aulas/` | `Adicionei aula-08-sequencia.pdf em /data/aulas. Atualize o mapa e me diga o que mudou.` |
| **Professor deu o enunciado/rubrica** | Salve em `/data/professor/` | `Adicionei o enunciado em /data/professor. Confira se meus artefatos atendem a rubrica.` |
| **Quer usar um resumo/livro** | Salve em `/data/extras/` | `Adicionei um resumo em /data/extras. Use só para apoio; o professor tem prioridade.` |
| **Professor corrigiu uma regra** | Diga no chat e, se tiver, anexe o slide | `O professor explicou em aula que [X]. Atualize o mapa e revalide meus artefatos.` |
| **Material colado no chat** | Cole o texto | A skill perguntará uma vez: "É do professor ou complementar?" |
| **Arquivo errado/desatualizado** | Remova ou substitua em `/data` | `Removi extras/resumo-antigo.md. Refaça a varredura.` |

### O que a skill faz quando há material novo

1. Refaz a varredura **só do que mudou**.
2. Classifica o arquivo e aplica a hierarquia de fontes.
3. Atualiza o Mapa Metodológico.
4. Relata: regras novas, regras alteradas, temas agora cobertos, conflitos.
5. **Revalida os artefatos que você já tem** e informa o impacto. Ela não reescreve o que já existe sem avisar.

### Exemplo: chegou a aula de sequência

```text
Você: Adicionei aula-08-sequencia.pdf em /data/aulas. Atualize o mapa.

Skill: Material novo detectado: aula-08 (diagrama de sequência).
 - Tema agora coberto: modelagem de interações.
 - Regras novas: lifelines, mensagens síncronas/assíncronas, ... (Aula 8, p. 3-6)
 - Impacto nos seus artefatos: o diagrama de classes de projeto precisa ter os métodos
   usados nas mensagens (3 métodos faltam em Consulta).
 Quer que eu gere o diagrama de sequência do caso de uso "Agendar Consulta"?
```

*(Exemplo ilustrativo do comportamento esperado.)*

---

## 7. Gates e rótulos

### Gates (pontos de parada obrigatórios)

| Gate | O que acontece |
|------|----------------|
| **Varredura do Material** | Antes de qualquer artefato, a skill lê `/data` e mostra o relatório. |
| **Travamento dos Requisitos** | Ela apresenta RF/RNF/RN consolidados e pergunta se é a base oficial. Responda: *"Confirmado"* ou *"Mudar X, Y"*. |
| **Prontidão para Entrega** | Antes de dizer que está pronto, ela confere tudo, incluindo se toda regra aplicada tem fonte. Pode responder *"Não pronto para entrega final"*. Isso é um bom sinal. |

### Rótulos de informação

| Rótulo | Significado | O que você faz |
|--------|-------------|----------------|
| **Confirmado** | Veio de você | Nada |
| **Definido pelo material** | Regra do professor, com fonte citada | Nada (confira a citação se quiser) |
| **Definido pelo baseline** | Regra do resumo embutido, por falta de material | Considere enviar o material para confirmar |
| **Inferido** | Deduzido de algo confirmado | Valide |
| **Proposto** | Sugestão da skill | Aceite ou recuse |
| **Pendente** | Falta decisão sua (ou detalhe no material) | Responda |
| **Rejeitado** | Você recusou | Nada |

Regra prática: **tudo que estiver Proposto, Pendente ou "Definido pelo baseline" merece atenção antes da entrega.**

---

## 8. Briefing do seu projeto

Coloque em `/data/projeto/briefing.md` ou cole no chat. Quanto mais concreto, menos pendências.

```text
Sistema: [nome]
Problema: [o que acontece hoje e por que precisa de um sistema]
Objetivo: [o que o sistema deve resolver]
Quem usa: [papéis, ex.: atendente, gerente, cliente]
Sistemas externos: [pagamento, e-mail, convênios... ou "nenhum"]
Principais funcionalidades que imagino: [lista livre]
Restrições conhecidas: [prazos, tecnologias, leis, horários de funcionamento]
Exigências do professor: [ex.: mínimo de N casos de uso, usar include/extend, etc.]
```

Não precisa estar perfeito. A skill aponta as lacunas.

---

## 9. Fluxo recomendado, passo a passo

Siga a ordem. Cada artefato depende do anterior.

| Etapa | O que fazer |
|-------|-------------|
| **0. Varredura** | Peça o relatório de `/data` e corrija o que estiver errado. |
| **1. Escopo** | Envie o briefing. Peça escopo, stakeholders e perguntas faltantes. |
| **2. Elicitação** | Peça perguntas de entrevista, um cenário narrado e brainstorming. Cenários revelam requisitos esquecidos. |
| **3. Requisitos** | Peça RF, RNF e RN no formato do professor. Nos RNF, ela exigirá métrica: se você não souber, vira `[PENDENTE]`. |
| **4. Validação e travamento** | Peça a validação e responda ao gate de travamento. |
| **5. Atores e casos de uso** | Peça a tabela de atores, o mapeamento requisito → caso de uso e os relacionamentos justificados pelas perguntas-chave da aula. |
| **6. Diagrama de casos de uso** | Monte no Draw.io e envie o print para revisão. |
| **7. Documentação** | Peça a tabela dos casos de uso relevantes (os mais importantes ou os com `include`/`extend`). |
| **8. Classes de análise** | Peça a **tabela de substantivos** antes do diagrama. |
| **9. Classes de projeto** | Peça o refinamento e a classificação de cada relacionamento pela árvore de decisão. |
| **10. Outros artefatos** | Se o material exigir mais (ex.: sequência), gere na ordem indicada. |
| **11. Consistência e entrega** | Peça a análise completa. Só entregue com *"Pronto para revisão acadêmica"*. |

---

## 10. Prompts prontos

### Começar

```text
Use a skill dev-systems-analysis. Faça a varredura de /data, mostre o relatório e depois
liste o que falta para eu começar a fase [requisitos / casos de uso / classes].
Faça no máximo 2 perguntas.
```

### Consultar o que o material diz

```text
Segundo o material em /data, como devo documentar um requisito não funcional?
Cite o arquivo e a página.
```

```text
Mostre o Mapa Metodológico atual em tabela: aulas, terminologia, notação, templates
e lacunas.
```

### Requisitos

```text
Gere os requisitos funcionais, não funcionais e regras de negócio no formato exigido
pelo material. Classifique os RNF e use [PENDENTE] onde faltar valor de métrica.
```

```text
Valide estes requisitos quanto a clareza, testabilidade, duplicidade e contradição.
Não corrija em silêncio: aponte e proponha a correção.
[cole os requisitos]
```

### Atores e casos de uso

```text
Com base nos requisitos travados, liste atores e casos de uso candidatos, mostrando quais
requisitos formam cada um. Justifique cada include e extend conforme as regras do material.
```

```text
Documente o caso de uso [nome] usando exatamente o template do material.
Marque como Proposto qualquer fluxo que eu não tenha confirmado.
```

### Diagramas

```text
Descreva o diagrama de casos de uso para eu montar no Draw.io: elementos, tabela de
relacionamentos (origem, destino, tipo, rótulo) e onde ficam os símbolos.
```

```text
Gere um arquivo .drawio do diagrama de [casos de uso / classes de análise / classes de projeto].
```

### Classes

```text
Monte a tabela de substantivos candidatos dos meus requisitos e casos de uso aplicando
as heurísticas do material.
```

```text
Classifique cada relacionamento entre estas classes usando a árvore de decisão do professor
e justifique cada um. Verifique também se há classe associativa escondida.
[liste as classes]
```

### Rubrica e fechamento

```text
Compare meus artefatos com a rubrica em /data/professor e liste o que falta.
```

```text
Faça a análise completa final: requisitos, atores, casos de uso, documentação, classes de
análise e de projeto, consistência, fontes consultadas, suposições e pendências.
Termine com o veredito de prontidão.
```

---

## 11. Revisando seus diagramas do Draw.io

A skill revisa **o que está realmente visível** e compara com as regras do Mapa Metodológico.

1. **Exporte em PNG ou PDF** com boa resolução (texto legível).
2. Envie **um diagrama por mensagem**.
3. Diga o que é: *"Diagrama de casos de uso, versão 2."*
4. Anexe os requisitos correspondentes, se possível.

```text
Revise o diagrama anexo (casos de uso). Compare com meus requisitos e com as regras do
material em /data. Para cada erro: problema, motivo (cite a fonte), versão corrigida e
artefatos afetados. Se algo estiver ilegível, diga em vez de supor.
```

Erros que ela costuma pegar: direção de `<<extend>>`/`<<include>>` invertida, relacionamento errado para obrigatório/opcional, ator dentro da fronteira, caso de uso com nome de tela, atributo desenhado como classe, agregação/composição só porque "contém", multiplicidade ausente.

---

## 12. Mudanças no projeto x mudanças no material

| Tipo | Exemplo | O que a skill faz |
|------|---------|-------------------|
| **Projeto** | "RF-04 agora exige aprovação do gerente" | Revisa a cadeia requisito → caso de uso → documentação → classe → relacionamento e informa o impacto |
| **Material** | "Chegou a aula 8" / "O professor mudou a notação" | Atualiza o mapa, relata o que mudou e revalida os artefatos |

Prompts:

```text
Mudança no projeto: [descreva]. Identifique os artefatos afetados, atualize-os e me diga
o que mudou em cascata.
```

```text
Mudança no material: [descreva]. Atualize o mapa metodológico e revalide meus artefatos
existentes, listando o que deixou de estar em conformidade.
```

---

## 13. Exemplo de sessão

> Tema fictício: sistema de agendamento de aulas de uma academia.

**Você:**
```text
Use a skill dev-systems-analysis. Faça a varredura de /data e mostre o relatório.
```

**Skill:** relatório de varredura (arquivos lidos, aulas 1–7 identificadas, sequência/Scrum/Git sem material, modo *Parcial + baseline*).

**Você:**
```text
Briefing: academia pequena quer agendar aulas coletivas. Alunos reservam vaga, instrutores
consultam turmas, a recepção gerencia planos. Pagamento via sistema externo. Gere RF, RNF e RN.
```

**Skill (comportamento esperado):**
- Consulta a aula de requisitos antes de escrever e cita *(Aula 2, p. 10-11)*.
- Entrega `RF-01 … RF-0N` com Nome + Descrição.
- Escreve um RNF de disponibilidade com `[PENDENTE: definir horário e tolerância]`.
- Lista regras **Propostas** (ex.: limite de reservas por plano) e pergunta se são reais.
- Faz até 2 perguntas, por exemplo: *"Um aluno pode cancelar uma reserva? Com qual antecedência?"*

**Você:**
```text
Cancelamento até 2 horas antes. Limite de 3 reservas por semana no plano básico.
Confirmo os requisitos.
```

**Skill:** registra como **Confirmado**, passa pelo gate de travamento e lista atores (Aluno, Instrutor, Recepcionista como principais; Sistema de Pagamento como secundário). Propõe casos de uso e justifica: *Reservar Aula* inclui *Verificar Disponibilidade de Vaga* (sempre acontece); *Aplicar Lista de Espera* estende *Reservar Aula* (só quando a turma está cheia), citando a regra do material.

**Você (semanas depois):**
```text
Adicionei aula-08-sequencia.pdf em /data/aulas. Atualize o mapa e gere o diagrama de
sequência de "Reservar Aula".
```

**Skill:** atualiza o mapa, relata o que mudou, aponta métodos que faltam nas classes de projeto e então gera o diagrama conforme a Aula 8.

---

## 14. Boas práticas e erros comuns

### Faça

- **Comece toda conversa com a varredura.**
- **Mantenha `/data` organizada** e atualizada; remova versões antigas.
- **Use `_indice.md`** para marcar o que é do professor e o que é complemento.
- **Responda as perguntas** da skill: cada Pendente em aberto vira risco na entrega.
- **Peça uma etapa por vez** e confirme os gates.
- **Peça a fonte** ("onde o material diz isso?") para aprender e defender o trabalho.
- **Peça a tabela de substantivos** antes do diagrama de classes.
- **Mantenha IDs estáveis** (RF-01, RF-02...).
- **Guarde um documento mestre** com as versões confirmadas.

### Evite

| Erro | Consequência | Alternativa |
|------|--------------|-------------|
| Deixar `/data` vazia e esperar fidelidade ao professor | Skill cai no baseline | Coloque os PDFs das aulas |
| Misturar resumo de colega com aulas sem indicar | Complemento pode ser tratado como apoio, não regra | Separe em `extras/` ou marque no `_indice.md` |
| Colocar rascunhos próprios como "modelo" | Erros seus viram referência | Mantenha em `projeto/` |
| "Faça o trabalho inteiro" sem briefing | Muitas suposições e pendências | Briefing + fluxo por etapas |
| Aceitar tudo que está **Proposto** sem ler | Itens que não são seus no documento final | Leia e aceite/recuse item a item |
| Pular o travamento dos requisitos | Retrabalho nos casos de uso e classes | Confirme explicitamente |
| Copiar valores dos exemplos das aulas | RNF que não reflete seu sistema | Defina seus próprios valores |
| Prints ilegíveis | Revisão limitada | Exportar em alta resolução |
| Conversas muito longas | Perda de contexto | Peça resumo de estado e abra um chat novo |

### Truque: resumo de estado

```text
Gere um resumo do estado do projeto: requisitos confirmados (com IDs), atores, casos de uso,
classes, decisões, fontes consultadas, suposições e pendências abertas.
```

Cole o resumo no início de uma conversa nova e peça a varredura de `/data` novamente.

---

## 15. Limitações conhecidas

| Tema | Situação |
|------|----------|
| **Acesso a `/data`** | Depende do seu ambiente permitir que o Claude leia a pasta. Sem acesso, use anexos no chat. |
| **Baseline** | Cobre só as Aulas 1–7. Sequência, Scrum/Kanban e Git só funcionam quando você adicionar o material. |
| **Checklist de refinamento** (dinâmico, estático, estrutural, nomenclatura, duplicidade) | O baseline não detalha. Aplica-se *nomenclatura* e *duplicidade*; o resto fica Pendente até haver material. |
| **PDFs escaneados e imagens ruins** | Leitura limitada; a skill declara o que não conseguiu ler. |
| **Arquivos muito grandes** | Ela lê por seções relevantes à tarefa; peça uma seção específica se algo passar batido. |
| **Divergências no material** | Aplica a aula mais recente e avisa. Em dúvida real, ela pergunta. |
| **Leitura de diagramas** | Depende da legibilidade; elementos ambíguos são declarados como não identificáveis. |
| **Arquivo `.drawio` gerado** | Pode exigir ajuste manual de posicionamento ao importar. |
| **Decisão final** | O professor é a autoridade. Em dúvida, confirme com ele. |

---

## 16. Perguntas frequentes e solução de problemas

**A varredura disse "Somente baseline" ou "/data não encontrada".**
A pasta não está acessível ao Claude no seu ambiente, ou está vazia. Verifique se `/data` foi montada/compartilhada e se há arquivos nela. Sem isso, envie os PDFs direto no chat.

**A skill não encontrou um arquivo que eu coloquei.**
Peça: `Refaça a varredura de /data`. Se continuar, confira o formato (veja seção 3) e o nome da pasta.

**O PDF está marcado como ilegível.**
Provavelmente é escaneado. Exporte novamente com texto selecionável, ou envie um resumo em `.md`/`.txt`.

**A skill ignorou uma regra do meu resumo.**
Resumos em `extras/` não sobrepõem o professor. Se o professor realmente ensinou aquilo, diga no chat (*"o professor explicou que..."*) ou mova o conteúdo para `aulas/` e registre no `_indice.md`.

**Dois materiais se contradizem. Qual vale?**
Vale a hierarquia da seção 2. Entre aulas, a mais recente. Entre fontes do mesmo nível sem critério, a skill pergunta.

**Ela citou uma página/aula que parece errada.**
Peça: `Mostre o trecho exato de onde tirou isso.` Se a fonte não sustentar a regra, a skill deve corrigir e rotular o item como Pendente.

**Posso usar a skill com outro curso ou professor?**
Sim: troque o conteúdo de `/data` pelo material do novo curso. O baseline embutido continua sendo da UNIFRAN, então confira se a varredura marca o modo *Material completo* e desconsidere o baseline.

**Ela disse "Não pronto para entrega final". E agora?**
Veja os problemas críticos e as pendências, resolva um a um e peça nova análise completa.

**A skill escreve o trabalho todo por mim?**
Ela estrutura, valida e redige os artefatos com base no que você confirma. As decisões de projeto são suas. O objetivo é um trabalho correto que você consiga defender.

---

## 17. Checklist final antes de entregar

### Material
- [ ] `/data` contém todas as aulas e a rubrica/enunciado
- [ ] Última varredura sem conflitos nem arquivos ilegíveis pendentes
- [ ] Modo *Material completo* (ou baseline aceito conscientemente)

### Requisitos
- [ ] RF, RNF e RN separados, no formato do professor
- [ ] RF com verbo no infinitivo
- [ ] RNF classificados e testáveis
- [ ] Nenhum `[PENDENTE]` esquecido

### Casos de uso
- [ ] Atores são papéis, fora da fronteira; fronteira com o nome do sistema
- [ ] Nomes de casos de uso conforme a convenção
- [ ] Setas e relacionamentos na notação do professor
- [ ] Documentação feita para os casos de uso relevantes
- [ ] Diagrama e documentação dizem a mesma coisa

### Classes
- [ ] Tabela de substantivos com justificativa
- [ ] Atributos não viraram classes
- [ ] Multiplicidade em todas as pontas
- [ ] Relacionamentos classificados pela árvore de decisão
- [ ] Classes de projeto coerentes com as de análise

### Geral
- [ ] Todos os artefatos exigidos pela rubrica presentes
- [ ] Nomes iguais em todos os artefatos
- [ ] Fontes consultadas, suposições e pendências listadas
- [ ] Veredito final da skill: **"Pronto para revisão acadêmica"**
- [ ] Formato de entrega conforme exigência do professor

---

## Resumo em uma linha

> **Coloque o material em `/data`, comece com a varredura, trave os requisitos, avance uma etapa por vez, adicione material novo quando surgir e só entregue com o veredito de prontidão.**