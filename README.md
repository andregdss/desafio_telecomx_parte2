# Desafio: Previsão de Evasão de Clientes (Churn) – Telecom X (Parte 2)

Este repositório contém o projeto de **Data Science e Machine Learning** desenvolvido como parte de um *Challenge* da plataforma **Alura**, com foco na **análise e previsão da evasão de clientes (churn)** em uma empresa de telecomunicações fictícia chamada **Telecom X**.

O projeto dá continuidade à etapa de tratamento e análise exploratória dos dados (Parte 1), avançando para **análises estatísticas aprofundadas, engenharia de atributos, modelagem preditiva e comparação de algoritmos**, com o objetivo de apoiar **estratégias de retenção de clientes baseadas em dados**.

---

## 🎯 Objetivo do Projeto

O objetivo principal deste projeto é **prever a evasão de clientes da Telecom X**, além de identificar os fatores que mais influenciam esse comportamento, permitindo ações preventivas e estratégicas.

Especificamente, o projeto busca:

- Analisar estatisticamente os fatores associados ao churn;
- Tratar multicolinearidade e preparar os dados para modelagem;
- Construir e avaliar diferentes modelos de Machine Learning;
- Comparar modelos com base em métricas adequadas para dados desbalanceados;
- Traduzir os resultados em **insights de negócio acionáveis**.

---

## 💾 Fonte de Dados

O conjunto de dados utilizado corresponde à base **já tratada na Parte 1 do desafio**, disponibilizada publicamente pela Alura e armazenada em formato CSV.

- Total de registros: **7.032 clientes**
- Variável alvo: **Evasao**  
  - `0` → Cliente não evadiu  
  - `1` → Cliente evadiu  

O dataset contém informações relacionadas a:

- Dados demográficos (gênero, cidadão sênior, parceiro, dependentes);
- Serviços contratados (telefone, internet, streaming, suporte);
- Informações contratuais (tipo de contrato, método de pagamento);
- Dados financeiros (cobranças mensais, gasto total);
- Tempo de permanência do cliente.

---

## 🛠️ Metodologia e Etapas

O projeto foi desenvolvido em um **Notebook Google Colab**, utilizando Python, e seguiu as seguintes etapas principais:

### 1. Preparação e Entendimento dos Dados (📌 Preparação)

- Importação das bibliotecas principais (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Statsmodels);
- Carregamento da base de dados tratada;
- Análise da estrutura do dataset e verificação de valores ausentes.

---

### 2. Tratamento e Engenharia de Variáveis (🔧 Transformação)

- Agrupamento semântico de categorias equivalentes (ex.: “Sem serviço” e “Não”);
- Remoção de colunas sem poder preditivo (`ID_cliente`);
- Aplicação de **One-Hot Encoding** nas variáveis categóricas;
- Conversão de variáveis booleanas para formato binário (0/1).

---

### 3. Análise Estatística e Exploratória (📊 Análise)

- Avaliação da proporção de churn (≈ 27%);
- Análise de correlação entre variáveis;
- Ranking das variáveis mais correlacionadas com a evasão;
- Identificação de padrões associados a churn.

---

### 4. Análise de Multicolinearidade (📐 VIF)

- Cálculo do **Variance Inflation Factor (VIF)**;
- Identificação de multicolinearidade extrema em variáveis financeiras;
- Remoção estratégica de variáveis com VIF elevado;
- Reavaliação da estabilidade do dataset final.

---

### 5. Modelagem Preditiva (🤖 Machine Learning)

Foram construídos e avaliados os seguintes modelos:

- **Random Forest** (com balanceamento via SMOTE);
- **XGBoost** (com ajuste de `scale_pos_weight`);
- **Regressão Logística** (com `class_weight='balanced'`);
- **Ridge Classifier** (modelo linear regularizado).

---

### 6. Avaliação dos Modelos (📈 Avaliação)

Os modelos foram avaliados utilizando métricas adequadas para dados desbalanceados:

- Accuracy;
- Precision;
- Recall;
- F1-score;
- ROC AUC;
- Matrizes de confusão;
- Curvas ROC e Precisão-Recall.

Também foi realizado:

- **Ajuste de limiar (threshold tuning)** focado em regras de negócio;
- **Validação cruzada estratificada (k-fold)** para garantir estabilidade.

---

## 📈 Principais Insights e Resultados

Os principais achados do projeto foram:

- **Tempo de contrato** é o principal fator de retenção;
- Clientes com **contrato mensal** apresentam maior risco de churn;
- Clientes com **alto gasto acumulado** têm até **3 vezes mais chance de evasão**;
- Métodos de pagamento como **cheque eletrônico** estão associados a maior churn;
- Serviços de valor agregado (suporte técnico, segurança online) reduzem a evasão;
- Modelos preditivos conseguem identificar **mais de 80% dos churns reais**.

---

## 🚀 Recomendações de Negócio

Com base nos resultados, recomenda-se:

- Incentivar migração para contratos de longo prazo (anual e bienal);
- Atuar preventivamente nos primeiros meses de contrato;
- Criar campanhas específicas para clientes com alto gasto acumulado;
- Reforçar o valor percebido de serviços adicionais;
- Utilizar modelos preditivos como ferramenta contínua de retenção.

---

## 💻 Como Executar o Notebook

O notebook pode ser executado diretamente no **Google Colab**:

1. Abra o arquivo `.ipynb` deste repositório;
2. Clique em **“Executar todas as células”**;
3. As bibliotecas necessárias serão importadas automaticamente;
4. Os resultados, gráficos e métricas serão gerados em sequência.

---

## 📌 Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Statsmodels
- XGBoost
- Google Colab

---

## 📄 Observação Final

Este projeto demonstra uma aplicação completa do **ciclo de Data Science**, integrando estatística, machine learning e interpretação de resultados, com foco em **decisão orientada a dados** e **impacto real no negócio**.
