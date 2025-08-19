# Projeto de Previsão de Churn com Machine Learning - Telecom X

## Objetivo de Negócio
Este projeto foi desenvolvido como parte do bootcamp da Alura com o objetivo de construir um modelo de Machine Learning capaz de prever quais clientes da empresa fictícia "Telecom X" têm a maior probabilidade de cancelar seus serviços (churn). O objetivo é permitir que a empresa tome ações de retenção proativas e direcionadas.

---

## 🛠️ Metodologia Aplicada
O projeto foi dividido em um pipeline completo de Machine Learning, cobrindo as seguintes etapas:

1.  **Limpeza e Tratamento de Dados:** Correção de tipos de dados, tratamento de valores ausentes e padronização de informações.
2.  **Análise Exploratória (EDA):** Investigação visual dos dados para entender o perfil dos clientes que cancelam, utilizando gráficos de distribuição e boxplots para identificar as principais variáveis relacionadas ao churn, como **Tempo de Contrato** e **Gasto Total**.
3.  **Pré-processamento:**
    *   **Encoding:** Transformação de variáveis categóricas em numéricas usando One-Hot Encoding.
    *   **Balanceamento de Classes:** Aplicação da técnica **SMOTE** no conjunto de treino para corrigir o desequilíbrio entre clientes que cancelam e os que permanecem, garantindo que o modelo aprendesse os padrões de ambos os grupos.
    *   **Padronização:** Normalização das variáveis numéricas com `StandardScaler` para otimizar o desempenho de modelos sensíveis à escala.
4.  **Modelagem e Avaliação:**
    *   Foram treinados dois modelos de classificação: **Regressão Logística** (como baseline) e **Random Forest**.
    *   A avaliação foi focada em métricas adequadas para dados desbalanceados, com ênfase no **Recall** para a classe de churn.

---

## 📊 Resultados e Modelo Escolhido
Após a avaliação, o modelo de **Regressão Logística foi selecionado como a melhor solução para o problema de negócio**.

| Métrica         | Regressão Logística | Random Forest |
| --------------- | ------------------- | ------------- |
| Acurácia        | 76%                 | 77%           |
| **Recall (Churn)**  | **67%**             | 62%           |
| Precisão (Churn)  | 54%                 | 57%           |
| F1-Score (Churn)  | 0.60                | 0.59          |

A escolha foi baseada no **Recall superior (67%)**, indicando que este modelo é mais eficaz em identificar a maioria dos clientes que realmente estão em risco de cancelar, o que é crucial para o objetivo de retenção da empresa.

---

## 💡 Principais Insights e Conclusões
A análise e o modelo nos permitiram identificar os principais fatores que influenciam a evasão de clientes:

*   **🏆 Fator de Retenção Mais Forte:** O **Tempo de Contrato** é o principal indicador de lealdade. Clientes de longa data raramente cancelam.
*   **🚨 Maior Fator de Risco:** Clientes com **contratos mensais (`Month-to-month`)** representam o maior risco de churn.
*   **💰 Fatores Financeiros:** **Gastos mensais elevados**, especialmente quando combinados com o serviço de **Fibra Óptica**, e o pagamento via **Cheque Eletrônico** estão fortemente associados a maiores taxas de cancelamento.

**Recomendação Estratégica:** A Telecom X deve focar suas campanhas de retenção em clientes novos com contratos mensais, oferecendo incentivos para a migração para contratos de 1 ou 2 anos.

---

## 💻 Como Executar o Projeto
1. Clone este repositório.
2. Instale as bibliotecas necessárias: `pandas`, `scikit-learn`, `seaborn`, `matplotlib`, `imbalanced-learn`.
3. Execute o notebook Jupyter `nome_do_seu_notebook.ipynb`. O conjunto de dados `telecom_x_dados_tratados.csv` já está incluído.
