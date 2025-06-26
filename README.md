# Classificação de Flores Iris com Rede Neural Multicamadas (MLP)

Este projeto demonstra a aplicação de uma **Rede Neural Perceptron Multicamadas (MLP)** para classificar as espécies de flores do famoso dataset **Iris**. O objetivo é treinar um modelo capaz de identificar corretamente a espécie de uma flor Iris a partir de suas características.

---

## O que é o Dataset Iris?

O **Dataset Iris** é um conjunto de dados clássico em machine learning, amplamente utilizado para tarefas de classificação. Ele contém 150 amostras de flores Iris, com 50 amostras de cada uma das três espécies: Setosa, Versicolor e Virginica. Para cada flor, são fornecidas quatro características (features):

* Comprimento da sépala (sepal length)
* Largura da sépala (sepal width)
* Comprimento da pétala (petal length)
* Largura da pétala (petal width)

---

## Estrutura do Projeto

O código Python contido neste repositório realiza as seguintes etapas:

1.  **Carregamento dos Dados:** Utiliza a biblioteca `scikit-learn` para carregar o dataset Iris.
2.  **Divisão dos Dados:** Os dados são divididos em conjuntos de **treinamento (70%)** e **teste (30%)**. Essa separação é crucial para avaliar a capacidade do modelo de generalizar para dados nunca vistos antes.
3.  **Configuração e Treinamento do Modelo MLP:**
    * Um modelo `MLPClassifier` (Rede Neural Perceptron Multicamadas) é instanciado com os seguintes parâmetros:
        * **`verbose=True`**: Exibe o progresso do treinamento no console.
        * **`hidden_layer_sizes=(5,4)`**: Define duas camadas ocultas, uma com 5 neurônios e outra com 4 neurônios.
        * **`activation='relu'`**: Usa a função de ativação ReLU (Rectified Linear Unit) nas camadas ocultas.
        * **`batch_size=20`**: Atualiza os pesos da rede a cada 20 amostras de treinamento.
        * **`learning_rate='adaptive'`**: Ajusta a taxa de aprendizado conforme o progresso do treinamento.
        * **`momentum=0.9`**: Utiliza o otimizador com momentum para acelerar a convergência.
        * **`early_stopping=False`**: Desabilita a parada antecipada, permitindo que o modelo treine por todas as iterações definidas.
        * **`max_iter=1000`**: Define o número máximo de épocas (iterações completas sobre o conjunto de treinamento).
        * **`random_state=10`**: Garante a reprodutibilidade dos resultados do treinamento.
    * O modelo é então treinado utilizando os dados de treinamento (`X_treinamento`, `y_treinamento`).
4.  **Visualização da Curva de Loss:** Um gráfico é gerado para mostrar a **curva de loss (perda)** do modelo ao longo das iterações. A curva de loss indica quão bem o modelo está aprendendo; idealmente, ela deve diminuir ao longo do tempo.
5.  **Previsões e Avaliação:**
    * O modelo treinado é usado para fazer previsões (`previsoes`) sobre o conjunto de dados de teste (`X_teste`).
    * A **acurácia** do modelo é calculada comparando as previsões com os rótulos reais do conjunto de teste (`y_teste`). A acurácia representa a porcentagem de previsões corretas do modelo.

---

![Image](https://github.com/user-attachments/assets/6347c5db-57e9-49ce-8746-f6a23c2ea5d2)

## Como Rodar o Código

Você pode executar este código diretamente em um ambiente como o **Google Colab** ou qualquer ambiente Python que tenha as bibliotecas necessárias instaladas.

### Pré-requisitos:

Certifique-se de ter as seguintes bibliotecas instaladas em seu ambiente Python:

```bash
pip install scikit-learn matplotlib
