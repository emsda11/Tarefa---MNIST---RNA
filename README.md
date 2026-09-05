# Tarefa 2 – Otimização do MNIST com Optuna

## Objetivo

Nesta tarefa, foi utilizado como base o código disponibilizado pelo professor para classificação das imagens do conjunto **MNIST**. A estrutura do código foi mantida, sendo realizada posteriormente a otimização dos hiperparâmetros utilizando o **Optuna**.

Foram avaliadas diferentes configurações relacionadas à quantidade de camadas ocultas, número de neurônios, função de ativação, taxa de *dropout*, número de *epochs* e tamanho do *batch*.

## Otimização dos hiperparâmetros

Foram realizados **15 trials**, utilizando parte dos dados de treinamento para validação. O conjunto de teste foi mantido separado durante esse processo e utilizado somente após a definição da melhor configuração.

A melhor configuração encontrada foi:

| Hiperparâmetro | Valor |
|---|---:|
| Camadas ocultas adicionais | 1 |
| Neurônios | 64 |
| Função de ativação | ReLU |
| Dropout | 0,1 |
| Epochs | 20 |
| Batch size | 128 |

A melhor configuração alcançou uma **acurácia de validação de aproximadamente 98,07%**.

## Treinamento do modelo final

Após a escolha dos melhores hiperparâmetros, o modelo foi treinado novamente utilizando **Early Stopping**, que interrompe o treinamento quando o desempenho no conjunto de validação deixa de apresentar melhora.

Embora a configuração previsse até 20 *epochs*, o treinamento foi encerrado após **11 epochs**.

## Resultados

Na avaliação final, foram obtidos os seguintes resultados:

| Métrica | Resultado |
|---|---:|
| Acurácia de treinamento | **98,52%** |
| Acurácia de teste | **97,34%** |
| Loss de teste | **0,0864** |
| Melhor acurácia de validação | **98,07%** |

O modelo inicial do código-base apresentou aproximadamente **95,31% de acurácia no conjunto de teste**. Após a otimização, a acurácia aumentou para **97,34%**, representando uma melhoria de aproximadamente **2 pontos percentuais**.

## Análise do ajuste final

O ajuste final pode ser considerado satisfatório, pois apresentou uma excelente acurácia tanto no treinamento quanto no teste. A diferença entre os resultados de treino e teste foi relativamente pequena, indicando uma boa capacidade de generalização.

Além disso, o uso de *dropout* e *Early Stopping* contribuiu para controlar o sobreajuste durante o treinamento.

## Tecnologias utilizadas

- Python
- TensorFlow/Keras
- Optuna
- MNIST
- Google Colab

## Notebook

O notebook completo, contendo o código e as células executáveis da atividade, está disponível no Google Colab:

**[Acessar notebook no Google Colab](https://colab.research.google.com/drive/1rTVXCYDfdgjuvHo3Lx1xvucXUAJ3rsWW)**
