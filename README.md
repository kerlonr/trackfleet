<div align="center">

# 🚚 TrackFleet

**Plano completo de gestão de um projeto de rastreamento de frotas, seguindo o Guia PMBOK® 8ª Edição.**

![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white)
![PMBOK](https://img.shields.io/badge/PMBOK_8ª_Edição-1F4E79?style=for-the-badge)

</div>

---

## Sobre

**TrackFleet — Gestão de Rastreador de Automóveis** é o trabalho prático da disciplina de
**Gestão de Projetos** do curso de Engenharia da Computação da **SETREM**. A cada aula, um domínio de
desempenho do PMBOK® 8ª Edição é estudado e aplicado ao TrackFleet, gerando os documentos que
compõem a entrega final.

- **Problema:** falta de visibilidade em tempo real da frota e de dados objetivos para decidir sobre
  manutenção e uso dos veículos, agravada pelo custo alto das soluções corporativas.
- **Objetivo:** lançar uma plataforma de rastreamento e gestão de frotas acessível para pequenas
  transportadoras até o fim do semestre letivo.
- **Valor esperado:** menos custos operacionais e de manutenção corretiva, mais segurança para
  veículos e motoristas e decisões baseadas em dados reais.
- **Restrições:** prazo do semestre, orçamento zero para hardware próprio (integração via API com
  rastreadores de terceiros) e LGPD.

**Gestores do projeto:** Enzo Allebrand e Kerlon Ribeiro.

## Documentos

Todos os documentos são escritos em **LaTeX**, com o PDF gerado ao lado de cada `.tex`.

| Domínio | Documentos |
|---|---|
| 🏛️ **Governança** | Termo de abertura · Modelo e escalonamento · Papéis e RACI · Regras e registro · Métricas e sinal |
| 🎯 **Escopo** | Declaração de escopo |
| 📅 **Cronograma** | Cronograma do projeto |
| 💰 **Finanças** | Orçamento + planilha `trackfleet_financas.xlsx` |
| 🤝 **Partes interessadas** | Registro das partes interessadas · Plano de engajamento · Plano de comunicações |
| 👥 **Recursos** | Estrutura analítica dos recursos · Estimativa e histograma · Matriz RACI · Termo da equipe |
| ⚠️ **Riscos** | Plano de gerenciamento · Registro de riscos · Análise e respostas |
| 📦 **Entrega** | `trabalho_pratico_01/documento_consolidado.pdf` |

## Estrutura

```text
.
|-- governanca/
|-- escopo/
|-- cronograma/
|-- financas/
|-- partes_interessadas/
|-- recursos/
|-- riscos/
|-- trabalho_pratico_01/      documento consolidado da entrega
`-- aulas/                    material de apoio das aulas
```

## Gerando os PDFs

Com uma distribuição LaTeX instalada (TeX Live ou MiKTeX):

```bash
cd escopo
pdflatex escopo.tex
```

O mesmo vale para qualquer outro `.tex` do repositório.
