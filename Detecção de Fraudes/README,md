# 📊 Relatório Final do Projeto
Detecção de Fraudes em Transações de Criptomoedas com Machine Learning
1. Introdução

O crescimento das transações em criptomoedas trouxe novas oportunidades financeiras, mas também aumentou significativamente os riscos de fraudes e atividades maliciosas. Sistemas automatizados capazes de identificar padrões suspeitos são essenciais para reduzir perdas financeiras e aumentar a segurança das transações.

Este projeto tem como objetivo desenvolver um modelo de Machine Learning capaz de identificar transações fraudulentas em redes de criptomoedas, utilizando técnicas de engenharia de atributos, pré-processamento de dados e algoritmos de classificação.

O modelo foi construído utilizando Python, Scikit-Learn e XGBoost, integrando todas as etapas de processamento em um pipeline automatizado de Machine Learning.

2. Objetivos do Projeto

O projeto possui os seguintes objetivos principais:

Detectar automaticamente transações fraudulentas.
Criar um pipeline de Machine Learning automatizado.
Aplicar boas práticas de pré-processamento de dados.
Construir um modelo escalável que possa ser utilizado em produção.
Demonstrar um fluxo completo de Data Science aplicado a problemas reais.
3. Conjunto de Dados

O dataset utilizado contém informações sobre transações realizadas em blockchain, incluindo características como:

número de transações enviadas e recebidas
tempo entre transações
valores mínimos e máximos transferidos
quantidade de contratos criados
saldo total da carteira
interações com tokens ERC20

Essas variáveis descrevem o comportamento financeiro de cada endereço na blockchain, permitindo identificar padrões associados a atividades fraudulentas.

A variável alvo utilizada foi:

flag

Onde:

0 → transação legítima
1 → transação fraudulenta
4. Engenharia de Atributos

Durante a etapa de engenharia de atributos foram realizadas as seguintes operações:

Limpeza dos nomes das colunas

Padronização para evitar inconsistências durante o processamento.

df.columns = df.columns.str.strip().str.lower()
Seleção de atributos

Foram removidas variáveis irrelevantes ou redundantes.

X = df[atributos]
y = df['flag']
Verificação de variabilidade

Foi realizada análise de valores únicos por variável para garantir que os atributos possuam informação relevante para o modelo.

5. Pré-processamento dos Dados

O pré-processamento foi realizado utilizando Pipeline e ColumnTransformer do Scikit-Learn, garantindo reprodutibilidade e evitando vazamento de dados.

As transformações aplicadas foram:

Tratamento de valores ausentes

Valores faltantes foram substituídos pela média da variável.

SimpleImputer(strategy='mean')
Padronização dos dados

Aplicação do StandardScaler para normalizar a escala das variáveis.

StandardScaler()
Pipeline de Pré-processamento
Imputação → Padronização → Modelo

Isso garante que todas as etapas sejam executadas automaticamente durante o treinamento e previsão.

6. Divisão Treino e Teste

O conjunto de dados foi dividido em:

80% treino
20% teste

Utilizando estratificação para preservar a proporção de fraudes no dataset.

train_test_split(stratify=y)
7. Modelo de Machine Learning

O algoritmo escolhido foi o XGBoost (Extreme Gradient Boosting), amplamente utilizado em problemas de classificação devido à sua alta performance e robustez.

Configuração do modelo
XGBClassifier(
    random_state=42,
    eval_metric='auc',
    objective='binary:logistic'
)

O modelo foi integrado ao pipeline para garantir que todo o fluxo de transformação seja aplicado automaticamente.

8. Avaliação do Modelo

A principal métrica utilizada foi AUC (Area Under the ROC Curve).

Essa métrica mede a capacidade do modelo de distinguir entre:

transações legítimas
transações fraudulentas

Valores de AUC próximos de 1 indicam excelente capacidade de classificação.

9. Pipeline Final

O pipeline completo inclui:

1️⃣ Pré-processamento
2️⃣ Treinamento do modelo
3️⃣ Predição automática

Isso permite que novos dados sejam processados da mesma forma que os dados de treinamento.

10. Uso do Modelo em Produção

Após o treinamento, o modelo pode ser salvo para uso em sistemas reais.

joblib.dump(pipeline_final, 'modelo_fraude.joblib')

Posteriormente pode ser carregado para realizar previsões em novas transações.

modelo = joblib.load('modelo_fraude.joblib')
11. Aplicações do Projeto

Este tipo de modelo pode ser utilizado em diversos contextos:

Sistemas antifraude em criptomoedas

Monitoramento de carteiras suspeitas em redes blockchain.

Bancos e fintechs

Detecção de padrões de fraude em transferências financeiras.

Exchanges de criptomoedas

Identificação de contas com comportamento suspeito.

Monitoramento de risco financeiro

Classificação automática de atividades potencialmente fraudulentas.

12. Como Adaptar para Outros Projetos

A estrutura do projeto é genérica e reutilizável.

Para adaptar para outros problemas basta:

1️⃣ Alterar o dataset

Substituir os dados de entrada.

2️⃣ Alterar a variável alvo

Exemplo:

fraude
inadimplencia
churn
cancelamento
3️⃣ Ajustar os atributos

Selecionar novas variáveis relevantes.

4️⃣ Trocar o algoritmo se necessário

Exemplos:

Random Forest
Logistic Regression
LightGBM
CatBoost
5️⃣ Ajustar métricas de avaliação

Dependendo do problema:

AUC
F1 Score
Precision
Recall
13. Possíveis Melhorias Futuras

O projeto pode ser aprimorado com:

Feature importance
ROC Curve
Cross Validation
Grid Search para otimização de hiperparâmetros
Balanceamento de classes (SMOTE ou class weights)
Deploy com API (FastAPI ou Flask)
14. Conclusão

Este projeto demonstrou a construção de um sistema de detecção de fraudes utilizando técnicas modernas de Machine Learning e engenharia de dados.

A utilização de pipelines do Scikit-Learn garante um fluxo robusto, reprodutível e pronto para integração em sistemas reais.

A metodologia aplicada pode ser facilmente adaptada para diversos problemas de classificação, tornando o modelo uma base sólida para aplicações em segurança financeira e análise de risco.

✅ Se quiser, eu também posso te ajudar a criar:

README de GitHub nível profissional
visualizações (ROC Curve + Feature Importance)
versão desse projeto que impressiona recrutadores

Porque esse projeto já está a 80% de virar um portfólio muito forte.
