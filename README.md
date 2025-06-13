# P2-Machine_Learning

## Análise de Dados do PIB Per Capita Global
Este projeto realiza uma análise exploratória e de clusterização de dados históricos do Produto Interno Bruto (PIB) per capita de diversos países e regiões do mundo, utilizando técnicas de regressão linear, correlação de Pearson e K-Means.

**Integrantes**:   
Bruno Polizel de Macedo  
Felipe de Novais Lira Crispim  
Gabriel Antonio Muniz Viana  
Rodrigo dos Santos Estevam.  

**Disciplina**: Desenvolvimento de Software Multiplataforma - 5º Semestre.

**Professor**: Bruno Zolotareff dos Santos.

Data: 11/06/2025

### Visão Geral do Projeto
O objetivo principal deste projeto é identificar e agrupar países com base em diferentes dinâmicas de crescimento econômico ao longo do tempo. Para isso, são realizadas três análises distintas:

**Regressão Linear**: Para identificar os países com a maior tendência de crescimento absoluto do PIB per capita.

**Correlação de Pearson**: Para encontrar os países cujo crescimento do PIB per capita foi mais consistente e positivo ao longo do tempo.

**Clusterização K-Means**: Para segmentar os países em grupos com base em seus padrões de crescimento e níveis de riqueza.

### Base de Dados
O projeto utiliza dois arquivos de dados principais, derivados de fontes de dados econômicos globais:

**PIB_PER.xlsx** (na aba PIB_PerCapita): Contém os dados do PIB per capita anual para 149 países e regiões, abrangendo o período de 1960 a 2023. Esta base é utilizada para a análise de Regressão Linear.

**pib.csv**: Uma versão processada dos dados de PIB, utilizada para as análises de Correlação de Pearson e K-Means.

Os dados representam o PIB per capita em dólares americanos correntes. Antes da análise, os dados passam por uma etapa de limpeza, onde colunas irrelevantes são removidas e valores ausentes são tratados por meio de interpolação e preenchimento.

### Análises Realizadas  
#### Regressão Linear: Tendência de Crescimento
Nesta análise, o objetivo é quantificar a "velocidade" do crescimento do PIB de cada país em termos absolutos.

**Metodologia**: Para cada país, é ajustado um modelo de regressão linear simples, onde a variável independente é o tempo (os anos de 1960 a 2023) e a variável dependente é o valor do PIB per capita.

**Métrica Prevista**: O coeficiente angular (a inclinação da reta) da regressão é extraído. Este valor, chamado de "tendência", representa o aumento médio anual do PIB per capita em dólares.

**Resultado Analisado**: São identificados os 15 países com a maior tendência de crescimento (maior aumento absoluto anual) e é visualizada a trajetória dos 3 primeiros em um gráfico para ilustrar seu desempenho.

#### Correlação de Pearson: Consistência do Crescimento
Esta análise foca na consistência da trajetória de crescimento, verificando se o aumento do PIB foi constante e linear ao longo do tempo.

**Metodologia**: É calculado o coeficiente de correlação de Pearson entre o tempo (anos) e o PIB per capita para cada país.

**Métrica Prevista**: O coeficiente de correlação (um valor entre -1 e 1). Um valor próximo de 1 significa um crescimento forte e constante, enquanto valores menores ou negativos indicam volatilidade ou estagnação.

**Resultado Analisado**: São identificados os 15 países com a maior correlação positiva (crescimento mais consistente) e os 15 com a menor correlação, visualizando as tendências dos principais grupos em gráficos.

#### Clusterização com K-Means
A análise de K-Means foi realizada com duas abordagens distintas para segmentar os países em grupos homogêneos, revelando diferentes padrões econômicos.

##### Análise por Taxa de Crescimento (2012-2022)
Esta abordagem foca na dinâmica econômica recente, agrupando os países pela sua taxa de crescimento percentual na última década analisada.

**Metodologia**:

Calcula-se a taxa de crescimento percentual do PIB per capita entre 2012 e 2022.

Utiliza-se o Método do Cotovelo (Elbow Method) para determinar o número ideal de clusters (grupos), que foi definido como 4.

O algoritmo K-Means é aplicado para agrupar os países com base nessa taxa de crescimento.

**Resultado Analisado**: Segmentação dos países em quatro categorias distintas de performance econômica:

Cluster 0: Estagnação/Recessão

Cluster 1: Baixo Crescimento

Cluster 2: Crescimento Moderado

Cluster 3: Alto Crescimento

##### Análise por Trajetória Histórica do PIB (1960-2023)
Esta segunda abordagem agrupa os países com base em sua trajetória completa de PIB ao longo de mais de 60 anos, refletindo tanto o crescimento quanto o nível de riqueza.

**Metodologia**:

Os dados do PIB per capita de 1960 a 2023 são padronizados para que as escalas não influenciem o resultado.

O K-Means é aplicado sobre os dados completos para encontrar 3 clusters.

A dimensionalidade dos dados é reduzida para 2 componentes principais usando PCA (Principal Component Analysis), facilitando a visualização dos grupos em um gráfico 2D.

**Resultado Analisado**: Agrupamento dos países em três grandes grupos que, em geral, correspondem a:

Países de alta renda e economias desenvolvidas.

Países de renda média ou com crescimento intermediário.

Países de renda baixa ou em desenvolvimento.

### Como Executar
Certifique-se de ter o Python e o Jupyter Notebook (ou um ambiente compatível como o Google Colab) instalados.

Instale as bibliotecas necessárias:

<pre>pip install pandas numpy matplotlib seaborn scikit-learn scipy openpyxl<br></pre>

Coloque os arquivos Atividade_P2_RegLinear_Pearson_K_Means (1).ipynb, PIB_PER.xlsx (que no código é referenciado como PIB_PER_2.xlsx) e pib.csv no mesmo diretório.

Abra e execute o notebook célula por célula.

### Bibliotecas Utilizadas
**pandas**: Para manipulação e análise de dados.

**numpy**: Para operações numéricas.

**scikit-learn**: Para aplicar os modelos de Regressão Linear e K-Means, além da padronização de dados e PCA.

**scipy**: Para o cálculo da correlação de Pearson.

**matplotlib e seaborn**: Para a visualização e plotagem de gráficos.

**openpyxl**: Para a leitura de arquivos Excel.
