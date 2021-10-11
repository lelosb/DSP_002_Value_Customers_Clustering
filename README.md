# DSP_002_Value_Customers_Clustering
> Status: Análise Exploratória dos dados ⚠️
## O objetivo deste projeto é explorar uma base de dados de um e-commerce e encontrar grupos de consumidores para um programa de fidelidade utilizando ferramentas de machine learning. Em resumo, é um problema de clusterização.

![1](https://github.com/lelosb/DSP_002_Value_Customers_Clustering/blob/main/reports/figures/design-cluster-analysis.jpg)

# Introdução

## O problema de Negócio

A empresa All In One Place é uma empresa e-commerce multimarcas. Em pouco mais de 1 ano de operação, o time de marketing percebeu que alguns clientes da sua base compram produtos mais caros com alta frequência e acabam contribuindo com uma parcela significativa do faturamento da empresa. Baseado nessa percepção, o time de marketing vai lançar um programa de fidelidade para os melhores clientes da base, chamado **Insiders**, mas o time não tem um conhecimento avançado em análise de dados para eleger os participantes do programa.
Por esse motivo, o time de marketing requisitou ao time de dados uma seleção de clientes elegíveis ao programa, usando técnicas avançadas de manipulação de dados.
Como parte do time de cientistas de dados da empresa, devemos utilizar nosso conhecimento e ferramentas de análise de dados para dizer ao time de negócios quem são os clientes elegíveis para participar do Insiders. Em posse dessa lista, o time de Marketing fará uma sequência de ações personalizadas e exclusivas ao grupo, de modo a aumentar o faturamento e a frequência de compra.

# Resultados esperados

Como resultado para esse projeto é esperada uma lista de pessoas elegíveis a participar do programa Insiders, junto com um relatório respondendo às seguintes perguntas:

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

O conjunto de dados está disponível na plataforma do Kaggle². Cada linha do dataset representa uma transação de venda, que ocorreu entre o período de Novembro de 2016 e Dezembro de 2017. O arquivo possui registro de 541909 transações, cada uma com 8 atributos disponíveis como segue:

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

### O que está sendo assumido sobre o negócio?

Para este projeto, devemos estabelecer algumas condições:

1) Quem são as pessoas elegíveis para participar do programa de Insiders ?

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
        
2)Quais as condições para uma pessoa ser removida do Insiders ?

    - Definir a periodicidade (quando o modelo vai ser rodado?)
    - A pessoa precisa ser similar ou parecido com uma pessoa do grupo
    

3)Quais ações o time de marketing pode realizar para aumentar o faturamento?

    - Desconto
    - preferência de compra
    - frete
    - visita a empresa

# Data Description
Fase de exporatória de dados. São valores faltantes ou inconsistentes, dados duplicados, outliers, se os tipos dos dados condizem com sua natureza.
# Feature Engineering

Para a aplicação dos modelos de aprendizado de máquina foram derivadas algumas features:

***gross_revenue*** - valor total gasto no período pelo cliente
***recency*** - dias passados desde a última compra
***frequency*** - frequencia de compra no período
***avg_basket_size*** - ticket médio


# Data Filtering

Filtragem dos dados que não serão utilizados nos modelos

# Exploratory Data Analisys

Fase de exploração dos dados, principalmente do ponto de vista estatístico.

# Data Preparation
Normalização e reescala dos dados
# Feature Selection
Features que serão utilizadas na modelagem
# Hyperparameter Fine Tunning

Nessa fase são ajustados os parâmetros que são responsabilidade do cientista de dados. Nosso principal Hiperparâmetro neste projeto é o número de clusters, o qual não temos a resposta de início. Foi aplicado o K-Means em um range de 2 a 10 clusters e foram utilizadas duas métricas para chegar ao melhor valor, o WSS e o Silhouette Score.

## WSS (Within-Cluster Sum of Square)

 As principais métricas de clusters são a compactação dentro de cada cluster e a distância entre os clusters. A WSS mede apenas a compactação, ou seja, mede apenas a distância entre os pontos dentro de um cluster. Por isso não pode ser utilizado sozinho. Já a Silhoueta mede a separação dos clusters
 Calcula as distâncias entre todos os pontos dentro de um mesmo cluster e tira a média (lembrando que o KMeans já separou os clusters).    Isso mede a compactação, depois mede a distância média entre os pontos de um cluster e ou outros clusters
 Cada ponto vai ter um score de silhoueta, que varia de -1 a 1 e diz o quanto o ponto pertence ao seu cluster ou o quanto deveria fazer parte de outro. Quanto mais perto do 1, melhor. Cada cor no gráfico mostra a distribuição da silhoueta de todos os pontos de um cluster

# Model training
Após decidir o número de clusters, devemos testar os modelos de ML para chegar no resultado final

## Machine Learning Model Applied
	Nomes dos modelos
	Tem que ter a performance (tabela de cross validation)
	Sem cross validation está errado
## Machine Learning Performance

# Inspection

Faz-se necessária a verificação da separação dos clusters. Até 3 dimensões dá pra fazer isso de forma visual, mas no nosso caso temos 5 features. Por isso é necessário utilizar outras ferramentas
## UMAP


# Convert Model Performance to Business Values

# Deploy Model to Production

# Data insights

# Business Results

1)Quantos clientes farão parte do grupo?

    - Número total de clientes em relação ao grupo total
    
2)Quais as principais características desses clientes ?

    - Escrever características do cliente:
        -Idade
        -Localização
    - Escrever características dos hábitos de consumo
         - Atributos de clusterização
    
3)Qual a porcentagem de contribuição do faturamento, vinda do Insiders ?

    - Comparar o faturamento dos Insiders em relação ao faturamento total
    - Faturamento do grupo (leva em conta o time que toma conta do grupo)
    
4)Qual a expectativa de faturamento desse grupo para os próximos meses ?

    - LTV do grupo de Insiders
    - Análise de Cohort
    
5)Quais as condições para uma pessoa ser elegível ao Insiders ?

    - Definir a periodicidade (quando o modelo vai ser rodado?)
    - A pessoa precisa ser desimilar ou não-parecido com uma pessoa do grupo

6)Qual a garantia que o programa Insiders é melhor que o restante da base ?

    - Teste A/B
    - Teste A/B Bayesiano
    - Teste de hipóteses

# Conclusions

	Resolveu o problema?
	Alcançou o proposto?
	Dava pra ter feito mais?
	Chegou no que esperava?
	
# Lessons learned


	
# Next steps

Ideias para implementação
 - Para cada retorno deve haver uma compra: pode-se excluir ambos
 - Compras/Devolução ou uma relação entre elas pode gerar uma feature
 - Variedade do carrinho pode ser uma métrica: (cross sell, ofertas...)
 - Menor número de clusters com silhoeta maior do que a sem embedding. Tem que ser melhor, senão pra que todo esse trabalho?
 - Qual a influência do formato dos clusters no modelo escolhido? Será que eu posso fazer uma inspeção visual no espaço e chutar qual embedding usar?
 
A conclusão 'final' foi que da forma como as features foram feitas existem basicamente 3 clusters, mas isso é muito pouco. Precisamos de mais para deixar parecido com o rfm. Agora vem a fase de clusterizar os espaços dos embeddings

# Referências
[1] Adaptado de : https://www.dreamstime.com/big-data-visualization-concept-infographics-design-cluster-analysis-data-clustering-big-data-visualization-concept-infographics-image189630891
[2] https://www.kaggle.com/vik2012kvs/high-value-customers-identification 
