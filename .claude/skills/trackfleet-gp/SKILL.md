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
- `o que temos/` — os entregáveis já produzidos para o domínio **Governança** (aula 2, 13/08),
  divididos em 5 PDFs numerados (`1.Termo_de_Abertura.pdf` … `5.Regras_e_Registro.pdf`), formando
  juntos o "Documento de Governança do Projeto".
- `escopo/` — os entregáveis LaTeX do domínio **Escopo** (aula 3, 20/08): `produto.tex`,
  `projeto.tex`, `qualidade.tex` (Escopo do Produto, Escopo do Projeto e Qualidade, as três dimensões
  do domínio, cada uma em arquivo separado).
- Para os próximos domínios (Cronograma, Finanças, Partes Interessadas, Recursos, Riscos), crie uma
  pasta nova por domínio, com o mesmo padrão: um `.tex` por parte relevante do domínio, nomeado pelo
  conteúdo (não por número de slide).

## Padrão dos documentos

Todo documento de entrega segue o mesmo cabeçalho e tom dos já produzidos (ver `escopo/*.tex` como
referência de formatação LaTeX pronta para reuso):

```
DOCUMENTO DE [DOMÍNIO] DO PROJETO
TrackFleet — Gestão de Rastreador de Automóveis
Disciplina de Gerenciamento de Projetos · Framework PMBOK® 8ª Edição · Domínio: [Nome do Domínio]
Integrantes: Enzo Allebrand e Kerlon Ribeiro (dois GPs) · 4º semestre · Data: [data da aula]
```

Cada seção do corpo do documento aplica um conceito da aula correspondente diretamente ao TrackFleet
(não repete a teoria genérica do slide — traduz o conceito em uma decisão concreta do projeto:
requisitos reais, exclusões reais, indicadores reais). Tabelas usam `booktabs` + `tabularx`; listas
aninhadas (como a EAP) usam `enumitem`. Os arquivos são LaTeX autocontidos (preâmbulo completo em cada
`.tex`), compiláveis isoladamente com `pdflatex` ou no Overleaf.

## Ao começar um novo domínio

1. Leia o PDF da aula correspondente em `aulas/` para extrair os conceitos-chave daquele domínio de
   desempenho.
2. Releia o Termo de Abertura (`o que temos/1.Termo_de_Abertura.pdf`) e os documentos de Governança já
   existentes para manter consistência de dados de contexto (problema, objetivo, restrições, papéis).
3. Aplique cada conceito do domínio a uma decisão concreta do TrackFleet — nunca deixe uma seção só
   com teoria genérica.
4. Produza um ou mais arquivos `.tex`, um por sub-parte relevante do domínio (como foi feito para
   Escopo: Produto, Projeto e Qualidade em arquivos separados), em uma pasta nova nomeada pelo
   domínio.
5. Responda sempre em português do Brasil, com ortografia completa (acentos e cedilhas corretos).
