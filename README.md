# Estimando Preço dos Carros

  Neste projeto, obtido a parti do kaggle (que pode ser obtido [aqui](https://www.kaggle.com/datasets/jsm020796/cars-price-dataset) vai ser feito um modelo de machine learning para estimar valores do preço do carros, no qual será feito uma análise exploratória, o tratamento dos dados, a modelagem e a comparação das métricas dos modelos (neste readme vai ser mostrado de modo resumido, se quiser ver como o processo foi feito com mais detalhe, acesse o notebook [aqui](https://colab.research.google.com/drive/1eRbRrGJaDPdkG4fr3MuYp21JQtc8rXcr?usp=sharing)).
  
 ## Análise Exploratória
 
 Quanto ao dicionário dos dados, temos as seguintes informaçõe (essas infomações foi tirada a partir de outros datases que já manipulei, caso conseiga ter acesso as informações, esse dicionário será atualizado)
 
 ![image](https://user-images.githubusercontent.com/39843884/184365896-2eba137d-0eb0-498a-9cfc-2422293ee4c3.png)

 
 Observado como os preços estão distribuidos vemos o gráfico a seguir:
 
 ![image](https://user-images.githubusercontent.com/39843884/184363530-3ad298db-200b-4dfc-9178-46ad83910ca8.png)

 Verifica-se que os preços estão na sua maioria entre 0 e 50 mil, percebe-se que temos valores discrepantes, no qual pode ser visto no gráfito de boxplot abaixo:
  
  ![image](https://user-images.githubusercontent.com/39843884/184363922-019063ff-da0e-4b35-baf5-887fbc6e1dd2.png)

 Podemos ver que temos valores muito discrepantes, a partir de valores acima de 200 mil, que será verificado em seguida comparando os resultados comparando os modelos com e sem valores discrepantes.

Quanto ao ano de produção, temos que os valores são mais frequentes a partir de 2000.

![image](https://user-images.githubusercontent.com/39843884/184365348-2ebe6ef5-fc71-41ed-b244-3205448eee94.png)

E fazendo um gráfico de dispersão entre o ano de produção e o preço, podemos ver que:

![image](https://user-images.githubusercontent.com/39843884/184366441-50a85f74-0995-4227-afcd-98842bc44674.png)

- A maioria dos valores estão entre 0 e 150 mil;
- os valores mais caros que 150 mil tem 2 da marca toyota e o resto pertencente a mercede-benz.

Para complememtar essa visualização, veremos o grafico de boxplot abaixo:

![image](https://user-images.githubusercontent.com/39843884/184367056-b6372238-55c2-4225-98d7-864862d76fca.png)

Observa-se que as marca renalut e mitsubishi tem os valores mais baratos, enquanto as marcas que tem valores acima de 100 mil, são bmw, mercede-benz e alguns do toyota.

Isso se confirma olhando o preço médio dos produtos em que a mercede-benz tem o valor mais alto, e o preço médio menor é ao renault.

![image](https://user-images.githubusercontent.com/39843884/184368085-2d7a15cf-3e97-49ab-b422-2ee14f182e5b.png)

quanto ao tipo de combustivo, o Petrol costuma ser o mais caro, seguido do diesel, e o motor com combustivel a gás costuma ter um valor mais barato.

![image](https://user-images.githubusercontent.com/39843884/184368566-8b98d9b9-85e1-4035-a187-c055ddc8932e.png)


Podemos ver que quanto maior o número de milhas pecorridos, o preço tende a diminuir, já que o carro costuma se desvalorizar com  o passar do tempo e com número de distância pecorrida.

![image](https://user-images.githubusercontent.com/39843884/184369099-baf4abf7-f7ea-4d82-b241-ddc2aea0798e.png)

A maioria do carros são registrados (cerca de 90%) sendo assim, essa variavel será desconsiderada na modelagem.

![image](https://user-images.githubusercontent.com/39843884/184369522-5b9debfa-d1f3-4e41-9dc9-2407b5402aef.png)

E os 15 modelos de carros mais frequentes que aparecem são essas:

![image](https://user-images.githubusercontent.com/39843884/184369824-fb844b12-4820-45b9-af87-57727b9517ef.png)


## Modelagem

Foi feito o tratamento dos dados, foi apagado todas as linhas com os valores nulos, as colunas Registration e Model foram desconsideradas, e com as colunas Brand e Body foi aplicado para serem variaveis dummies, a partir disso, foi disso,o dataset foi dividido em 75% de treino e 25% de teste, e o modelo que teve a melhor perfomace foi o catboost, com as seguintes métricas:

![image](https://user-images.githubusercontent.com/39843884/184370683-ebacb133-bdf5-4403-b64d-1420eee8769d.png)

## Conclusão

![image](https://user-images.githubusercontent.com/39843884/184370925-788bdad9-0786-40ab-a4c0-0a30a3d7c23e.png)

Podemos ver que, em geral o modelo teve uma boa perfomace, sendo que alguns teve uma estimativa teve muito diferente, que no caso, esse valores tem que ser investigados o porquê, seja porque tenha muito pouco valor, ou seja que seja algum algo que nesse projeto não foi percebido.
Espero que com esse projeto pode mostrar as pessoa como modelos de machine learning pode ser de ajuda para ajudar na compra de um carro ou gestor de uma empresa com informaçoes obtidas a partir de uma an
