# Pergunta orientada a dados (???)
Justificar a definição / diferença da questão de pesquisa

# Tipos de dados do dataset
Qual o tipo de cada um dos atributos?

## Descrição dos Atributos:

| Nome do Atributo             | Tipo             |
|------------------------------|------------------|
| Data                         | Quantitativo      | 
| Estação                      | Nominal           |
| Latitude                     | Quantitativo      |
| Longitude                    | Quantitativo      | 
| Altitude                     | Quantitativo      | 
| Temperatura (°C)             | Quantitativo      |
| Ponto de Orvalho (°C)        | Quantitativo      | 
| Umidade Relativa (%)         | Quantitativo      | 
| Pressão Atmosférica (hPa)    | Quantitativo      |
| Radiação Solar Global (W/m²) | Quantitativo      | 
| Velocidade do Vento (m/s)    | Quantitativo      | 
| Direção do Vento (°)         | Quantitativo      | 
| Precipitação Total (mm)      | Quantitativo      | 
| Precipitação Convectiva (mm) | Quantitativo      | 
| Precipitação Estratiforme (mm)| Quantitativo     | 
| Neve Total (mm)              | Quantitativo      | 
| Cobertura de Nuvens (%)      | Quantitativo      | 
| Visibilidade (km)            | Quantitativo      | 
| Qualidade do Ar              | Quantitativo      | 
| Sensação Térmica (°C)        | Quantitativo      | 
| Índice UV                    | Quantitativo      |

# Outras bases de dados úteis (???)
Justificar a utilização de outras bases 

O dataset 'Hourly Weather Surface Brazil Southeast Region' é abrangente o bastante para abordar os objetivos do projeto e resolver o problema identificado. Este conjunto de dados oferece informações detalhadas sobre as condições climáticas na região sudeste do Brasil, incluindo Belo Horizonte, o que nos permite avaliar a variabilidade espacial e temporal do clima, identificar áreas suscetíveis a eventos climáticos extremos e analisar as tendências climáticas ao longo do tempo.

O dataset selecionado oferece uma cobertura temporal e espacial abrangente das condições climáticas na região sudeste do Brasil, incluindo Belo Horizonte. Com dados horários, podemos capturar variações climáticas em diferentes momentos do dia e ao longo das estações do ano, permitindo uma análise detalhada da variabilidade temporal do clima. Além disso, a resolução espacial dos dados é suficientemente fina para identificar padrões climáticos em nível local, o que é crucial para avaliar a variabilidade espacial do clima na cidade.

Além de o dataset ser altamente especializado em informações climáticas, fornecendo uma ampla gama de variáveis relevantes, como temperatura, umidade, pressão atmosférica e vento. Essas variáveis são essenciais para compreender e analisar as características das ondas de calor, bem como para identificar áreas suscetíveis a esses eventos. E ao concentrar nossos esforços analíticos exclusivamente no dataset selecionado, podemos otimizar recursos e focar em uma análise mais aprofundada e detalhada das informações disponíveis. Isso nos permite explorar completamente o potencial do conjunto de dados em relação aos objetivos do projeto, sem diluir a análise com informações adicionais que podem não ser essenciais ou relevantes para a resolução do problema identificado.

Portanto, com base nessas considerações, acreditamos firmemente que o dataset 'Hourly Weather Surface Brazil Southeast Region' é suficiente e adequado para atender às necessidades do projeto e fornecer insights valiosos sobre as ondas de calor em Belo Horizonte, da região sudeste do Brasil.

# Preparação dos dados

Nesta etapa, deverão ser descritas todas as técnicas utilizadas para pré-processamento/tratamento dos dados.

Algumas das etapas podem estar relacionadas à:

* Limpeza de Dados: trate valores ausentes: decida como lidar com dados faltantes, seja removendo linhas, preenchendo com médias, medianas ou usando métodos mais avançados; remova _outliers_: identifique e trate valores que se desviam significativamente da maioria dos dados.

* Transformação de Dados: normalize/padronize: torne os dados comparáveis, normalizando ou padronizando os valores para uma escala específica; codifique variáveis categóricas: converta variáveis categóricas em uma forma numérica, usando técnicas como _one-hot encoding_.

* _Feature Engineering_: crie novos atributos que possam ser mais informativos para o modelo; selecione características relevantes e descarte as menos importantes.

* Tratamento de dados desbalanceados: se as classes de interesse forem desbalanceadas, considere técnicas como _oversampling_, _undersampling_ ou o uso de algoritmos que lidam naturalmente com desbalanceamento.

* Separação de dados: divida os dados em conjuntos de treinamento, validação e teste para avaliar o desempenho do modelo de maneira adequada.
  
* Manuseio de Dados Temporais: se lidar com dados temporais, considere a ordenação adequada e técnicas específicas para esse tipo de dado.
  
* Redução de Dimensionalidade: aplique técnicas como PCA (Análise de Componentes Principais) se a dimensionalidade dos dados for muito alta.

* Validação Cruzada: utilize validação cruzada para avaliar o desempenho do modelo de forma mais robusta.

* Monitoramento Contínuo: atualize e adapte o pré-processamento conforme necessário ao longo do tempo, especialmente se os dados ou as condições do problema mudarem.

* Entre outras....

Avalie quais etapas são importantes para o contexto dos dados que você está trabalhando, pois a qualidade dos dados e a eficácia do pré-processamento desempenham um papel fundamental no sucesso de modelo(s) de aprendizado de máquina. É importante entender o contexto do problema e ajustar as etapas de preparação de dados de acordo com as necessidades específicas de cada projeto.



## Limpeza de Dados:
Durante a fase inicial de preparação dos dados, os atributos foram categorizados como quantitativos, descritivos e nominais, a fim de caracterizá-los adequadamente. Observou-se que todos os atributos quantitativos continham dados negativos, os quais representavam casos em que não foi possível aferir ou computar os dados de determinado atributo. Para lidar com essa questão, foi utilizado o Excel para isolar esses componentes e, em seguida, os dados foram tratados manualmente. Posteriormente, os dados foram transferidos para o ambiente do Jupyter Notebook, onde, por meio de programação em Python, foi possível remover 100% dos valores negativos de forma automatizada.

### Transformação de Dados:
Após a limpeza inicial dos dados, foram realizadas as seguintes transformações:

Normalização dos valores quantitativos: Os valores numéricos foram normalizados para uma escala específica, garantindo que fossem comparáveis entre si.
Separação de Dados:
Os dados foram divididos em conjuntos de treinamento, validação e teste, seguindo as boas práticas para avaliar o desempenho do modelo de maneira adequada.

### Tratamento de Dados Temporais:
Considerando a natureza temporal dos dados, foi utilizado o índice temporal para categorizar os registros por hora. Por exemplo, se a contagem começou em 2017 às 00:00, ela será encerrada em 2021 às 00:00 de acordo com os registros disponíveis.

Visualização de Dados:
Para garantir a qualidade e compatibilidade dos dados, foram criados gráficos que incluem:

Mapas de Calor: Foram gerados mapas de calor utilizando as medidas de média e mediana das variáveis ao longo do tempo, permitindo uma visualização mais clara dos padrões climáticos.
Gráficos de Variáveis: Além dos mapas de calor, foram criados gráficos para cada variável individual, permitindo uma análise mais detalhada de sua distribuição ao longo do período de tempo.
Conclusão:
A análise inicial dos dados climáticos de Belo Horizonte revelou que, após a limpeza dos dados, não foi necessária a conversão ou alteração dos mesmos. As técnicas utilizadas garantiram a integridade e a qualidade dos dados, possibilitando uma análise robusta dos padrões climáticos ao longo dos últimos cinco anos.

# Descrição dos modelos

Nesta seção, conhecendo os dados e de posse dos dados preparados, é hora de descrever os algoritmos de aprendizado de máquina selecionados para a construção dos modelos propostos. Inclua informações abrangentes sobre cada algoritmo implementado, aborde conceitos fundamentais, princípios de funcionamento, vantagens/limitações e justifique a escolha de cada um dos algoritmos. 

Explore aspectos específicos, como o ajuste dos parâmetros livres de cada algoritmo. Lembre-se de experimentar parâmetros diferentes e principalmente, de justificar as escolhas realizadas.

Como parte da comprovação de construção dos modelos, um vídeo de demonstração com todas as etapas de pré-processamento e de execução dos modelos deverá ser entregue. Este vídeo poderá ser do tipo _screencast_ e é imprescindível a narração contemplando a demonstração de todas as etapas realizadas.

# Avaliação dos modelos criados

## Métricas utilizadas

Nesta seção, as métricas utilizadas para avaliar os modelos desenvolvidos deverão ser apresentadas (p. ex.: acurácia, precisão, recall, F1-Score, MSE etc.). A escolha de cada métrica deverá ser justificada, pois esta escolha é essencial para avaliar de forma mais assertiva a qualidade do modelo construído. 

## Discussão dos resultados obtidos

Nesta seção, discuta os resultados obtidos pelos modelos construídos, no contexto prático em que os dados se inserem, promovendo uma compreensão abrangente e aprofundada da qualidade de cada um deles. Lembre-se de relacionar os resultados obtidos ao problema identificado, a questão de pesquisa levantada e estabelecendo relação com os objetivos previamente propostos. 

# Pipeline de pesquisa e análise de dados

Em pesquisa e experimentação em sistemas de informação, um pipeline de pesquisa e análise de dados refere-se a um conjunto organizado de processos e etapas que um profissional segue para realizar a coleta, preparação, análise e interpretação de dados durante a fase de pesquisa e desenvolvimento de modelos. Esse pipeline é essencial para extrair _insights_ significativos, entender a natureza dos dados e, construir modelos de aprendizado de máquina eficazes. 
