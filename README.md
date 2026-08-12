<h1 align="center">Análise de Vendas em E-commerce</h1>

<p align="center">
  Projeto de análise exploratória de dados desenvolvido no workshop de Dados e IA da <strong>EBAC</strong>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white" alt="Pandas">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/status-em%20andamento-yellow" alt="Status">
</p>

---

## 📌 Sobre o projeto

Este repositório reúne a análise exploratória de uma base de **5.000 pedidos de e-commerce**, contendo informações de categoria de produto, região, forma de pagamento, quantidade, preço, desconto e prazo de entrega.

O objetivo é praticar o ciclo completo de uma análise de dados: **limpeza → exploração → geração de insights**, documentando cada decisão tomada ao longo do caminho.

## Pergunta de análise

> Quais fatores de categoria de produto, região e forma de pagamento mais influenciam o valor total dos pedidos e o desconto aplicado, e como o prazo de entrega varia entre regiões?

## Fonte dos dados

- **Nome do arquivo:** `ecommerce_sales_analytics_5000-selected-columns.csv`
- **Linhas / colunas:** 5.000 pedidos × 10 colunas
- **Colunas:** `order_id`, `order_date`, `customer_id`, `product_category`, `region`, `quantity`, `unit_price`, `discount`, `payment_method`, `delivery_days`

## Principais decisões de limpeza

| Problema encontrado | Tratamento aplicado |
|---|---|
| Separador do CSV era `;` em vez de `,` | Leitura com `sep=';'` |
| Nomes de colunas com espaços (` unit_price `) | `.str.strip()` nos nomes |
| Valores decimais mistos (`.` e `,`) em `unit_price` | Padronização para `.` antes da conversão para `float` |
| 68 valores `"-"` em `discount` | Tratados como dado faltante (`NaN`), não como zero |
| Datas com padding inconsistente (`01/01/2022` vs `9/30/2035`) | Conversão explícita com `pd.to_datetime(format='%m/%d/%Y')` |
| Duplicatas | Nenhuma encontrada em `order_id` ou linhas completas |

## Principais insights

- **Electronics** lidera a receita total entre as categorias, seguida por Clothing, Home e Beauty — com uma diferença expressiva entre a categoria líder e a última colocada.
- O **prazo médio de entrega é praticamente homogêneo entre as regiões** (variação de menos de 0,1 dia), sugerindo que a região não é, isoladamente, um fator relevante de atraso logístico nesta base.
- **Cartão** é a forma de pagamento mais usada, mas o **desconto médio aplicado é praticamente igual** entre Cartão, COD e Wallet — indicando que o desconto não é usado como incentivo para um meio de pagamento específico.

> _(Insights detalhados, com gráficos, disponíveis no notebook)_

## Estrutura do repositório

```
├── data/
│   ├── raw/            # dados originais, sem alterações
│   └── processed/      # dados após limpeza
├── notebooks/
│   └── analise_exploratoria.ipynb
├── images/             # gráficos exportados
├── requirements.txt
├── .gitignore
└── README.md
```

## Tecnologias utilizadas

- Python
- Pandas
- Matplotlib / Seaborn
- Jupyter Notebook

## 👤 Autora

Feito por **Julia de Souza Seger** — projeto desenvolvido durante o workshop de Dados e IA da [EBAC](https://ebaconline.com.br).

<p align="center">
  <a href="https://www.linkedin.com/in/julia-seger/">LinkedIn</a> ·
  <a href="https://github.com/juliasgr">GitHub</a>
</p>
