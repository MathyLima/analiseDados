# Análise dos Dados de Preço de Casas

## Introdução

Neste documento, apresento as conclusões de minha análise exploratória e de regressão sobre os dados de preços de casas da Califórnia.

## Dados

Os dados analisados incluem informações sobre várias características das casas, como número médio de quartos, renda média dos residentes, e número médio de ocupantes.

## Análise Exploratória

### Correlação de Pearson

- **AveRooms:** A correlação de Pearson mostrou uma relação linear positiva entre o número médio de quartos (`AveRooms`) e o preço da casa. Isso sugere que, em geral, mais quartos estão associados a preços mais altos.

- **MedInc:** A correlação de Pearson também revelou uma relação positiva significativa entre a renda média (`MedInc`) e o preço da casa. Isto indica que, à medida que a renda média aumenta, o preço das casas também tende a aumentar.

- **AveOccup:** A correlação com o número médio de ocupantes (`AveOccup`) não foi tão forte quanto com `AveRooms` e `MedInc`.

## Regressão Linear Simples

### Modelo com `AveRooms`

- **Mean Squared Error (MSE):** 1.15a
- **R^2 Score:** 0.093
- **Coeficiente:** -0.465
- **Intercepto:** 3.405

Esses resultados indicam um ajuste ruim do modelo quando considerado apenas o número médio de quartos. A correlação positiva foi contradita pelo coeficiente negativo.

## Regressão Linear Múltipla

### Modelo com `MedInc`, `AveRooms`, e `AveOccup`

- **Mean Squared Error (MSE):** 0.573
- **R^2 Score:** 0.552
- **Coeficiente:**
  - **MedInc:** 0.532
  - **AveRooms:** -0.247
  - **AveOccup:** -0.397
- **Intercepto:** 2.520

Neste modelo, a renda média (`MedInc`) mostrou um efeito positivo significativo no preço da casa, enquanto o número médio de quartos (`AveRooms`) e o número médio de ocupantes (`AveOccup`) apresentaram efeitos negativos. 

## Conclusões

1. **Renda Média e Número de Quartos:** A análise revelou que a renda média e o número de quartos são fatores importantes que influenciam o preço das casas. A renda média teve um efeito positivo significativo, enquanto o número de quartos, quando controlado por outras variáveis, teve um efeito negativo no preço.

2. **Efeito do Número de Quartos:** Apesar da correlação positiva entre o número médio de quartos e o preço, o modelo de regressão linear múltipla indicou um efeito negativo. Isso pode ser devido à multicolinearidade ou outros fatores não capturados pelo modelo.

## Próximos Passos

- **Exploração de Interações:** Investigar se há interações entre as variáveis que podem explicar melhor os resultados.
- **Análise de Resíduos:** Verificar os resíduos do modelo para identificar possíveis padrões ou problemas.
- **Validação Cruzada:** Testar o modelo em diferentes subconjuntos de dados para garantir a robustez dos resultados.

## Referências

- Dados do [California Housing Dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_california_housing.html)
