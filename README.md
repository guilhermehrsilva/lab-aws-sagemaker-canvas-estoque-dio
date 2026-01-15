# 📊 Previsão de Estoque Inteligente na AWS com SageMaker Canvas

## 🎯 Objetivo do Projeto
Desenvolver um modelo de previsão de estoque (*Time Series Forecasting*) utilizando o Amazon SageMaker Canvas para otimizar o planejamento logístico e evitar rupturas de estoque. Este projeto faz parte do bootcamp da DIO.

## 🛠️ Tecnologias Utilizadas
* **Amazon SageMaker Canvas:** Para construção de modelos de Machine Learning *no-code*.
* **Dataset de Varejo:** Dados históricos de vendas, promoções e preços.

## 🚀 Passo a Passo da Implementação

### 1. Seleção e Tratamento dos Dados
Importei um dataset contendo histórico de vendas com as seguintes variáveis principais:
* `ID_PRODUTO`: Identificador único do item.
* `DATA_EVENTO`: Data da venda (Série Temporal).
* `PRECO`: Valor unitário do produto.
* `QUANTIDADE_ESTOQUE`: Variável alvo (Target) a ser prevista.

### 2. Construção do Modelo (Build)
Configurei o SageMaker Canvas para um problema de *Time Series Forecasting*, definindo uma janela de previsão futura (forecast horizon). O modelo foi treinado utilizando o modo **Quick Build** para validação rápida de hipóteses.

### 3. Análise de Performance (Metrics)
O modelo alcançou métricas excelentes, indicando alta confiabilidade nas previsões:

![Print das Métricas](imagens/Captura de tela_15-1-2026_102232_sqvguqgzwcpzqtz.studio.us-east-2.sagemaker.aws.jpeg)

* **Avg. wQL (Weighted Quantile Loss):** 0.060 (Quanto menor, melhor. Este valor indica alta precisão).
* **MAPE (Mean Absolute Percentage Error):** 0.148 (A margem de erro média do modelo é de ~14%).
* **Impacto das Variáveis:** O `PRECO` foi identificado como o fator mais crítico, influenciando 9.61% no comportamento do estoque.

### 4. Resultados e Previsões (Predict)
Realizei uma simulação de previsão para um item específico (`Single Prediction`). O gráfico abaixo demonstra os cenários gerados pelo modelo (P10, P50 e P90):

![Print do Gráfico](caminho_para_sua_imagem_do_grafico.png)

* **Análise:** O modelo previu uma tendência de queda na demanda para o item selecionado nos dias subsequentes (08/02 a 09/02), sugerindo uma gestão de estoque conservadora para este período.

## 結論 (Conclusão)
A utilização do SageMaker Canvas permitiu criar um modelo preditivo robusto sem a necessidade de codificação complexa, acelerando a entrega de valor para a área de negócios. A precisão obtida (wQL de 0.060) demonstra que a ferramenta é viável para aplicações reais de planejamento de demanda.

---
*Desenvolvido por: Guilherme Risson*
