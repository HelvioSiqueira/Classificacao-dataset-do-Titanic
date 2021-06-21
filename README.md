# Previsão de sobreviventes no dessastre do Titanic
### Tentativa de previsão de sobreviventes usando classificação no dataset do Titanic

O RMS Titanic foi um navio de passageiros britânico que naufragou no dia 14 abril de 1912 com 1316 passageiros onde
apenas 700 pessoas se salvaram. A competição do Kaggle [Titanic - Machine Learning from Disaster](https://www.kaggle.com/c/titanic)
se baseia em tentar prever as pessoas que irão morrer e as que irão sobreviver de acordo com o dataset de pessoas que
estavam à bordo do navio.

Esse é o meu contato com machine learning, então qualque erro à ser reportado ou critica, não hesite em me contatar.

## Análise Exploratoria

O dataset não está pronto pra uso(nenhuma novidade), então faço uma analise exploratoria inicial pra conhecer o dataset, 
que tem varios dados faltantes, colunas que não oferecem uso ou colunas que ainda precisa ser tratadas. 

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/dataset.png "Dataset Titanic")

Com uso de graficos constastato que mulheres foram os sobreviventes predominantes e que pessoas que na 1° Classe tiveram
maior chance de sobrevivencia, e tambem que pessoas com mais 3 parentes a bordo tiveram uma baixa chance de sobrevivencia.

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/sobreviventes%20por%20sexo.png "Diferenciação de sobreviventes por sexo")

## Limpeza dos Dados

É hora de resolver os problemas detectados na análise exploratoria! Os dados precisam ser limpos para não resultar em 
problemas no treinamento do modelo. Substitui os dados nulos da coluna 'Age' pelo desvio padrão usado aleatoriedade, e a porta de
embarque 'Embarked' pela moda, o problema da coluna 'Cabin' foi resolvido no pré-processamento de dados já que criei 
outra coluna para resolver o problema dos dados faltantes.

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/nulos.png "Valores nulos em cada coluna")

## Pré-processamento dos dados

Aqui faço a criação de novas colunas usando colunas já existentes, como a 'relatives' que indica quantos parentes
a pessoa tinha a bordo do Titanic, e também transformo a coluna nomes em uma coluna de titulos(que também
pode ter influenciado em quem iria sobreviver). Divido também a coluna de 'Age' em intervalos, para ficar mais facil
aplicar o modelo. Feito tudo isso, transformo todo os valores não inteiro em inteiros.

![alt text](https://github.com/HelvioSiqueira/Classificacao-dataset-do-Titanic/blob/main/public/imagens/sobreviventes_p_titulo.png "Porcentagem de sobrevivente por titulo")