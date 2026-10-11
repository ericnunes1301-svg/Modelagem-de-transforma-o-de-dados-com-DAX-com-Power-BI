# Modelagem-de-transforma-o-de-dados-com-DAX-com-Power-BI
Modelagem de transformação de dados com DAX com Power BI
# Dashboard de Vendas: Power BI

Projeto prático de Power BI do desafio da DIO. O objetivo é tratar dados financeiros de vendas no Power Query, modelar as tabelas em esquema dimensional e construir um relatório com análises de vendas, lucro e unidades vendidas.

## Fonte dos dados

Base financeira (`financials`) do repositório [julianazanelatto/power_bi_analyst](https://github.com/julianazanelatto/power_bi_analyst).

## Etapas do projeto

### 1. Tratamento no Power Query

A tabela de origem (`financials_origem`) foi separada em tabelas dimensão e fato. Principais transformações:

- Remoção e reordenação de colunas
- Ajuste dos tipos de dados
- Criação de colunas personalizadas na tabela de produtos, com estatísticas de vendas:
  - Média de Unidades Vendidas (`List.Average`)
  - Média de Vendas (`List.Average`)
  - Mediana de Vendas (`List.Median`)
  - Valor máximo de venda (`List.Max`)
  - Valor mínimo de venda (`List.Min`)

### 2. Modelagem

| Tabela | Tipo | Conteúdo |
|---|---|---|
| `F_Vendas` | Fato | Vendas, país, data, mês, preço de fabricação e IDs de produto |
| `D_Produtos` | Dimensão | Produto e estatísticas de vendas por produto |
| `D_Produtos_Detalhes` | Dimensão | Preço de fabricação, preço de venda e unidades vendidas |
| `D_Descontos` | Dimensão | Faixa de desconto e valor dos descontos |
| `financials_origem` | Origem | Base original, mantida como referência |

As tabelas se relacionam pela chave `ID_produtos`, com relacionamentos de um para muitos.

### 3. Relatório

<img width="1360" height="737" alt="Modelando com DAX Power BI" src="https://github.com/user-attachments/assets/a52582b2-1e43-4eb0-af5f-fb89333b343e" />


## Ferramentas

- Power BI Desktop
- Power Query (linguagem M)

## Autor

**Eric**
