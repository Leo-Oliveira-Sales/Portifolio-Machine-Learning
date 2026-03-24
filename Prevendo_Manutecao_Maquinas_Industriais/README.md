# ⚙️ Predictive Maintenance — Prevendo Manutenção de Máquinas Industriais

#### Projeto de Machine Learning aplicado à Manutenção Preditiva (Predictive Maintenance) utilizando dados de sensores IoT para prever se uma máquina industrial precisará de manutenção.

#### O objetivo é utilizar dados históricos de sensores industriais para identificar padrões que indiquem falhas ou necessidade de manutenção preventiva.

### Esse tipo de solução é amplamente utilizado em Indústria 4.0, permitindo reduzir custos operacionais e evitar paradas inesperadas de máquinas.

---

## 🧠 Problema de Negócio

Em ambientes industriais, falhas inesperadas de equipamentos podem gerar:

* paradas de produção
* prejuízos financeiros
* perda de produtividade
* aumento de custos de manutenção

### A manutenção tradicional geralmente ocorre de duas formas:

#### 🔧 Manutenção corretiva

    A máquina quebra e depois é consertada.

#### ⏱ Manutenção preventiva

    Manutenção feita em intervalos fixos, mesmo que a máquina não precise.

### Este projeto propõe uma terceira abordagem:

#### 🤖 Manutenção preditiva

    Utilizar Machine Learning e dados de sensores IoT para prever quando uma máquina precisará de manutenção.

Isso permite agir antes da falha acontecer.

---

## 📂 Dataset

O dataset contém dados fictícios de sensores IoT coletados de máquinas industriais.

#### Dimensão do dataset:

    11.500 registros
    178 sensores
    1 variável alvo

#### Total de colunas:

    179 colunas

* Cada linha representa:

      Uma leitura completa dos sensores de uma máquina

* Cada coluna representa:

      Leitura de um sensor específico

* Exemplo de sensores:

X1, X2, X3 ... X178

---

## 🎯 Variável Alvo

A última coluna do dataset indica o status da máquina:

    VARIAVEL_ALVO

* Valor	Significado

        0	Máquina não precisa de manutenção
        1	Máquina precisa de manutenção

Distribuição da classe:

    Classe 0 → 80%
    Classe 1 → 20%

Isso indica um problema de classificação binária com leve desbalanceamento.

---

## 📊 Análise Exploratória

#### Algumas verificações realizadas:

✔ Valores ausentes

    df.isna().sum().sum()

Resultado:

    0 valores ausentes

✔ Colunas duplicadas

      df.columns.duplicated().sum()

Resultado:

    0 colunas duplicadas

✔ Prevalência da classe positiva

    20% das máquinas precisam de manutenção

---

## 🔗 Correlação com a Variável Alvo

#### Foi calculada a correlação entre cada sensor e a variável alvo para identificar sensores mais relacionados com falhas.

Escala utilizada:

Correlação	| Interpretação
------------|---------
0.01 – 0.30	| fraca
0.30 – 0.50	| moderada
0.50 +	    | forte

* Sensores com maior correlação:

      X11
      X10
      X12
      X44
      X158
      X159
      X160
      X43
      X9
      X8

Apesar de as correlações serem relativamente baixas, elas ajudam a identificar sinais importantes para os modelos de Machine Learning.

---

### 🌲 Importância das Variáveis

Para identificar quais sensores são mais relevantes para prever manutenção, foi utilizado o modelo:

    RandomForestClassifier

Top sensores mais importantes:

    X156
    X159
    X28
    X157
    X160
    X158
    X161
    X162
    X45
    X27
    X96
    X17
    X39
    X13
    X95

Esses sensores possuem maior impacto na previsão de falhas.

Uma possível melhoria futura seria treinar modelos utilizando apenas os sensores mais importantes.


---

## ⚙️ Preparação dos Dados

Separação das variáveis:

    X = sensores (X1 até X178)
    y = VARIAVEL_ALVO

Divisão dos dados:

    70% treino
    30% teste

Função utilizada:

    train_test_split()

### 📏 Padronização dos Dados

Foi aplicado:

    StandardScaler

Motivo:

    normalizar as leituras dos sensores
    melhorar o desempenho dos algoritmos

---

## 🤖 Modelos de Machine Learning

Foram testados quatro algoritmos de classificação:

Modelo	| Biblioteca
--------|-----------
Logistic | Regression	Scikit-Learn
Naive Bayes	| Scikit-Learn
Random Forest	| Scikit-Learn
XGBoost	| XGBoost

* Métricas avaliadas:

      AUC (Area Under ROC Curve)
      Accuracy
      Recall
      Precision
  
---

#### 📈 Resultados dos Modelos

Modelo	| AUC	| Accuracy	| Recall	| Precision
--------|-----|-----------|---------|---------------
Random | Forest	| 0.995	| 0.973	| 0.921	| 0.946
XGBoost	| 0.994	| 0.970	| 0.894	| 0.953
Naive Bayes	| 0.982	| 0.954	| 0.885	| 0.885
Logistic Regression	| 0.524	| 0.820	| 0.102	| 0.972

## 🏆 Melhor Modelo

#### O modelo com melhor desempenho foi:

    RandomForestClassifier

* Principais motivos:

      maior AUC
      alta acurácia
      melhor equilíbrio entre precision e recall
  
### 💾 Salvando o Modelo

O modelo final foi salvo utilizando:

    pickle

Arquivo gerado:

    melhor_modelo.pkl

Isso permite utilizar o modelo posteriormente em:

    APIs
    sistemas industriais
    aplicações de monitoramento
    
### 🔮 Fazendo Novas Previsões

* Exemplo de nova leitura de sensores:

      nova_maquina = pd.DataFrame(np.random.randint(-150,150,(1,178)), columns=X.columns)

* Previsão:

      modelo.predict(nova_maquina)

* Resultado possível:

      [1]

* Significado:

      A máquina provavelmente precisará de manutenção

---

### 🏭 Aplicações do Projeto

Este tipo de solução pode ser aplicado em:

    indústrias de manufatura
    fábricas automatizadas
    monitoramento de equipamentos
    manutenção preditiva em IoT
    Indústria 4.0

Benefícios:

    redução de falhas inesperadas
    redução de custos de manutenção
    aumento da vida útil de equipamentos
    aumento da eficiência operacional

---

### 🚀 Como Executar o Projeto

1️⃣ Clonar o repositório

    git clone https://github.com/seu-usuario/nome-do-projeto.git

2️⃣ Instalar dependências

    pip install pandas numpy scikit-learn xgboost seaborn matplotlib

---

## 📁 Estrutura do Projeto

    predictive-maintenance-ml
    │
    ├── dataset
    │   └── dataset.csv
    │
    ├── notebook
    │   └── predictive_maintenance_model.ipynb
    │
    ├── models
    │   └── melhor_modelo.pkl
    │
    ├── README.md
    │
    └── requirements.txt

## 💡 Melhorias Futuras

#### Possíveis evoluções do projeto:

1. otimização de hiperparâmetros com GridSearchCV
2. treinamento apenas com tops sensores
3. implementação de pipeline de ML
4. criação de API com FastAPI ou Flask
5. integração com sistemas de monitoramento IoT
6. deploy do modelo

---

# 👨‍💻 Autor

#### Leonardo Sales

#### Portfólio de Data Science e Machine Learning
