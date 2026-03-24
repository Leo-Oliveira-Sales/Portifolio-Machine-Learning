# 📊 People Analytics — Previsão de Demissão de Funcionários

Modelo de Machine Learning aplicado a Recursos Humanos (People Analytics) para identificar fatores que influenciam a demissão voluntária de colaboradores e prever o risco de saída de funcionários.

O projeto utiliza Python, Scikit-Learn e Pipeline de Machine Learning para construir um modelo preditivo capaz de auxiliar decisões estratégicas de RH.

---

## 🧠 Problema de Negócio

A rotatividade de funcionários (attrition) é um dos principais desafios enfrentados por empresas.

Quando um colaborador pede demissão, a empresa pode sofrer:

* perda de conhecimento
  
* custos de contratação
  
* custos de treinamento
  
* queda de produtividade

#### O objetivo deste projeto é:

Identificar os fatores que aumentam a probabilidade de um funcionário pedir demissão.

Com isso, o RH pode agir de forma preventiva para melhorar retenção de talentos e satisfação no trabalho.

---

## 📂 Dataset

#### Fonte dos dados:

https://developer.ibm.com/patterns/data-science-life-cycle-in-action-to-solve-employee-attrition-problem/

Dimensão do dataset:

23.058 registros

30 variáveis

#### Tipos de variáveis:

    Dados demográficos
    Informações profissionais
    Informações salariais
    Satisfação no trabalho
    Histórico de carreira

#### Variável alvo:

#### Attrition

Categorias originais:

Categoria	| Significado
----------|----------
Current employee	| Funcionário atual
Voluntary Resignation	| Demissão voluntária
Termination	| Demissão pela empresa

Para o modelo:

    0 = Funcionário permaneceu na empresa
    1 = Funcionário pediu demissão

A categoria Termination foi removida, pois representa decisão da empresa.

---

## 🧾 Dicionário das Variáveis (Principais)
    Variável	Descrição
    Age	Idade do colaborador
    AgeStartedWorking	Idade em que começou a trabalhar
    DistanceFromHome	Distância entre casa e trabalho
    Education	Nível de escolaridade
    EducationField	Área de formação
    Gender	Gênero
    JobRole	Cargo
    MaritalStatus	Estado civil
    MonthlyIncome	Salário mensal
    NumCompaniesWorked	Número de empresas trabalhadas
    OverTime	Realiza horas extras
    PercentSalaryHike	Aumento salarial
    TotalWorkingYears	Anos totais de experiência
    YearsAtCompany	Tempo na empresa
    YearsSinceLastPromotion	Anos desde última promoção
    WorkLifeBalance	Equilíbrio vida-trabalho

---

### ⚙️ Tecnologias Utilizadas:


    Python

    Pandas

    Scikit-Learn

    Jupyter Notebook

### Principais bibliotecas:

    pandas | scikit-learn

---

### Modelos utilizados:

* Logistic Regression

    🔧 Pipeline de Machine Learning

#### Foi criado um pipeline completo de pré-processamento e modelagem utilizando Scikit-Learn.

1. Pré-processamento numérico
   
* Imputação de valores ausentes (mediana)
* Padronização com StandardScaler

      SimpleImputer(strategy='median')
      StandardScaler()
  
2. Pré-processamento categórico

* Preenchimento de valores ausentes
* Codificação One-Hot

      OneHotEncoder(handle_unknown='ignore')
  
3. ColumnTransformer

Permite aplicar diferentes transformações para:

* variáveis numéricas
* variáveis categóricas

4. Pipeline final

       Pré-processamento → Modelo

5. Modelo utilizado:

        LogisticRegression(max_iter=1000)

## 🤖 Treinamento do Modelo

Divisão dos dados 80/20:

    80% treino | 20% teste

Função utilizada:

    train_test_split()

Avaliação do modelo:

    accuracy_score()

---

## 📈 Resultado

Acurácia do modelo:

    85.5%
    
    Accuracy = 0.855

Isso significa que o modelo consegue prever corretamente cerca de 85% dos casos de demissão voluntária ou permanência na empresa.

---

## 🔍 Principais Fatores Associados à Demissão

Os coeficientes da regressão logística indicam quais fatores aumentam a probabilidade de demissão.

---

## Principais fatores identificados:

### ✈️ Viagens frequentes

Funcionários que viajam frequentemente a trabalho têm maior probabilidade de pedir demissão.

### ⏰ Horas extras

Funcionários que trabalham com muitas horas extras apresentam maior risco de saída.

### 🏠 Distância casa-trabalho

Maior distância entre casa e empresa aumenta a chance de demissão.

### 📉 Tempo sem promoção

Funcionários que passam muitos anos sem promoção têm maior tendência a sair da empresa.

### 💼 Funções específicas

Alguns cargos apresentaram maior probabilidade de saída, como:

Laboratory Technician

Sales Representative

### 👤 Estado civil

Funcionários solteiros apresentaram maior probabilidade de demissão voluntária.

---

## 💡 Insights de Negócio

#### O modelo sugere que empresas podem reduzir a rotatividade através de:

* redução de horas extras
* programas de promoção e crescimento
* políticas de work-life balance
* revisão de políticas de viagens corporativas
* melhorias em cargos com maior rotatividade

---

## 🚀 Como Executar o Projeto

1️⃣ Clonar o repositório

    git clone https://github.com/seu-usuario/nome-do-repositorio.git

2️⃣ Instalar dependências

    pip install -r requirements.txt

ou

    pip install pandas scikit-learn

3️⃣ Executar o notebook

Abra o notebook no Jupyter:

    People_Analytics.ipynb
    
---

## 📁 Estrutura do Projeto

    people-analytics-attrition
    │
    ├── data
    │   └── people_data.csv
    │
    ├── notebook
    │   └── people_analytics_model.ipynb
    │
    ├── README.md
    │
    └── requirements.txt

---

## 📊 Aplicações do Projeto

* Este projeto pode ser adaptado para:

previsão de turnover de funcionários

People Analytics

análise de satisfação no trabalho

retenção de talentos

suporte à decisão em RH estratégico

---

# 👨‍💻 Autor

#### Leonardo Sales

#### Portfólio de Data Science e Machine Learning

