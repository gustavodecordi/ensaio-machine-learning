# Ensaio de Machine Learning

## Descrição

Como parte das atividades de conclusão da disciplina **"Fundamentos de Machine Learning"** da **Comunidade de Ciência de Dados (CDS)**, foi proposto um ensaio prático considerando o seguinte cenário fictício: a empresa Data Money acredita que o sucesso na entrega de ótimos resultados aos seus clientes é atribuído à expertise de seus Cientistas de Dados, especialmente no treinamento e ajuste fino dos algoritmos de **Machine Learning**.

## Objetivo

O projeto tem como objetivo realizar ensaios com algoritmos de Classificação, Regressão e Clusterização, buscando entender como a variação dos principais hiperparâmetros influencia o desempenho dos modelos, particularmente no controle de *overfitting* e *underfitting*.
Esses ensaios visam estudar os impactos potenciais da alteração de hiperparâmetros nas métricas de performance, fornecendo *insights* sobre o comportamento dos algoritmos diante dessas mudanças.

# Planejamento da solução

## Produto final

O produto final consistirá em 7 tabelas que apresentam o desempenho dos algoritmos, avaliados por meio de múltiplas métricas, aplicadas a três conjuntos de dados distintos: treinamento, validação e teste.

## Algoritmos ensaiados

### Classificação:
- **Algoritmos**: K-Nearest Neighbors, Decision Tree, Random Forest e Logistic Regression.
- **Métricas de performance**: Accuracy, Precision, Recall e F1-Score.

### Regressão:
- **Algoritmos**: Linear Regression Lasso, Linear Regression Ridge, Linear Regression Elastic Net,
  Decision Tree Regressor, Random Forest Regressor e Polynomial Regression.
- **Métricas de performance**: R2, MSE, RMSE, MAE e MAPE.

### Clusterização:
- **Algoritmos**: K-Means e Affinity Propagation.
- **Métricas de performance**: Silhouette Score.

## Ferramentas utilizadas
**Python 3.9.12**, **Pandas 2.0.1**, **Numpy 1.23.5** e **Scikit-learn 1.5.1**.

# Desenvolvimento

## Estratégia da solução

Para conduzir os ensaios com os algoritmos de *Machine Learning*, utilizarei a biblioteca Scikit-learn, uma das mais populares ferramentas em Python para aprendizado de máquina. O objetivo será identificar o algoritmo com melhor desempenho, ajustando diferentes modelos com diversas configurações de hiperparâmetros. A meta é encontrar o equilíbrio ideal entre *overfitting* e *underfitting*, assegurando que o modelo tenha a melhor capacidade de generalização.

## O passo a passo

- **Passo 1**: Divisão dos dados em treino, teste e validação.

- **Passo 2**: Treinamento dos algoritmos com os dados de treinamento, utilizando os hiperparâmetros com os valores *dafault*.  Medir a performance dos algoritmos treinados

- **Passo 3**: Treinamento dos algoritmos com os dados de treinamento, utilizando os hiperparâmetros com os valores *dafault*. Medir a performance dos algoritmos treinados utilizando o conjunto de dados de validação.

- **Passo 4**: (Ajuste Fino) Alternar os valores dos principais hiperparâmetros que controlam o *overfitting* do algoritmo até encontrar o conjunto de hiperparâmetros que apresente a melhor performance dos algoritmos.

- **Passo 5**: Unir os dados de treinamento e validação.

- **Passo 6**: Retreinar o algoritmo com a união dos dados de treinamento e validação, utilizando os melhores valores para os hiperparâmetros.

- **Passo 7**: Medir a performance do algoritmo retreinado, utilizando o conjunto de dados de teste.

# Os top 3 Insights

### Insight Top 1
Os algoritmos de árvores apresentaram os melhores resultados baseados em todas as métricas de classificação utilizadas nos testes realizados.

### Insight Top 2
A performance dos algoritmos de classificação sobre os dados de validação ficou bem próxima da performance sobre os dados de teste. A similaridade entre as métricas de desempenho nos conjuntos de validação e teste sugere que os modelos não estão sobreajustados aos dados de treinamento.

### Insight Top 3
Os resultados dos algoritmos de regressão foram insatisfatórios, indicando a necessidade de aprimorar a seleção de atributos e o preparo das variáveis independentes.

# Resultados

## Ensaios de classificação:

<div align="center">

### Métricas - Treino
| Algorithm           |   Accuracy |   Precision |   Recall |   F1-Score |
|-------------------- |:----------:|:-----------:|:--------:|:----------:|
| K-Nearest Neighbors |     0.9476 |      0.9323 |   0.9786 |     0.9549 |
| Decision Tree       |     1      |      1      |   1      |     1      |
| Random Forest       |     1      |      1      |   1      |     1      |
| Logistic Regression |     0.8753 |      0.8785 |   0.905  |     0.8916 |


### Métricas - Validação
| Algorithm           |   Accuracy |   Precision |   Recall |   F1-Score |
|-------------------- |:----------:|:-----------:|:--------:|:----------:|
| K-Nearest Neighbors |     0.9252 |      0.9096 |   0.9638 |     0.9359 |
| Decision Tree       |     0.9444 |      0.9536 |   0.948  |     0.9508 |
| Random Forest       |     0.9622 |      0.9561 |   0.9783 |     0.967  |
| Logistic Regression |     0.8742 |      0.8777 |   0.9039 |     0.8906 |


### Métricas - Teste
| Algorithm           |   Accuracy |   Precision |   Recall |   F1-Score |
|-------------------- |:----------:|:-----------:|:--------:|:----------:|
| K-Nearest Neighbors |     0.9263 |      0.9058 |   0.9694 |     0.9366 |
| Decision Tree       |     0.9528 |      0.9471 |   0.9702 |     0.9585 |
| Random Forest       |     0.9631 |      0.9567 |   0.9785 |     0.9675 |
| Logistic Regression |     0.8711 |      0.873  |   0.9014 |     0.887  |

</div>

## Ensaios de regressão:

<div align="center">
  
### Métricas - Treino
| Algorithm                     |    R2   |   MSE   |   RMSE  |   MAE   |   MAPE |
|------------------------------ |:-------:|:-------:|:-------:|:-------:|:------:|
| Lasso Linear Regression       | 0.0074 | 474.475  | 21.7824 | 17.3055 | 8.7367 |
| Ridge Linear Regression       | 0.0461 | 455.996  | 21.3541 | 16.9983 | 8.6534 |
| Elastic Net Linear Regression | 0.0078 | 474.269  | 21.7777 | 17.2995 | 8.7323 |
| Decision Tree Regressor       | 0.9918 |   3.9404 |  1.985  |  0.2141 | 0.0826 |
| Random Forest Regressor       | 0.9028 |  46.4547 |  6.8158 |  4.8608 | 2.578  |
| Polynomial Regression         | 0.0942 | 432.986  | 20.8083 | 16.458  | 8.3505 |


### Métricas - Validação
| Algorithm                     |    R2   |   MSE   |   RMSE  |   MAE   |   MAPE |
|------------------------------ |:-------:|:-------:|:-------:|:-------:|:------:|
| Lasso Linear Regression       |  0.0079 | 473.747 | 21.7657 | 17.2649 | 8.6958 |
| Ridge Linear Regression       |  0.0399 | 458.445 | 21.4113 | 17.0395 | 8.6824 |
| Elastic Net Linear Regression |  0.0081 | 473.636 | 21.7632 | 17.2629 | 8.694  |
| Decision Tree Regressor       | -0.2971 | 619.381 | 24.8874 | 17.0926 | 7.1058 |
| Random Forest Regressor       |  0.3351 | 317.478 | 17.8179 | 13.0022 | 7.0309 |
| Polynomial Regression         |  0.0665 | 445.768 | 21.1132 | 16.7499 | 8.5479 |


### Métricas - Teste
| Algorithm                     |    R2   |   MSE   |   RMSE  |   MAE   |   MAPE |
|------------------------------ |:-------:|:-------:|:-------:|:-------:|:------:|
| Lasso Linear Regression       | 0.0101 | 482.006 | 21.9546 | 17.4522 | 8.7614 |
| Ridge Linear Regression       | 0.0511 | 461.999 | 21.4942 | 17.1427 | 8.5366 |
| Elastic Net Linear Regression | 0.0141 | 480.046 | 21.91   | 17.4165 | 8.7361 |
| Decision Tree Regressor       | 0.0905 | 442.848 | 21.044  | 16.8298 | 7.8832 |
| Random Forest Regressor       | 0.3972 | 293.492 | 17.1316 | 12.638  | 6.3788 |
| Polynomial Regression         | 0.0909 | 442.641 | 21.039  | 16.7364 | 8.277  |

</div>

## Ensaios de clusterização:

<div align="center">
  
### Métricas - ciclo 1 (antes de refinar o pré-processamento dos dados)

| Algorithm                | **Clusters encontrados** | **Average Silhouette Score** |
|--------------------------|:------------------------:|:----------------------------:|
| **K-Means**              | 3                        | 0.23157                      |
| **Affinity Propagation** | 7                        | 0.20366	                     |


### Métricas - ciclo 2 (depois de refinar o pré-processamento dos dados)

| Algorithm                | **Clusters encontrados** | **Average Silhouette Score** |
|--------------------------|:------------------------:|:----------------------------:|
| **K-Means**              | 3                        | 0.24452                      |
| **Affinity Propagation** | 5                        | 0.19128                      |

</div>

# Conclusão

Este ensaio permitiu aprofundar minha compreensão sobre os desafios de ajuste de modelos de machine learning, especialmente no que diz respeito aos estados de *underfitting* e *overfitting*.
Ao trabalhar com algoritmos baseados em árvores, como **Decision Tree** e **Random Forest**, constatei a importância da escolha adequada da profundidade máxima das árvores e do número de árvores na floresta. Parâmetros mal ajustados podem levar ao *overfitting*, comprometendo a capacidade de generalização do modelo.
Já nos algoritmos de regressão polinomial, o grau do polinômio exerce um papel crucial no balanceamento entre *underfitting* e *overfitting*. Um grau muito baixo pode resultar em um modelo subajustado, incapaz de capturar as complexidades dos dados, enquanto um grau muito alto pode levar ao *overfitting*, com o modelo memorizando o ruído presente nos dados de treinamento.
Ao longo do ensaio, experimentei diversos algoritmos de classificação, regressão e clusterização, identificando os principais parâmetros que influenciam o desempenho dos modelos e as estratégias mais eficazes para evitar problemas de ajuste.

# Próximos passos

Pretendo expandir meus conhecimentos em *Machine Learning* experimentando novos algoritmos e conjuntos de dados, buscando identificar as melhores combinações de hiperparâmetros de cada cenário.
