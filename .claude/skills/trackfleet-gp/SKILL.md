---
name: trackfleet-gp
description: Use ao trabalhar nos entregáveis da disciplina de Gestão de Projetos (Engenharia da Computação, SETREM) para o projeto TrackFleet, seguindo o framework PMBOK 8ª Edição. Cobre contexto do projeto, convenções de documentos LaTeX e o padrão para produzir o próximo domínio de desempenho a cada aula.
---

# TrackFleet — Gestão de Projetos (PMBOK 8ª Edição)

## Contexto do projeto

**TrackFleet — Gestão de Rastreador de Automóveis** é o projeto de trabalho prático da disciplina de
Gestão de Projetos, do curso de Engenharia da Computação da SETREM, ministrada pelo Prof. Eduardo
Mildner. A cada aula, um domínio de desempenho do Guia PMBOK® 8ª Edição é estudado e, em seguida,
aplicado ao TrackFleet como exercício prático — produzindo os documentos que compõem a entrega
final da disciplina.

- **Integrantes / GPs:** Enzo Allebrand e Kerlon Ribeiro (co-gestão — dois GPs, sem hierarquia entre
  eles; discordâncias sobem ao patrocinador).
- **Problema:** falta de visibilidade em tempo real da frota e de dados objetivos para decisões de
  manutenção e uso dos veículos, agravada pelo custo elevado das soluções corporativas existentes.
- **Objetivo:** lançar uma plataforma de rastreamento e gestão de frotas acessível para pequenas
  transportadoras até o fim do semestre letivo.
- **Valor esperado:** redução de custos operacionais e de manutenção corretiva, melhora na segurança
  dos veículos e motoristas, decisões de gestão baseadas em dados reais.
- **Patrocinador:** Diretoria da transportadora parceira (papel fictício, definido pela dupla para
  fins do exercício).
- **Restrições:** prazo do semestre letivo · orçamento zero para hardware próprio (integração via API
  com rastreadores de terceiros) · LGPD (dados de localização e de motoristas).
- **Premissas:** as transportadoras-alvo já possuem ou têm acesso a rastreadores GPS compatíveis; os
  motoristas aceitam o monitoramento dos veículos da empresa.
- **Modelo de governança:** híbrido e leve — os dois GPs decidem o dia a dia por consenso; mudanças de
  objetivo, prazo ou escopo essencial, e qualquer impasse sem consenso entre os GPs, sobem ao
  patrocinador, que desempata e aprova.

Sempre que um documento novo precisar desses dados de contexto, use exatamente estes — não invente
valores diferentes para o mesmo campo em documentos diferentes.

## Estrutura do repositório

- `aulas/` — os slides de cada aula da disciplina, em PDF, na ordem do cronograma (ex.:
  `3. Escopo_PMBOK_8a_Edicao.pdf`). São a fonte teórica de cada domínio.
- `governanca/` — os entregáveis LaTeX do domínio **Governança**: `termo_de_abertura.tex`,
  `papeis_e_raci.tex`, `modelo_e_escalonamento.tex`, `metricas_e_sinal.tex`, `regras_e_registro.tex`.
- `escopo/` — o entregável LaTeX do domínio **Escopo** (aula 3, 20/08): `escopo.tex`, um único
  documento que reúne as três dimensões do domínio (Escopo do Produto, Escopo do Projeto e Qualidade)
  em partes separadas dentro do mesmo arquivo. Antes eram três `.tex` distintos (`produto.tex`,
  `projeto.tex`, `qualidade.tex`), fundidos em um só a pedido, com o escopo aprofundado (catálogo
  detalhado de alertas, catálogo de relatórios e a arquitetura/infraestrutura de tecnologia do
  produto).
- `cronograma/` (27/08) — `cronograma.tex`: atividades A1–A21 com dono único, dependências, PERT,
  caminho crítico com recursos (nivelado), calendário com feriados e buffer até 17/12.
- `financas/` (03/09) — `financas.tex` + `trackfleet_financas.xlsx` (a planilha recalcula tudo por
  fórmula; custos saem dos dias-pessoa do cronograma × R$ 300; contingência = VME da aba Riscos).
- `partes_interessadas/` (10/09) — registro, plano de engajamento, plano de comunicações.
- `recursos/` (17/09) — termo da equipe, matriz RACI, EAR, estimativa e histograma.
- `riscos/` (24/09) — plano de gerenciamento, registro de riscos, análise e respostas.
- `trabalho_pratico_01/` (01/10) — `documento_consolidado.tex`, que NÃO copia conteúdo: inclui os
  `.tex` de cada pasta via `docmute` (um capítulo por domínio). Ao mudar um domínio, edite o `.tex`
  da pasta dele e recompile também o consolidado.
- Domínio novo: uma pasta por domínio, um `.tex` por parte relevante, nomeado pelo conteúdo (não por
  número de slide), em minúsculas com underscore (ex.: `metricas_e_sinal.tex`). Para entrar no
  consolidado, acrescente um `\chapter` + `\subdocumento{...}` (vários arquivos) ou `\input{...}` (um).

Datas das aulas (mapa da aula 1): Governança 13/08, Escopo 20/08, Cronograma 27/08, Finanças 03/09,
Partes Interessadas 10/09, Recursos 17/09, Riscos 24/09, Trabalho Prático 01 01/10. O campo "Data" do
cabeçalho é sempre a data da aula do domínio.

**Números compartilhados entre domínios** (se mudar um, propague para todos e para o consolidado):
prazo 31/08–12/11 (51 dias úteis), buffer 24 dias úteis; BAC R$ 32.770, contingência R$ 3.970 (VME
líquido), gerenciamento R$ 1.639, orçamento R$ 34.409; donos por frente (Enzo: backend, alertas,
relatórios, infraestrutura; Kerlon: integração com o provedor, frontend, testes, LGPD). Referências
internas usam `\label`/`\ref` com prefixo do domínio (`esc:`, `cro:`, `fin:`, `ris:`); entre
documentos, cite a seção pelo nome, nunca pelo número.

## Padrão dos documentos

Todo documento de entrega segue o mesmo cabeçalho e tom dos já produzidos (ver `escopo/escopo.tex` e
os `governanca/*.tex` como referência de formatação LaTeX pronta para reuso):

```
DOCUMENTO DE [DOMÍNIO] DO PROJETO
TrackFleet — Gestão de Rastreador de Automóveis
Disciplina de Gerenciamento de Projetos · Framework PMBOK® 8ª Edição · Domínio: [Nome do Domínio]
Integrantes: Enzo Allebrand e Kerlon Ribeiro (dois GPs) · 4º semestre · Data: [data da aula]
```

No `.tex`, esse cabeçalho é gerado pela macro `\cabecalho{DOMÍNIO}{Domínio}{data}` e o subtítulo da
parte por `\parte{Título}` (separadores por `\separador`), definidos no preâmbulo de cada arquivo — é
isso que permite ao consolidado redefini-los. Copie o preâmbulo de um documento existente.

Cada seção do corpo do documento aplica um conceito da aula correspondente diretamente ao TrackFleet
(não repete a teoria genérica do slide — traduz o conceito em uma decisão concreta do projeto:
requisitos reais, exclusões reais, indicadores reais). Tabelas usam `booktabs` + `tabularx` (ou `xltabular` quando a tabela precisa quebrar página); listas
aninhadas (como a EAP) usam `enumitem`. Os arquivos são LaTeX autocontidos (preâmbulo completo em cada
`.tex`), compiláveis isoladamente com `pdflatex` ou no Overleaf.

**Visual sóbrio, de projeto acadêmico sério:** fonte Times New Roman (pacote `mathptmx`) e nenhuma cor
decorativa — sem títulos coloridos, sem paletas de destaque, sem blocos de cor. Cabeçalhos de seção
usam a formatação padrão do LaTeX (negrito preto). Essa regra vale para todo `.tex` novo do projeto.

**Sem negrito ou itálico no meio da frase.** `\textbf{}`/`\textit{}` só são usados em posições
estruturais: o subtítulo da seção logo abaixo do cabeçalho, cabeçalhos de tabela, e o rótulo inicial
de um item de lista (ex.: `\item \textbf{Objetivo:} lançar...`, `\item[\textbf{E1}] Monitoramento...`).
Nunca destacar uma palavra ou expressão no meio de uma frase corrida — nem para termos estrangeiros
(escreva ``scope creep'' ou "guardrails" entre aspas, sem itálico).

**Escaneável por tópicos.** Qualquer seção que descreva o que o produto é/faz precisa comunicar isso a
quem só ler os rótulos em negrito e os itens de lista, sem precisar ler parágrafos corridos — o
cliente do projeto deve entender o produto batendo o olho nos tópicos. Prefira listas com rótulo
(`O que é:`, `Para quem:`, `Como funciona:`) a parágrafos densos sempre que a seção define algo que o
leitor pode querer entender rapidamente.

## Ao começar um novo domínio

1. Leia o PDF da aula correspondente em `aulas/` para extrair os conceitos-chave daquele domínio de
   desempenho.
2. Releia o Termo de Abertura (`governanca/termo_de_abertura.tex`) e os demais documentos de
   Governança já existentes para manter consistência de dados de contexto (problema, objetivo,
   restrições, papéis).
3. Aplique cada conceito do domínio a uma decisão concreta do TrackFleet — nunca deixe uma seção só
   com teoria genérica.
4. Produza um ou mais arquivos `.tex`, um por sub-parte relevante do domínio (como foi feito para
   Governança e para Escopo), em uma pasta nova nomeada pelo domínio.
5. Responda sempre em português do Brasil, com ortografia completa (acentos e cedilhas corretos).
