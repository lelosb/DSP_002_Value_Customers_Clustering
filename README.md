# DSP_002_Value_Customers_Clustering
> Status: Análise Exploratória dos dados ⚠️
## O objetivo deste projeto é explorar uma base de dados de um e-commerce e encontrar grupos de consumidores para um programa de fidelidade utilizando ferramentas de machine learning. Em resumo, é um problema de clusterização.

[1]!

# Introdução

## O problema de Negócio

A empresa All In One Place é uma empresa e-commerce multimarcas. Em pouco mais de 1 ano de operação, o time de marketing percebeu que alguns clientes da sua base, compram produtos mais caros, com alta frequência e acabam contribuindo com uma parcela significativa do faturamento da empresa. Baseado nessa percepção, o time de marketing vai lançar um programa de fidelidade para os melhores clientes da base, chamado Insiders, mas o time não tem um conhecimento avançado em análise de dados para eleger os participantes do programa.
Por esse motivo, o time de marketing requisitou ao time de dados uma seleção de clientes elegíveis ao programa, usando técnicas avançadas de manipulação de dados.
Como parte do time de cientistas de dados da empresa, devemos utilizar nosso conhecimento e ferramentas de análise de dados para dizer ao time de negócios quem são os clientes elegíveis para participar do Insiders. Em posse dessa lista, o time de Marketing fará uma sequência de ações personalizadas e exclusivas ao grupo, de modo a aumentar o faturamento e a frequência de compra.

# Resultados esperados

Como resultado para esse projeto, é esperado que você entregue uma lista de pessoas elegíveis a participar do programa Insiders, junto com um relatório respondendo às seguintes perguntas:

Quem são as pessoas elegíveis para participar do programa de Insiders ?
Quantos clientes farão parte do grupo?
Quais as principais características desses clientes ?
Qual a porcentagem de contribuição do faturamento, vinda do Insiders ?
Qual a expectativa de faturamento desse grupo para os próximos meses ?
Quais as condições para uma pessoa ser elegível ao Insiders ?
Quais as condições para uma pessoa ser removida do Insiders ?
Qual a garantia que o programa Insiders é melhor que o restante da base ?
Quais ações o time de marketing pode realizar para aumentar o faturamento?

# Solução

## Data Load

O conjunto de dados está disponível na plataforma do Kaggle². Cada linha do dataset representa uma transação de venda, que ocorreu entre o período de Novembro de 2016 e Dezembro de 2017. No arquivo, os dados estão disponíveis como segue:

|Feature | Descrição |
|Invoice Number| identificador único de cada transação.
|Stock Code Product| código do item.
|Description Product| nome do item
|Quantity| A quantidade de cada item comprado por transação.
|Invoice Date| O dia em que a transação ocorreu
|Unit Price| Preço do produto por unidade
|Customer ID| identificador único do cliente
|Country| O nome do país que o cliente reside


## Business assumptions

	O que está sendo assumido sobre o negócio?
	Quais os resultados da sua pesquisa sobre o modelo de negócio?
	Não precisa colocar todas, mas as principais
	Aqui se coloca as definições de negócio (tempo de churn, por exemplo)
	
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
1)Quem são as pessoas elegíveis para participar do programa de Insiders ?

    - O que é ser elegível? O que são os clientes de maior 'valor'? (resposta pelo time de negócio)
    - Faturamento:
        - Alto ticket médio
        - Alto LTV (Life Time Value)
        - Baixa Recência (tempo entre as compras)
        - Alto basket size
        - Baixa probabilidade de Churn (não renovação)
        - Alta Previsão de LTV
        - Alta propensão de compra
    - Custo
        - Baixa taxa de devolução
    - Experiência de compra
        - Média alta de avaliação
        
2)Quantos clientes farão parte do grupo?

    - Número total de clientes em relação ao grupo total
    
3)Quais as principais características desses clientes ?

    - Escrever características do cliente:
        -Idade
        -Localização
    - Escrever características dos hábitos de consumo
         - Atributos de clusterização
    
4)Qual a porcentagem de contribuição do faturamento, vinda do Insiders ?

    - Comparar o faturamento dos Insiders em relação ao faturamento total
    - Faturamento do grupo (leva em conta o time que toma conta do grupo)
    
5)Qual a expectativa de faturamento desse grupo para os próximos meses ?

    - LTV do grupo de Insiders
    - Análise de Cohort
    
6)Quais as condições para uma pessoa ser elegível ao Insiders ?

    - Definir a periodicidade (quando o modelo vai ser rodado?)
    - A pessoa precisa ser desimilar ou não-parecido com uma pessoa do grupo

7)Quais as condições para uma pessoa ser removida do Insiders ?

    - Definir a periodicidade (quando o modelo vai ser rodado?)
    - A pessoa precisa ser similar ou parecido com uma pessoa do grupo
    
8)Qual a garantia que o programa Insiders é melhor que o restante da base ?

    - Teste A/B
    - Teste A/B Bayesiano
    - Teste de hipóteses

9)Quais ações o time de marketing pode realizar para aumentar o faturamento?

    - Desconto
    - preferência de compra
    - frete
    - visita a empresa




# Referências
[1] Adaptado de : https://www.dreamstime.com/big-data-visualization-concept-infographics-design-cluster-analysis-data-clustering-big-data-visualization-concept-infographics-image189630891
[2] https://www.kaggle.com/vik2012kvs/high-value-customers-identification 
