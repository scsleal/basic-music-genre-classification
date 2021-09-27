******
Resumo
******

O presente projeto visa comparar o desempenho de determinados modelos de Machine Learning (ML) aplicados na classificação de gênero musical com base no dataset *GTZAN Dataset - Music Genre Classification* disponível no site do Kaggle. Também foi realizado uma breve análise exploratória de dados de um trecho de uma música utilizando o pacote *Librosa*, dedicada a análise de áudio e música.

Os modelos de classificação selecionados foram: *Convolution Neural Network* (CNN), *K-Nearest Neighbors*, *Extra Tree Classifier*, *Decision Tree Classifier* e o *Support Vector Machine*. Os 4 últimos foram treinados em série enquanto que o primeiro foi treinado aparte dos demais com determinada configuração. Foi utilizado a biblioteca *Keras* do *Tensorflow* para treinar o modelo CNN, enquanto os demais foi utilizado a biblioteca do *Scikit-learn*.

Os dados foram salvos em um arquivo csv e carregados como DataFrame do pandas do Python. A partir do dataframe, é separado o rótulo, ou classe, **y**, que é a coluna dos gêneros musicais, nomeada de *label*, dos demais dados, **X**. Junto com essa separação, é realizado alguns *feature enginnering* nos dados com os transformadores do *Scikit-Learn*. Em y, as categorias de texto são convertidas em números através do *LabelEncoder* para o modelo CNN e para o demais foi usado o get_dummies do pandas. Em **X**, é utilizado o *StandardScaler* para normalizar os dados nele contidos, removendo a média e deixando a variância igual a 1.

Os parâmetros para medir a qualidade do modelo CNN foram a função de perda Sparse Categorical Crossentropy e a Precisão (Accuracy). Quanto aos demais modelos, foram escolhidos a Precisão, Log Loss (também conhecido como Logistic Loss ou Cross-Entropy Loss) e o AUC (Area Under the ROC Curve). A curva ROC é do gráfico do TPR (True Positive Rate) x FPR (False Positive Rate). Quanto mais próximo de 1 está AUC, melhor o modelo preditivo. TPR e FPR são frações dos elementos que compõem a Confusion matrix.

Foi verificado que o CNN é muito mais preciso do que os demais modelos, com uma precisão de 92.5%, seguido pelo SVC com 84.8% de precisão. Comparando os modelos do sklearn selecionados, nota-se uma significativa diferença dos valores de perda dos modelos mais precisos em relação ao menos precisos. Analisando os valores de AUC  dos modelos, verifica-se que SVC contém valor bem próximo do K-Nearest Neighbors.
