# 🚨 Detecção de Fraudes em Criptomoedas com Machine Learning

## 📌 Visão Geral do Projeto

---

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

## Objetivos do Projeto

#### O projeto possui os seguintes objetivos principais:

Detectar automaticamente transações fraudulentas.

Criar um pipeline de Machine Learning automatizado.

Aplicar boas práticas de pré-processamento de dados.

Construir um modelo escalável que possa ser utilizado em produção.

Demonstrar um fluxo completo de Data Science aplicado a problemas reais.

---

## Conjunto de Dados

O dataset utilizado contém informações sobre transações realizadas em blockchain, incluindo características como:

número de transações enviadas e recebidas

tempo entre transações

valores mínimos e máximos transferidos

quantidade de contratos criados

saldo total da carteira

interações com tokens ERC20

#### Essas variáveis descrevem o comportamento financeiro de cada endereço na blockchain, permitindo identificar padrões associados a atividades fraudulentas.

---

## A variável alvo utilizada foi:

## flag

Durante a etapa de engenharia de atributos foram realizadas as seguintes operações:

#### Limpeza dos nomes das colunas

Padronização para evitar inconsistências durante o processamento.

    df.columns = df.columns.str.strip().str.lower()

---

#### Seleção de atributos

Foram removidas variáveis irrelevantes ou redundantes.

    X = df[atributos]
    y = df['flag']

#### Verificação de variabilidade

Foi realizada análise de valores únicos por variável para garantir que os atributos possuam informação relevante para o modelo.

---

## Pré-processamento dos Dados

O pré-processamento foi realizado utilizando Pipeline e ColumnTransformer do Scikit-Learn, garantindo reprodutibilidade e evitando vazamento de dados.

### As transformações aplicadas foram:

#### Tratamento de valores ausentes

Valores faltantes foram substituídos pela média da variável.

    SimpleImputer(strategy='mean')
    
#### Padronização dos dados

Aplicação do StandardScaler para normalizar a escala das variáveis.

    StandardScaler()
    
Pipeline de Pré-processamento

Imputação → Padronização → Modelo

Isso garante que todas as etapas sejam executadas automaticamente durante o treinamento e previsão.

---

##  Divisão Treino e Teste

O conjunto de dados foi dividido em:

80% treino | 20% teste

Utilizando estratificação para preservar a proporção de fraudes no dataset.

    train_test_split(stratify=y)

---

##  Modelo de Machine Learning

O algoritmo escolhido foi o XGBoost (Extreme Gradient Boosting), amplamente utilizado em problemas de classificação devido à sua alta performance e robustez.

* Configuração do modelo:

        XGBClassifier(
            random_state=42,
            eval_metric='auc',
            objective='binary:logistic'
        )

O modelo foi integrado ao pipeline para garantir que todo o fluxo de transformação seja aplicado automaticamente.

---

##  Avaliação do Modelo

A principal métrica utilizada foi AUC (Area Under the ROC Curve).

Essa métrica mede a capacidade do modelo de distinguir entre:

transações legítimas | transações fraudulentas

Valores de AUC próximos de 1 indicam excelente capacidade de classificação.

---

##  Pipeline Final

O pipeline completo inclui:

1️⃣ Pré-processamento

2️⃣ Treinamento do modelo

3️⃣ Predição automática

Isso permite que novos dados sejam processados da mesma forma que os dados de treinamento.

---

##  Uso do Modelo em Produção

Após o treinamento, o modelo pode ser salvo para uso em sistemas reais.

    joblib.dump(pipeline_final, 'modelo_fraude.joblib')

Posteriormente pode ser carregado para realizar previsões em novas transações.

    modelo = joblib.load('modelo_fraude.joblib')

---

##  Aplicações do Projeto

**Este tipo de modelo pode ser utilizado em diversos contextos:**

Sistemas antifraude em criptomoedas

Monitoramento de carteiras suspeitas em redes blockchain.

Bancos e fintechs

Detecção de padrões de fraude em transferências financeiras.

Exchanges de criptomoedas

Identificação de contas com comportamento suspeito.

Monitoramento de risco financeiro

Classificação automática de atividades potencialmente fraudulentas.

----

##  Conclusão

Este projeto demonstrou a construção de um sistema de detecção de fraudes utilizando técnicas modernas de Machine Learning e engenharia de dados.

A utilização de pipelines do Scikit-Learn garante um fluxo robusto, reprodutível e pronto para integração em sistemas reais.

A metodologia aplicada pode ser facilmente adaptada para diversos problemas de classificação, tornando o modelo uma base sólida para aplicações em segurança financeira e análise de risco.




# 👨‍💻 Autor

**Leonardo Sales**

📊 Analista de Dados / Cientista de Dados em formação
💻 Projetos de Machine Learning e Análise de Dados

GitHub: Portfólio de projetos em Data Science

---

