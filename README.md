
# Challenge Telecom X: análise de evasão de clientes - Parte 2

## 📝 Descrição do Projeto

Este projeto de Data Science realiza uma análise completa para identificar os fatores-chave que levam um cliente a cancelar seus serviços e, a partir disso, construir um modelo de machine learning capaz de prever essa evasão. Com base nos insights gerados, o projeto finaliza com a proposição de estratégias de negócio focadas na retenção de clientes.

## 🎯 Objetivos

  * Preparar os dados para a modelagem (tratamento, encoding, normalização).

  * Realizar análise de correlação e seleção de variáveis.

  * Treinar dois ou mais modelos de classificação.

  * Avaliar o desempenho dos modelos com métricas.

  * Interpretar os resultados, incluindo a importância das variáveis.

## 📊 Dataset

O estudo foi realizado com base no arquivo `dados_tratados.csv`, que contém dados anonimizados de clientes da TelecomX. As informações no dataset incluem:

  * **Dados Demográficos:** Gênero, se é cidadão sênior, se possui parceiro ou dependentes.
  * **Informações do Contrato:** Tempo de serviço (em meses), tipo de contrato, método de pagamento e faturamento eletrônico.
  * **Serviços Contratados:** Telefonia, múltiplas linhas, serviço de internet (DSL ou Fibra Ótica), e serviços adicionais como segurança online, backup, suporte técnico e streaming.
  * **Dados Financeiros:** Cobrança mensal e cobrança total.

## 🛠️ Metodologia

1.  **Preparação e Limpeza dos Dados:**

      * Carregamento dos dados a partir de um arquivo CSV.
      * Remoção da coluna de `ID` do cliente, por não ter valor preditivo.
      * Codificação de variáveis categóricas (One-Hot Encoding) para transformar dados textuais em formato numérico.
      * Codificação da variável alvo `Evasao` para o formato binário (0 para "Não" e 1 para "Sim").

2.  **Análise Exploratória de Dados (EDA):**

      * Análise da proporção de evasão, identificando um desequilíbrio de classes (26.6% de evasão).
      * Análise de correlação para medir a relação linear entre as variáveis e a evasão.
      * Criação de visualizações (histogramas e box plots) para aprofundar o entendimento sobre os fatores mais impactantes, como o tipo de contrato e o tempo de serviço.

3.  **Modelagem Preditiva:**

      * Os dados foram divididos em conjuntos de **treino (70%)** e **teste (30%)** de forma estratificada.
      * Foram treinados e avaliados três modelos de classificação:
          * **Dummy Classifier:** Modelo de base para estabelecer um benchmark de performance.
          * **Árvore de Decisão:** Modelo simples e interpretável, com profundidade controlada para evitar overfitting.
          * **K-Nearest Neighbors (KNN):** Modelo baseado em distância, que exigiu a normalização dos dados (MinMaxScaler) para um desempenho justo.

4.  **Avaliação dos Modelos:**

      * Os modelos foram comparados utilizando as seguintes métricas, adequadas para cenários com classes desbalanceadas:
          * **Acurácia:** Percentual geral de acertos.
          * **Precisão:** Dentre as previsões de evasão, quantas estavam corretas.
          * **Recall (Revocação):** Dos clientes que realmente evadiram, quantos o modelo conseguiu identificar.
          * **F1-Score:** Média harmônica entre Precisão e Recall.
      * Matrizes de confusão foram geradas para cada modelo para uma análise visual dos erros e acertos.

## 📈 Principais Resultados e Descobertas

  * **Fatores de Maior Risco de Evasão:**

      * **Tipo de Contrato:** Clientes com contrato **mensal (Month-to-month)** são, de longe, os mais propensos a cancelar.
      * **Tempo de Serviço:** Clientes com **pouco tempo de casa** (baixo tempo de serviço) têm uma taxa de churn muito maior.
      * **Cobrança Mensal:** Faturas com **valores mensais mais altos** estão associadas a uma maior evasão.
      * **Serviço de Internet:** O serviço de **Fibra Ótica** apresentou uma correlação positiva com o churn, sugerindo uma necessidade de investigação sobre preço ou qualidade.

  * **Fatores de Maior Retenção:**

      * **Contratos de Longo Prazo:** Contratos de **1 ou 2 anos** são os mais fortes indicadores de lealdade.
      * **Tempo de Serviço Elevado:** Clientes com mais tempo de contrato tendem a permanecer fiéis.
      * **Serviços Adicionais:** A contratação de **suporte técnico** mostrou ter uma correlação negativa com a evasão.

O modelo **KNN** se destacou com o melhor **F1-Score (52.9%)** e **Recall (51.3%)**, sendo o mais indicado para identificar o maior número possível de clientes em risco de evasão.

## 🚀 Como Executar o Projeto

Para replicar esta análise, siga os passos abaixo:

**1. Pré-requisitos:**
baixar o arquivo `telecomX_part2.ipynb` no drive para usar o Google Colab.


**3. Bibliotecas:**

```
pandas
scikit-learn
plotly
seaborn
matplotlib
numpy
```

**4. Execução:**
Abra o arquivo `telecomX_part2.ipynb` no Google Colab. Execute as células sequencialmente para reproduzir todo o processo de análise e modelagem.

## 👤 Autor

  * **[Ana Clara Moura Sander]**
  * **[anaclaramourasanders@gmail.com]**
