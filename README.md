# Análise de Vendas e Lucratividade — Superstore

Análise exploratória de dados de uma loja fictícia para investigar vendas, lucro e descontos por produto, categoria e região. O projeto utiliza Python para preparar e explorar os dados e apresenta um [dashboard interativo no Looker Studio](https://datastudio.google.com/s/iAv1zTyJ3Tw).

## Principais resultados

- **US$ 2,30 milhões em vendas** e **US$ 286 mil de lucro** (margem de 12,5%) em 9.994 transações.
- **Furniture vende quase tanto quanto Technology** (US$ 742 mil contra US$ 836 mil), mas **lucra 8 vezes menos** (US$ 18 mil contra US$ 145 mil). Tables é a subcategoria com maior prejuízo (−US$ 17,7 mil).
- **18,7% das transações dão prejuízo**, somando −US$ 156 mil.
- **Desconto é o principal fator de prejuízo:** sem desconto, o lucro médio é de US$ 66,90 por transação; com desconto acima de 20%, há prejuízo médio de US$ 97,20.
- **West e East concentram 70% do lucro.** A região Central tem a menor margem (7,9%, contra 14,9% da West).

**Recomendação:** revisar a política de descontos acima de 20%, começando por Furniture, e investigar a operação da região Central.

## Objetivo

Entender o desempenho comercial da Superstore e identificar pontos que merecem atenção:

- Quais categorias e produtos geram mais vendas?
- Como o lucro varia entre regiões?
- Quais transações apresentam lucro negativo?
- Como descontos e lucro se relacionam na base analisada?

## Etapas do projeto

1. **Obtenção dos dados:** download da base Superstore com `kagglehub`.
2. **Inspeção:** análise das primeiras linhas, tipos de dados, estatísticas descritivas, valores ausentes e duplicatas.
3. **Preparação:** conversão das datas de pedido e envio, padronização dos nomes das colunas e tratamento do código postal como texto.
4. **Análise exploratória:** cálculo de vendas e lucro por categoria, identificação dos dez produtos com maior volume de vendas, comparação entre regiões e investigação de transações com lucro negativo.
5. **Visualização:** gráficos de vendas por categoria, lucro por região, distribuição das vendas, correlações e relação entre desconto e lucro.

O código identifica valores atípicos de vendas por meio de um boxplot e **mantém esses registros** na análise.

## Dashboard interativo

📊 **[Explorar o dashboard da Superstore](https://datastudio.google.com/s/iAv1zTyJ3Tw)**

O painel complementa a análise em Python e permite explorar visualmente os indicadores de desempenho.

## Tecnologias utilizadas

- **Python e pandas:** leitura, preparação e análise dos dados;
- **Matplotlib e Seaborn:** criação dos gráficos;
- **KaggleHub:** download da base;
- **Looker Studio:** dashboard interativo.

## Como executar

É necessário ter Python instalado e acesso à internet, pois o script baixa a base durante a execução.

```bash
git clone https://github.com/Trilicia/Superstore_sales_analysis.git
cd Superstore_sales_analysis
python -m venv .venv
```

Ative o ambiente virtual:

```bash
# Windows — PowerShell
.venv\Scripts\Activate.ps1

# macOS ou Linux
source .venv/bin/activate
```

Instale as dependências e execute a análise:

```bash
pip install pandas numpy matplotlib seaborn kagglehub
python main.py
```

O script apresenta resultados no terminal e abre janelas com gráficos. Feche cada gráfico para avançar na execução.

> **Nota:** o arquivo `superstore_tratado.csv` está disponível no repositório, mas o `main.py` lê a base baixada pelo KaggleHub.

## Arquivos do repositório

| Arquivo                                                                               | Descrição                                                 |
| ------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| [`main.py`](main.py)                                                                 | Preparação, análise exploratória e gráficos em Python. |
| [`Desafio_Extra_Análise_de_dados.ipynb`](Desafio_Extra_An%C3%A1lise_de_dados.ipynb) | Análise em formato de notebook.                            |
| [`superstore_tratado.csv`](superstore_tratado.csv)                                   | Base tratada disponível no repositório.                   |
| `Arquivo de documentação — Superstore Dataset.docx`                              | Documentação complementar.                                |
| `Desafio_Extra-_Análise_Superstore (2).pdf`                                        | Material complementar em PDF.                               |

## Cuidados na interpretação

Os gráficos e as correlações mostram padrões presentes nesta base, mas não demonstram relações de causa e efeito. Por exemplo, a associação entre descontos e lucro não significa que o desconto seja a única causa de uma venda com prejuízo.

## Fonte dos dados

[Superstore Dataset — Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final).
