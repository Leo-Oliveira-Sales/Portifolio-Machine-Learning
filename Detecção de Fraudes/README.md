# 🚨 Detecção de Fraudes em Criptomoedas com Machine Learning

## 📌 Visão Geral do Projeto

Com o crescimento das criptomoedas, aumentaram também os riscos relacionados a **fraudes financeiras e atividades maliciosas em redes blockchain**. Detectar esse tipo de comportamento manualmente é extremamente difícil devido ao grande volume de transações.

Este projeto desenvolve um **modelo de Machine Learning capaz de identificar transações potencialmente fraudulentas** a partir de características comportamentais das transações.

A solução foi construída utilizando **Python, Scikit-Learn e XGBoost**, integrando todo o fluxo de análise em um **pipeline automatizado de Machine Learning**.

O projeto inclui:

* limpeza de dados
* engenharia de atributos
* pré-processamento
* treinamento do modelo
* avaliação do modelo
* pipeline automatizado para previsão

---

# 🧠 Fluxo de Machine Learning

O projeto segue um fluxo padrão de ciência de dados:

```
Limpeza dos Dados
        ↓
Engenharia de Atributos
        ↓
Divisão Treino/Teste
        ↓
Pipeline de Pré-Processamento
        ↓
Treinamento do Modelo (XGBoost)
        ↓
Avaliação do Modelo
        ↓
Predições
```

---

# 📊 Descrição do Dataset

O dataset contém informações sobre **transações e comportamento de carteiras em blockchain**.

Alguns exemplos de variáveis presentes no dataset:

| Variável                 | Descrição                              |
| ------------------------ | -------------------------------------- |
| sent tnx                 | número de transações enviadas          |
| received tnx             | número de transações recebidas         |
| avg val sent             | valor médio enviado                    |
| avg val received         | valor médio recebido                   |
| total ether sent         | total de ether enviado                 |
| total ether received     | total de ether recebido                |
| unique sent to addresses | número de endereços únicos interagidos |

Essas variáveis ajudam a identificar **padrões suspeitos de movimentação financeira**.

---

# 🎯 Variável Alvo

A variável utilizada para classificação foi:

```
flag
```

| Valor | Significado           |
| ----- | --------------------- |
| 0     | Transação legítima    |
| 1     | Transação fraudulenta |

---

# ⚙️ Tecnologias Utilizadas

Este projeto foi desenvolvido utilizando:

* Python
* Pandas
* Scikit-Learn
* XGBoost
* Joblib
* Jupyter Notebook

---

# 🧹 Pré-Processamento dos Dados

O pré-processamento foi realizado utilizando **Pipelines do Scikit-Learn**, garantindo reprodutibilidade e evitando vazamento de dados.

## Padronização dos nomes das colunas

```
df.columns = df.columns.str.strip().str.lower()
```

## Tratamento de valores ausentes

Valores faltantes foram preenchidos utilizando a **média da variável**.

```
SimpleImputer(strategy="mean")
```

## Padronização das variáveis

Foi aplicado **StandardScaler** para normalizar a escala dos dados.

```
StandardScaler()
```

---

# 🧠 Modelo de Machine Learning

O algoritmo utilizado foi **XGBoost (Extreme Gradient Boosting)**.

Esse modelo é amplamente utilizado em problemas de classificação devido à sua:

* alta performance
* capacidade de lidar com dados complexos
* robustez contra overfitting

Configuração utilizada:

```python
XGBClassifier(
    random_state=42,
    eval_metric='auc',
    objective='binary:logistic'
)
```

---

# 🔄 Pipeline do Projeto

Todo o fluxo de dados foi implementado utilizando **Pipeline do Scikit-Learn**.

Estrutura do pipeline:

```
Imputação de valores faltantes
        ↓
Padronização das variáveis
        ↓
Modelo XGBoost
```

Isso garante que todas as transformações sejam aplicadas automaticamente durante o treinamento e durante as previsões.

---

# 📈 Avaliação do Modelo

A principal métrica utilizada foi:

### AUC — Área sob a Curva ROC

Essa métrica mede a capacidade do modelo de **diferenciar transações legítimas de fraudulentas**.

Valores próximos de **1 indicam excelente desempenho do modelo**.

---

# 🚀 Como Executar o Projeto

### 1️⃣ Clonar o repositório

```
git clone https://github.com/seu_usuario/crypto-fraud-detection.git
```

### 2️⃣ Instalar as dependências

```
pip install -r requirements.txt
```

### 3️⃣ Executar o notebook

Abra o **Jupyter Notebook** e execute as células do projeto.

---

# 💾 Salvando o Modelo

Após o treinamento, o modelo pode ser salvo para uso posterior.

```python
joblib.dump(pipeline_final, "modelo_fraude.joblib")
```

---

# 🔮 Fazendo Previsões

O modelo salvo pode ser carregado para realizar previsões em novos dados.

```python
modelo = joblib.load("modelo_fraude.joblib")

predicao = modelo.predict(novos_dados)
```

---

# 🧩 Possíveis Aplicações

A estrutura deste projeto pode ser utilizada em diversos problemas reais:

* detecção de fraude em criptomoedas
* fraude em cartões de crédito
* análise de risco financeiro
* detecção de comportamento suspeito
* sistemas antifraude em fintechs
* análise de anomalias em transações financeiras


---

# 📁 Estrutura do Projeto

```
crypto-fraud-detection
│
├── data
│   └── dataset.csv
│
├── notebooks
│   └── fraud_detection.ipynb
│
├── models
│   └── modelo_fraude.joblib
│
├── README.md
└── requirements.txt
```

---

# 👨‍💻 Autor

**Leonardo Sales**

📊 Analista de Dados / Cientista de Dados em formação
💻 Projetos de Machine Learning e Análise de Dados

GitHub: Portfólio de projetos em Data Science

---

