# DSP_002_Value_Customers_Clustering

Readme
Título
Subtitulo
Capa (imagem)
1)Business problem
	Definição do problema de negócio
	O que é o projeto? Quais problemas vc resolveu?

2) Business assumption
	O que está sendo assumido sobre o negócio?
	Quais os resultados da sua pesquisa sobre o modelo de negócio?
	Não precisa colocar todas, mas as principais
	Aqui se coloca as definições de negócio (tempo de churn, por exemplo)
3)Solution strategy
	Raciocínio
	Quais os passos?
Data Description
Feature Engineering
Data Filtering
Exploratory Data Analisys
Data Preparation
Feature Selection
Machine Learning Modeling
Hyperparameter Fine Tunning
Convert Model Performace to Business Values
Deploy Model to Production
	Qual a estratégia utilizada?
4)Top 3 data insights
	Mostra os resultados para o negócio
5) Machine Learning Model Applied
	Nomes dos modelos
	Tem que ter a performance (tabela de cross validation)
	Sem cross validation está errado
6) Machine Learning Performance
7) Business Results
	
8) Conclusions
	Resolveu o problema?
	Alcançou o proposto?
	Dava pra ter feito mais?
	Chegou no que esperava?
9) Lessons learned
	O que foi bom? O que foi ruim? O que dava pra melhorar?
10) Next steps
11) References

Ideas for my project
 - For each return should there be a invoice. I can exclude both
quantidade de compras - devolução ou uma relação entre isso pode ser uma feature
 - A simple ranking with the most valuable customers
 - Watch the outliers since the begining
 - Diagrama de fluxo planejado / executado
 - Entender a silhoueta pra explicar
 - Possa pensar na variedade de produtos por compra, para oferecer cross sell
 - Uma coluna de della comparando os clusters com o insiders
 Menor número de clusters com silhoeta maior do que a sem embedding. Tem que ser melhor, senão pra que todo esse trabalho?
 Qual a influência do formato dos clusters no modelo escolhido? Será que eu posso fazer uma inspeção visual no espaço e chutar qual embedding usar?
 Talvez a quantidade de retornos não seja tão importante, pq muitas vezes o retorno entra como crédito

Foi pego  um erro apenas obsevando o outlier a analise univariada do gross revenue. Existia uma diferença muito grande entre o maior comprador e o 95 percentil
cagada monstra quando dropamos quantidades duplicadas
GRAFICOS PROFISSIONAIS PRECISAM SER COMPLETOS
A saída tem que meio que ser contemplando aquele modelo RFM
1) Ordenar os clientes por recency dando uma 'nota'
2) Dividir a base de clientes com base nas notas
3) Ordenar por frequency
4)Dividir os clientes conforme a nota 
A idéia é dar notas nos requisitos mais importantes e depois tirar as médias dessas notas para rankear os clientes

A conclusão 'final' foi que da forma como as features foram feitas existem basicamente 3 clusters, mas isso é muito pouco. Precisamos de mais para deixar parecido com o rfm. Agora vem a fase de clusterizar os espaços dos embeddings
