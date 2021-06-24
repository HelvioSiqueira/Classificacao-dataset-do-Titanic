# Previsão de sobreviventes no desastre do Titanic

O RMS Titanic foi um navio de passageiros britânico que naufragou no dia 14 abril de 1912 com 1316 passageiros onde
apenas 700 pessoas se salvaram. A competição do Kaggle [Titanic - Machine Learning from Disaster](https://www.kaggle.com/c/titanic)
se baseia em tentar prever as pessoas que irão morrer e as que irão sobreviver de acordo com o dataset de pessoas que
estavam à bordo do navio.

## Análise Exploratoria

O dataset não está pronto pra uso(nenhuma novidade), então faço uma analise exploratoria inicial pra conhecer o dataset, 
que tem varios dados faltantes, colunas que não oferecem uso ou colunas que ainda precisa ser tratadas. 

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/dataset.png "Dataset Titanic")

Com uso de graficos constato que as mulheres foram os sobreviventes predominantes e que pessoas que na 1° Classe tiveram
maior chance de sobrevivencia, e tambem que pessoas com mais três parentes a bordo tiveram uma baixa chance de sobrevivência.

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/sobreviventes%20por%20sexo.png "Diferenciação de sobreviventes por sexo")

## Limpeza dos Dados

É hora de resolver os problemas detectados na análise exploratoria! Os dados precisam ser limpos para não resultar em 
problemas no treinamento do modelo. Substitui os dados nulos da coluna 'Age' pelo desvio padrão usado aleatoriedade, e a porta de
embarque 'Embarked' pela moda, o problema da coluna 'Cabin' foi resolvido no pré-processamento de dados já que criei 
outra coluna para resolver o problema dos dados faltantes.

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/nulos.png "Valores nulos em cada coluna")

## Pré-processamento dos dados

Aqui faço a criação de novas colunas usando colunas já existentes, como a coluna 'relatives' que indica quantos parentes
a pessoa tinha a bordo do Titanic, e também transformo a coluna nomes em uma coluna de titulos(que também
pode ter influenciado em quem iria sobreviver). Divido também a coluna de 'Age' em categorias, para ficar mais facil
aplicar o modelo.

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/sobreviventes_p_titulo.png "Porcentagem de sobrevivente por titulo")

Feito tudo isso, converto todos os valores não inteiro em inteiros.

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/base_final.png "Porcentagem de sobrevivente por titulo")

## Criação do Modelo de ML

Decido usar o RandomForest, por ser um algoritmo de simples entendimento, e por se adequar(segundo os casos de usos
observados) perfeitamente ao caso do Titanic.

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/score.png "Porcentagem de sobrevivente por titulo")

Ao final o modelo ficou com um score de mais ou menos 0.837 onde conseguiu acertar que 226 pessoas sobreviveriam errando somente 28, e que
124 viriam a morrer, errando 40(O motivo da alta quantidade de erros pode ser a pouca quantidade de amostras onde as 
pessoas morreriam no dataset, sigo trabalhando pra reduzir esse numero ;) ).

Esse é o meu primeiro contato com machine learning, então qualquer erro à ser reportado ou critica, não hesite em me contatar.