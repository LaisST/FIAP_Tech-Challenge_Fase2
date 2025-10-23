# FIAP Tech Challenge – Fase 2

Projeto desenvolvido como parte do curso de pós-graduação da FIAP, com foco em análise de dados financeiros e aplicação de modelos de Machine Learning para previsão de movimentos do mercado.

---

## Objetivo

Este projeto tem como objetivo analisar dados históricos do IBOVESPA e construir modelos de Machine Learning capazes de prever se o fechamento do dia seguinte será maior ou menor que o do dia atual.

---

## Bibliotecas Utilizadas

- **Manipulação de dados**: `numpy`, `pandas`  
- **Visualização**: `matplotlib.pyplot`, `seaborn`  
- **Modelagem e treino**:
  - `sklearn.model_selection` → `train_test_split`
  - `sklearn.naive_bayes` → `GaussianNB`
  - `sklearn.ensemble` → `RandomForestClassifier`
  - `sklearn.neighbors` → `KNeighborsClassifier`
  - `sklearn.pipeline` → `Pipeline`
  - `sklearn.svm` → `LinearSVC`
- **Escalonamento**: `StandardScaler`, `MinMaxScaler`  
- **Validação**: `accuracy_score`  

---

## Coleta e Preparação dos Dados

Os dados foram carregados a partir de um arquivo CSV contendo informações diárias do IBOVESPA entre setembro de 2023 e setembro de 2025. As colunas incluem: data, preço de abertura, fechamento, máxima, mínima, volume e variação percentual.

**Fonte dos dados**: [Investing.com](https://br.investing.com/indices/bovespa-historical-data)

---

## Pré-Processamento

- Conversão de tipos de dados  
- Limpeza de valores nulos e duplicados  
- Correção de colunas com mistura de texto e números  

---

## Análise Exploratória (EDA)

A análise exploratória permitiu entender o comportamento do mercado e orientar a criação de features relevantes:

- Identificação de outliers  
- Correlação entre variáveis  
- Tendências, volatilidade e sazonalidade  

---

## Criação da Target e Features

- **Target**: A target (ou variável-alvo) é o resultado que queremos prever  
- **Features**: As features são as características ou informações de entrada utilizadas pelo modelo para aprender padrões

---

## Separação da Base para Treino e Teste

A divisão respeitou a ordem cronológica dos dados:

- **Treino**: todos os dados, exceto os últimos 30 dias  
- **Teste**: últimos 30 dias da série temporal  

---

## Modelos Preditivos

### Random Forest Classifier  
Conjunto de árvores de decisão que votam para definir a classe final. Robusto contra overfitting e eficaz na captura de interações entre variáveis.

### KNN (K-Nearest Neighbors)  
Classifica com base nos vizinhos mais próximos. Simples, intuitivo e útil quando a proximidade entre exemplos é relevante.

### SVM (Support Vector Machine)  
Encontra o hiperplano que melhor separa as classes, maximizando a margem. Alta precisão e bom desempenho em dados complexos.

### Naive Bayes  
Baseado no Teorema de Bayes, assume independência entre variáveis. Rápido, simples e eficaz em padrões estatísticos claros.

---

## Conclusão

O modelo escolhido foi o  **KNN Classifier (K=3)**, pois obteve acurácia de **70%**, representando um resultado consistente diante da volatilidade do mercado. O modelo mostrou bom equilíbrio entre simplicidade e desempenho, destacando o impacto das variáveis de retorno, volatilidade e médias móveis.

**Limitações**: A previsão é afetada por ruídos e eventos imprevisíveis do mercado financeiro, o que restringe a precisão dos modelos.

---

Autora: Lais Costa Santos Teixeira

Curso: Pós-graduação Data Analytics – FIAP

Ano: 2025

