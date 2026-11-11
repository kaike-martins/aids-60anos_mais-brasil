# 🔬 Análise Epidemiológica — AIDS em Pessoas com 60 Anos ou Mais no Brasil (2010–2024)

Análise epidemiológica sobre a evolução dos casos de AIDS em pessoas com 60 anos ou mais no Brasil, cobrindo o período de 2010 a 2024. O projeto foi desenvolvido como atividade acadêmica no curso de Ciência de Dados da FMU São Paulo e virou um trabalho científico apresentado ao vivo no **CONIC-SEMESP 2026** (26º Congresso Nacional de Iniciação Científica), com orientação da professora Luciana de Castro Lugli.

![Excel](https://img.shields.io/badge/Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=flat-square)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![PowerPoint](https://img.shields.io/badge/PowerPoint-D24726?style=flat-square&logo=microsoftpowerpoint&logoColor=white)
![Fonte](https://img.shields.io/badge/Fonte-SINAN%2FDATASUS%20%2B%20IBGE-5B2C8F?style=flat-square)

---

## 🎓 Trabalho científico (CONIC-SEMESP 2026)

**Título:** Crescimento demográfico ou aumento real da incidência? AIDS na população idosa brasileira (2010–2024)

- **Área/subárea:** Ciências Exatas, da Terra e Agrárias / Estatística
- **Categoria:** Concluído, com apresentação oral online em 11/11/2026
- **Artigo (PDF):** [`artigo/conic-2026-artigo.pdf`](artigo/conic-2026-artigo.pdf)
- **Slides:** [`apresentacao/conic-2026-apresentacao.pdf`](apresentacao/conic-2026-apresentacao.pdf)

---

## 📋 Contexto

O envelhecimento populacional brasileiro trouxe consigo um fenômeno pouco discutido: o crescimento dos casos de AIDS entre idosos. Este projeto quantifica essa tendência a partir de dados oficiais do DATASUS e do IBGE, com uma visão temporal, regional e por sexo, e separa o que é efeito do **aumento da população idosa** do que é **aumento real da taxa de incidência**.

> **Nota sobre os dados:** todos os dados utilizados neste projeto são integralmente públicos, provenientes do DATASUS e do IBGE. Não há qualquer informação confidencial ou identificação individual em nenhum dos arquivos.

---

## 🎯 Perguntas respondidas

- Qual foi a evolução do número de casos entre 2010 e 2024?
- Quanto desse crescimento vem do envelhecimento da população e quanto é aumento real da taxa de incidência?
- Existe diferença expressiva entre os sexos?
- Como a incidência mudou entre as regiões do país?
- O que explica a queda registrada em 2020?

---

## 📊 Principais achados

- **33.382 casos** registrados no período total.
- Os casos anuais cresceram **94,2%** (de 1.531 para 2.973), enquanto a população com 60 anos ou mais cresceu **67,1%** (de 20,9 para 34,9 milhões).
- A **taxa de incidência** passou de **7,34 para 8,52 casos por 100 mil idosos** (+16,2%). Ou seja, a maior parte do aumento dos casos é demográfica.
- O aumento da taxa se concentra em 2010–2013. Desde 2013 a taxa nacional está estável (−3,3%).
- **62,3%** dos casos são em homens e **37,7%** em mulheres.
- Em 2020 a taxa caiu para 6,47, associada à queda de diagnósticos durante a pandemia de COVID-19. Em seguida, voltou ao patamar anterior.
- A média nacional esconde trajetórias regionais opostas:

| Região | Taxa 2010 | Taxa 2024 | Variação |
|---|---:|---:|---:|
| Norte | 8,40 | 17,27 | +106% |
| Nordeste | 4,29 | 8,68 | +103% |
| Centro-Oeste | 6,70 | 9,58 | +43% |
| Sul | 11,34 | 11,43 | +1% |
| Sudeste | 7,65 | 6,23 | −19% |

*Taxas por 100 mil idosos.*

- Em números absolutos, o Sudeste concentra 38,8% dos casos (12.942), com São Paulo liderando (5.904).

---

## 🗂️ Estrutura do projeto

```
aids-60anos_mais-brasil/
│
├── README.md
│
├── artigo/
│   └── conic-2026-artigo.pdf              # Trabalho submetido ao CONIC-SEMESP 2026
│
├── dados/
│   ├── aids_60mais_total.csv              # Casos por ano (DATASUS)
│   ├── aids_60mais_sexo.csv               # Casos por sexo
│   ├── aids_60mais_regiao.csv             # Casos por região
│   ├── aids_60mais_estado.csv             # Casos por estado
│   └── aids_60mais_taxa_incidencia.csv    # Casos, população 60+ e taxa por 100 mil (Brasil e regiões, 2010–2024)
│
├── analise/
│   └── analise_aids_60mais.xlsx           # Análise completa, notas metodológicas e a população do IBGE (aba pop_cru_60mais)
│
├── dashboard/
│   └── 60_anos_mais_com_aids.pbix         # Dashboard interativo no Power BI
│
└── apresentacao/
    ├── conic-2026-apresentacao.pptx       # Slides da apresentação oral no CONIC 2026
    └── conic-2026-apresentacao.pdf        # Mesma apresentação em PDF
```

---

## 🛠️ Ferramentas e metodologia

**Coleta de dados.** Os casos foram extraídos do DATASUS (TabNet), na base de AIDS do Ministério da Saúde, que integra SINAN, SIM e Siscel/Siclom. Foi usado o filtro de Idade Detalhada para garantir o recorte exato de 60 anos ou mais. Os dados são consolidados até 30/09/2025 e foram acessados em 13/05/2026. A população vem do IBGE (Tabela 7358, Projeção da População por sexo e idade, edição 2018).

**Taxa de incidência.** Para separar o efeito do tamanho da população do aumento do risco, a análise usa a taxa bruta por 100 mil habitantes:

```
taxa = (casos no ano ÷ população de 60 anos ou mais no ano) × 100.000
```

A taxa foi calculada para o Brasil e para cada região, com a população da respectiva região. O resultado, ano a ano, está em [`dados/aids_60mais_taxa_incidencia.csv`](dados/aids_60mais_taxa_incidencia.csv).

**Tratamento no Excel.** Importação de 4 arquivos CSV via Power Query, com tratamento de encoding UTF-8, remoção de linhas de total e registros inconsistentes, e criação de coluna de Total calculada em tabela estruturada.

**Análise no Excel.** Aba de análise com 3 gráficos (evolução por ano, comparativo por sexo, casos por região), textos de interpretação, tabelas de população e percentuais, e uma aba de Notas Metodológicas documentando 7 limitações dos dados.

**Dashboard no Power BI.** Carregamento das 4 tabelas, Unpivot nas tabelas de estado, região e sexo para formato longo, modelagem de relacionamentos (todos Muitos para Um conectados à tabela total) e dashboard com cartão de total dinâmico, cartão de crescimento, filtro por ano, botões de filtro por sexo, gráfico de linha com evolução por sexo e gráfico de barras por região.

**Apresentação.** Slides do CONIC 2026 (8 slides e 1 de reserva), cobrindo a pergunta de pesquisa, dados e método, o contraste entre casos e taxa, a análise regional, as limitações e a conclusão.

---

## ⚠️ Limitações

- Os casos de AIDS refletem testagem, diagnóstico tardio e tratamento, e não equivalem à incidência de infecção por HIV.
- Estudo ecológico: a taxa descreve a população e não o risco individual.
- Dados de 2024 sujeitos a revisão, por atraso de notificação.
- A queda de 2020 reflete menos diagnósticos na pandemia, e não necessariamente menos infecções.
- Subnotificação estrutural, especialmente em municípios de menor porte.
- A população do IBGE é projeção (edição 2018). A Revisão 2024, com dados do Censo 2022, estima cerca de 2% menos idosos nos anos recentes.
- Sem testes estatísticos nem intervalos de confiança. Em regiões com poucos casos, as taxas oscilam mais.
- 7 casos com sexo ignorado e 13 com região ignorada ou exterior.
- Divergência de 1 caso entre os totais por ano e por região em 2021, vinda da própria base.

---

## 📚 Fontes

- DATASUS, base de AIDS do Ministério da Saúde (SINAN, SIM e Siscel/Siclom): [datasus.saude.gov.br](https://datasus.saude.gov.br)
- IBGE, Tabela 7358 (Projeção da População por sexo e idade): [sidra.ibge.gov.br/tabela/7358](https://sidra.ibge.gov.br/tabela/7358)

As referências bibliográficas do trabalho científico estão no PDF em [`artigo/`](artigo/).

---

## 👤 Autor

**Kaike Martins Pereira**, estudante de Ciência de Dados na FMU São Paulo. Orientação: professora Luciana de Castro Lugli.

[LinkedIn](https://www.linkedin.com/in/kaikemarttins)
