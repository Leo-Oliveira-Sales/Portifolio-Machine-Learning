# 📊 Previsão de Indicadores Macroeconômicos com Regressão Multi-Target

Projeto de Data Science aplicado à Economia que utiliza Machine Learning para prever múltiplos indicadores macroeconômicos simultaneamente por meio da técnica de Regressão Multi-Target (Multi-Output Regression).

O objetivo é demonstrar como modelos de aprendizado de máquina podem capturar relações entre variáveis econômicas e realizar previsões simultâneas de múltiplos indicadores.

---

## 🎯 Objetivo do Projeto

Aplicar técnicas de Machine Learning para prever simultaneamente os seguintes indicadores macroeconômicos:

    PIB
    Inflação
    Taxa de Desemprego

A partir das variáveis:

    Taxa de Juros
    Taxa de Câmbio
    Produção Industrial

A abordagem utiliza **Regressão Multi-Target**, permitindo que o modelo faça previsões para múltiplas variáveis dependentes ao mesmo tempo, explorando possíveis relações entre elas.

---

## 🧠 Conceito Utilizado
**Regressão Multi-Target**

>A Regressão Multi-Target (Multi-Output Regression) é uma técnica de aprendizado de máquina utilizada quando o objetivo é prever mais de uma variável de saída simultaneamente.

>Diferente da regressão tradicional, onde o modelo prevê apenas uma variável alvo, essa abordagem permite prever diversos indicadores ao mesmo tempo, o que é especialmente útil em contextos econômicos e financeiros.

* Principais abordagens para Multi-Target:

      Modelos independentes para cada variável
      MultiOutputRegressor
      Modelos multivariados (Deep Learning)
      Regressão conjunta (ex: PLS)

Neste projeto foi utilizado:

    MultiOutputRegressor + Random Forest

---

## 🗂 Dataset

O dataset contém 1000 observações fictícias de indicadores econômicos.

⚠️ Os dados são simulados e utilizados apenas para fins educacionais.

>>Variáveis do dataset

Variável	| Descrição
----------|---------
taxa_juros	| Taxa de juros da economia
taxa_cambio	| Valor da taxa de câmbio
producao_industrial	| Índice de produção industrial
pib	| Produto Interno Bruto
inflacao	| Taxa de inflação
taxa_desemprego	| Taxa de desemprego

#### Dimensão do dataset:

    1000 linhas
    6 variáveis

---

## ⚙️ Tecnologias Utilizadas

    Python
    Pandas
    NumPy
    Scikit-Learn
    Random Forest
    Machine Learning
    Jupyter Notebook

Bibliotecas principais:

    sklearn
    pandas
    numpy
    
#### 🔬 Metodologia

O pipeline do projeto segue as etapas clássicas de Data Science:

1️⃣ Carregamento dos dados

    Importação do dataset com Pandas

2️⃣ Separação das variáveis

#### Variáveis independentes (features):

* taxa_juros
* taxa_cambio
* producao_industrial

#### Variáveis alvo (targets):

* pib
* inflacao
* taxa_desemprego

3️⃣ Divisão treino / teste

    80% treino
    20% teste

Utilizando:

    train_test_split()
    
4️⃣ Padronização dos dados

Aplicação do:

    StandardScaler - Para normalizar as variáveis de entrada.

5️⃣ Construção do modelo

Modelo utilizado:

    MultiOutputRegressor(
        RandomForestRegressor(n_estimators=100)
    )

#### Estrutura conceitual do modelo:

                ┌── Modelo 1 ──► PIB
    X ──────────┤
                ├── Modelo 2 ──► Inflação
                │
                └── Modelo 3 ──► Desemprego

Cada variável alvo recebe um modelo de regressão baseado em Random Forest.

---

## 📈 Avaliação do Modelo

#### Foram utilizadas duas métricas:
  
1. Mean Squared Error (MSE)

        PIB: 38.89
        Inflação: 4.94
        Desemprego: 1.20

* **O MSE mede o erro médio entre valores reais e previstos.**

>Quanto menor o valor, melhor o desempenho do modelo.

2. Coeficiente de Determinação (R²)

        PIB: 0.94
        Inflação: 0.94
        Desemprego: 0.99

* **O R² mede o quanto da variabilidade dos dados é explicada pelo modelo.**

>Valores próximos de 1 indicam excelente desempenho preditivo.

---

## 📊 Comparação entre valores reais e previstos

**Exemplo de saída do modelo:**

PIB	| Inflação	| Desemprego	| PIB Pred	| Inflação Pred	| Desemprego Pred
----|-----------|-------------|-----------|---------------|-----------------
63.01	| 26.68	| 30.27	| 54.65	| 25.03	| 28.16
101.76	| 36.17	| 52.48	| 96.78	| 35.58	| 51.89
70.14	| 30.86	| 40.71	| 78.47	| 31.73	| 41.67

---

### 🚀 Como Executar o Projeto


#### Clone o repositório:

    git clone https://github.com/seuusuario/nome-do-repositorio

Instale as dependências:

    pip install -r requirements.txt


### 📌 Possíveis Melhorias

Este projeto pode ser expandido com:

    Modelos adicionais (XGBoost, LightGBM)
    Redes neurais para regressão multi-output
    Análise de correlação entre indicadores
    Feature Engineering
    Visualizações econômicas
    Validação cruzada
    Hyperparameter tuning
    
---

### 💼 Aplicações Práticas

Este tipo de abordagem pode ser aplicado em:

    Previsão macroeconômica
    Modelagem econômica
    Análise de políticas monetárias
    Planejamento econômico
    Finanças quantitativas
    Modelagem de indicadores econômicos

---

# 👨‍💻 Autor

### Leonardo Sales

### Portfólio de Data Science, Machine Learning e Análise de Dados
