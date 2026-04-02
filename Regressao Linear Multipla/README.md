
## 📊 Estimativa de Expectativa de Vida com Machine Learning

Projeto de Ciência de Dados e Machine Learning cujo objetivo é analisar fatores socioeconômicos e de saúde que impactam a expectativa de vida global e construir um modelo de regressão capaz de realizar previsões.

O projeto foi dividido em duas etapas principais:

1️⃣ Análise e Preparação dos Dados

2️⃣ Modelagem Preditiva (Regressão)

## 📌 Objetivo do Projeto

Construir um modelo de regressão para estimar a expectativa de vida de países com base em variáveis socioeconômicas, educacionais e indicadores de saúde pública.

* Entre os fatores analisados estão:

      Mortalidade adulta
      Cobertura vacinal
      PIB per capita
      Consumo de álcool
      Escolaridade
      Investimentos em saúde
      Indicadores nutricionais
    
## 📂 Estrutura do Projeto

    life-expectancy-regression/
    │
    ├── data
    │   └── dataset.csv
    │
    ├── notebooks
    │   ├── 01_data_analysis.ipynb
    │   └── 02_regression_models.ipynb
    │
    ├── images
    │   └── graphs
    │
    └── README.md

---

## 🧠 Parte 1 — Análise e Preparação dos Dados

Nesta etapa foi realizada uma análise exploratória completa dos dados (EDA) para compreender a estrutura do dataset e identificar padrões relevantes.

#### 📊 Dataset

O dataset contém informações de 193 países entre 2000 e 2015, totalizando:

2938 registros

22 variáveis

* Principais variáveis:

      Variável	Descrição
      Life_expectancy	Expectativa de vida ao nascer
      Adult_mortality	Taxa de mortalidade adulta
      Infant_deaths	Mortalidade infantil
      Alcohol	Consumo de álcool per capita
      Hepatitis_b	Cobertura vacinal de Hepatite B
      GDP	PIB per capita
      Schooling	Média de anos de escolaridade
      Population	População total

---

## 🧹 Tratamento e Limpeza de Dados

**Durante o pré-processamento foram realizadas diversas etapas importantes:**

>Padronização de colunas/ remoção de espaços/ padronização para snake_case/ organização semântica das variáveis

      dados.columns = (
          dados.columns
          .str.strip()
          .str.lower()
          .str.replace(" ", "_")
          .str.capitalize()
      )

>Remoção de variáveis pouco interpretáveis

Algumas variáveis foram removidas por falta de clareza na documentação.

    dados = dados.drop(columns=[
        "Percentage_expenditure",
        "Under-five_deaths",
        "Income_composition_of_resources"
    ])


## 🔎 Análise Exploratória dos Dados (EDA)

Foram utilizadas diversas técnicas de visualização para compreender a distribuição das variáveis.

Bibliotecas utilizadas:

    pandas
    numpy
    matplotlib
    seaborn
    plotly
    Distribuição das variáveis

*Histogramas foram utilizados para entender a distribuição das variáveis numéricas*

* **Principais observações:**

      A maior parte dos países apresenta expectativa de vida entre 60 e 80 anos
      Existem outliers significativos em população e casos de sarampo
      Variáveis econômicas possuem alta variabilidade

---

## 💡 Principais Insights

📚 Educação

    Países com maior nível de escolaridade apresentam maior expectativa de vida.

💰 Economia

    Países com maior PIB per capita tendem a ter melhor qualidade de vida e maior longevidade.

💉 Vacinação

    Cobertura vacinal maior está associada a aumento da expectativa de vida.

🍷 Consumo de álcool

    A correlação positiva pode estar associada ao nível de desenvolvimento econômico dos países, e não necessariamente ao efeito direto do consumo.


---

## 🤖 Parte 2 — Modelagem de Machine Learning

**Na segunda etapa do projeto foram treinados modelos de regressão para estimar a expectativa de vida.**


* Bibliotecas utilizadas:

      scikit-learn
      pandas
      numpy
      📏 Métricas de Avaliação


#### ⚙️ Tecnologias Utilizadas em todo o projeto:

    Python
    pandas
    numpy
    matplotlib
    seaborn
    plotly
    scikit-learn
    Jupyter Notebook
---

# 👨‍💻 Autor

Leonardo Sales

Estudante de Ciência de Dados e Inteligência Artificial.

🔗 GitHub
https://github.com/Leo-Oliveira-Sales

💡 Projeto desenvolvido para portfólio de Data Science e Machine Learning.
