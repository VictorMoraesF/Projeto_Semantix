# Projeto_Semantix

"""# Previsão de Cancelamento de Clientes (Churn)

Este repositório contém o projeto de Machine Learning desenvolvido para identificar clientes com alto risco de evasão, migrando a estratégia da empresa de uma abordagem reativa para preditiva.

## 1. Coleta e Preparação de Dados
A base de dados utilizada foi a **Telco Customer Churn**. O dataset original conta com 7.043 registros e variáveis descritivas do comportamento do usuário.
- **Limpeza:** A coluna `customerID` foi removida. A variável `TotalCharges` foi corrigida para numérico, e os valores nulos foram eliminados.
- **Transformação:** O alvo preditivo (`Churn`) foi binarizado. As demais características categóricas foram tratadas com *One-Hot Encoding*.

## 2. Modelagem
Os dados foram segmentados em **70% para Treino e 30% para Teste**. O algoritmo escolhido foi o **Random Forest Classifier (Floresta Aleatória)**:
- **Ensemble:** 100 árvores de decisão.
- **Balanceamento:** Uso do parâmetro `class_weight='balanced'` para garantir sensibilidade à classe minoritária.
- **Profundidade:** Limitada a 5 níveis para evitar *overfitting*.

## 3. Visualização dos Resultados
Abaixo está a Matriz de Confusão do modelo, gerada sobre a base de testes (2.110 clientes).

![Matriz de Confusão](confusion_matrix.png)

*O modelo atingiu uma Acurácia Global de 74%, com destaque para **80% de Recall (Sensibilidade)** na classe alvo (clientes evadidos).*

## 4. Conclusões e Decisão de Negócio
A modelagem atende integralmente ao objetivo de **antecipar o problema**. Com 80% de Recall, a cada 10 clientes prestes a cancelar o contrato, o algoritmo alerta sobre 8 deles. 

Financeiramente, a precisão alcançada (51%) significa que metade das ações preventivas será direcionada a clientes que efetivamente sairiam, enquanto a outra metade são "alarmes falsos". Como o custo de realizar uma ação de retenção é drasticamente inferior ao Custo de Aquisição de Clientes (CAC) necessário para repor um assinante, o uso desta inteligência justifica-se como um mecanismo de proteção de receita altamente rentável.
"""
