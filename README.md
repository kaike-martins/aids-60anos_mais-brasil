# 🔬 Análise Epidemiológica — AIDS em Pessoas com 60 Anos ou Mais no Brasil (2010–2024)

Análise epidemiológica completa sobre a evolução dos casos de AIDS em pessoas com 60 anos ou mais no Brasil, cobrindo o período de 2010 a 2024. O projeto foi desenvolvido como atividade acadêmica no curso de Ciência de Dados da FMU São Paulo e resultou em um convite para co-autoria em artigo científico pela professora orientadora.

---

## 📋 Contexto

O envelhecimento populacional brasileiro trouxe consigo um fenômeno pouco discutido: o crescimento expressivo dos casos de AIDS entre idosos. Este projeto busca quantificar e compreender essa tendência a partir de dados oficiais do DATASUS e do IBGE, oferecendo uma visão regional, temporal e por sexo da epidemia nessa faixa etária.

> **Nota sobre os dados:** todos os dados utilizados neste projeto são integralmente públicos, provenientes do DATASUS/SINAN e do IBGE. Não há qualquer informação confidencial ou identificação individual em nenhum dos arquivos.

---

## 🎯 Perguntas respondidas

- Qual foi a evolução do número de casos entre 2010 e 2024?
- Existe diferença expressiva entre os sexos?
- Quais regiões concentram mais casos — e quais cresceram mais?
- O que explica a queda registrada em 2020?
- Há evidências de interiorização da epidemia no período?

---

## 📊 Principais achados

- **33.382 casos** registrados no período total
- Crescimento de **94%** entre 2010 e 2024 (de 1.531 para 2.973 casos anuais)
- **63% dos casos são masculinos** e 37% femininos
- A **queda em 2020** é atribuída à subnotificação causada pela pandemia de COVID-19, não a uma redução real da epidemia
- A **Região Sudeste** concentra 39% dos casos (12.942), com São Paulo liderando (5.904)
- **Nordeste cresceu 202%** e **Norte cresceu 245%** no período — sinal de interiorização da epidemia para regiões historicamente com menor infraestrutura de saúde

---

## 🗂️ Estrutura do projeto

```
aids-60-brasil/
│
├── README.md
├── dados/
│   ├── sinan_casos_ano.csv          # Casos por ano (DATASUS/SINAN)
│   ├── sinan_casos_sexo.csv         # Casos por sexo
│   ├── sinan_casos_regiao.csv       # Casos por região
│   ├── sinan_casos_estado.csv       # Casos por estado
│   └── ibge_populacao_60mais.csv    # Projeção populacional IBGE (Tabela 7358)
│
├── analise/
│   └── analise_aids_60mais.xlsx     # Análise completa com gráficos e notas metodológicas
│
├── dashboard/
│   └── dashboard_aids_60mais.pbix   # Dashboard interativo no Power BI
│
└── apresentacao/
    └── apresentacao_aids_60mais.pptx  # Apresentação em PowerPoint (10 slides)
```

---

## 🛠️ Ferramentas e metodologia

**Coleta de dados**
Os dados de casos foram extraídos diretamente do DATASUS/SINAN via TabNet, utilizando o filtro de Idade Detalhada para garantir o recorte exato de 60 anos ou mais. Os dados populacionais foram obtidos do IBGE (Tabela 7358 — Projeção da População por sexo e idade).

**Tratamento no Excel**
Importação de 4 arquivos CSV via Power Query, com tratamento de encoding UTF-8, remoção de linhas de total e registros inconsistentes, e criação de coluna de Total calculada em tabela estruturada.

**Análise no Excel**
Construção de aba de Análise com 3 gráficos (evolução por ano, comparativo por sexo, casos por região), textos de interpretação para cada visualização, tabelas de população e percentuais, e aba de Notas Metodológicas documentando 7 limitações dos dados.

**Dashboard no Power BI**
Carregamento das 4 tabelas, Unpivot nas tabelas de estado, região e sexo para formato longo, modelagem de relacionamentos (todos Muitos para Um conectados à tabela total), e construção de dashboard com cartão de total dinâmico, cartão de crescimento, filtro por ano, botões de filtro por sexo, gráfico de linha com evolução por sexo e gráfico de barras por região.

**Apresentação**
10 slides com identidade visual institucional, cobrindo contexto, metodologia, achados, implicações para a prática de enfermagem, notas metodológicas e fontes.

---

## ⚠️ Limitações dos dados

1. Dados de 2024 sujeitos a revisão — consolidação ainda em andamento no SINAN
2. Subnotificação estrutural, especialmente em municípios de menor porte
3. Recorte etário obtido via filtro de Idade Detalhada para garantir o corte exato de 60 anos ou mais
4. 7 casos com sexo ignorado no SINAN
5. 13 casos com região ignorada ou exterior
6. A queda registrada em 2020 reflete subnotificação causada pela pandemia de COVID-19, não redução real da epidemia
7. Dados populacionais do IBGE são projeções estatísticas, não contagens reais

---

## 📚 Fontes

- **DATASUS/SINAN** — Sistema de Informação de Agravos de Notificação: [datasus.saude.gov.br](https://datasus.saude.gov.br)
- **IBGE Tabela 7358** — Projeção da População por sexo e idade: [sidra.ibge.gov.br](https://sidra.ibge.gov.br)
- **Boletim Epidemiológico HIV/AIDS** — Ministério da Saúde

---

## 👤 Autor

**Kaike Martins**
Estudante de Ciência de Dados — FMU São Paulo
[LinkedIn](https://linkedin.com/in/kaikemarttins) · [GitHub](https://github.com/kaike-martins)
