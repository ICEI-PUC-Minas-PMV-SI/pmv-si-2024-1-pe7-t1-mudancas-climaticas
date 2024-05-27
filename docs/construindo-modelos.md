# Pergunta orientada a dados (???)
Justificar a definição / diferença da questão de pesquisa

# Tipos de dados do dataset

## Descrição dos Atributos:

| Nome do Atributo             | Tipo             |
|------------------------------|------------------|
| Data                         | Quantitativo      | 
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

# Outras bases de dados úteis 

O dataset 'Hourly Weather Surface Brazil Southeast Region' é abrangente o bastante para abordar os objetivos do projeto e resolver o problema identificado. Este conjunto de dados oferece informações detalhadas sobre as condições climáticas na região sudeste do Brasil, incluindo Belo Horizonte, o que nos permite avaliar a variabilidade espacial e temporal do clima, identificar áreas suscetíveis a eventos climáticos extremos e analisar as tendências climáticas ao longo do tempo.

O dataset selecionado oferece uma cobertura temporal e espacial abrangente das condições climáticas na região sudeste do Brasil, incluindo Belo Horizonte. Com dados horários, podemos capturar variações climáticas em diferentes momentos do dia e ao longo das estações do ano, permitindo uma análise detalhada da variabilidade temporal do clima. Além disso, a resolução espacial dos dados é suficientemente fina para identificar padrões climáticos em nível local, o que é crucial para avaliar a variabilidade espacial do clima na cidade.

Além de o dataset ser altamente especializado em informações climáticas, fornecendo uma ampla gama de variáveis relevantes, como temperatura, umidade, pressão atmosférica e vento. Essas variáveis são essenciais para compreender e analisar as características das ondas de calor, bem como para identificar áreas suscetíveis a esses eventos. E ao concentrar nossos esforços analíticos exclusivamente no dataset selecionado, podemos otimizar recursos e focar em uma análise mais aprofundada e detalhada das informações disponíveis. Isso nos permite explorar completamente o potencial do conjunto de dados em relação aos objetivos do projeto, sem diluir a análise com informações adicionais que podem não ser essenciais ou relevantes para a resolução do problema identificado.

Portanto, com base nessas considerações, acreditamos firmemente que o dataset 'Hourly Weather Surface Brazil Southeast Region' é suficiente e adequado para atender às necessidades do projeto e fornecer insights valiosos sobre as ondas de calor em Belo Horizonte, da região sudeste do Brasil.

# Preparação dos dados

## Limpeza de Dados:

Durante a fase inicial de preparação dos dados, os atributos foram categorizados como quantitativos, descritivos e nominais, a fim de caracterizá-los adequadamente. Observou-se que todos os atributos quantitativos continham dados negativos, os quais representavam casos em que não foi possível aferir ou computar os dados de determinado atributo. Para lidar com essa questão, foi utilizado o Excel para isolar esses componentes e, em seguida, os dados foram tratados manualmente. Posteriormente, os dados foram transferidos para o ambiente do Jupyter Notebook, onde, por meio de programação em Python, foi possível remover 100% dos valores negativos de forma automatizada.

Para iniciar a limpeza dos dados, foi realizada uma inspeção inicial para entender a estrutura do dataset e identificar possíveis problemas. Utilizamos o comando head para visualizar as primeiras linhas do dataset:

```
python
print(base.head())

```

Essa inspeção permitiu observar a presença de valores negativos em atributos quantitativos, que são indicativos de dados faltantes ou erros de medição.

## Remoção de Valores Negativos

Os valores negativos foram considerados inválidos para os seguintes atributos quantitativos:

```
colunas = [
'PRECIPITAÇÃO TOTAL, HORÁRIO (mm)',
'PRESSAO ATMOSFERICA AO NIVEL DA ESTACAO, HORARIA (mB)',
'PRESSÃO ATMOSFERICA MAX.NA HORA ANT. (AUT) (mB)',
'PRESSÃO ATMOSFERICA MIN. NA HORA ANT. (AUT) (mB)',
'RADIACAO GLOBAL (Kj/m²)',
'TEMPERATURA DO AR - BULBO SECO, HORARIA (°C)',
'TEMPERATURA DO PONTO DE ORVALHO (°C)',
'TEMPERATURA MÁXIMA NA HORA ANT. (AUT) (°C)',
'TEMPERATURA MÍNIMA NA HORA ANT. (AUT) (°C)',
'TEMPERATURA ORVALHO MAX. NA HORA ANT. (AUT) (°C)',
'TEMPERATURA ORVALHO MIN. NA HORA ANT. (AUT) (°C)',
'UMIDADE REL. MAX. NA HORA ANT. (AUT) (%)',
'UMIDADE REL. MIN. NA HORA ANT. (AUT) (%)',
'UMIDADE RELATIVA DO AR, HORARIA (%)',
'VENTO, DIREÇÃO HORARIA (gr) (° (gr))',
'VENTO, RAJADA MAXIMA (m/s)',
'VENTO, VELOCIDADE HORARIA (m/s)'
]

```
- Substituímos os valores negativos por NaN (Not a Number) para facilitar a remoção posterior:

```
base[colunas] = base[colunas].mask(base[colunas] < 0)

```
- Em seguida, todas as linhas contendo NaN em qualquer uma das colunas foram removidas, garantindo que apenas dados completos fossem mantidos no dataset:

```
base = base.dropna()

```

## Remoção de Atributos Desnecessários

Foram removidos atributos que não contribuíam diretamente para as análises quantitativas, como latitude, longitude e altitude, juntamente com outros atributos descritivos:

```
colunas_nao_numericas = ['index', 'Data', 'Hora', 'station_code', 'latitude', 'longitude', 'height', 'region', 'state', 'station']
base_sem_nan = base.drop(columns=colunas_nao_numericas)

```

- Após essa etapa de limpeza, o dataset foi verificado novamente para assegurar que os valores negativos haviam sido removidos com sucesso:

```
print(base.head())

```

### Transformação de Dados

#### Normalização dos Valores Quantitativos

Para garantir que os valores quantitativos fossem comparáveis entre si, realizamos a normalização desses valores. Esta etapa envolve ajustar as escalas dos dados para que todos os atributos tenham uma faixa similar, o que é essencial para análises subsequentes e para a aplicação de algoritmos de aprendizado de máquina.

#### Separação de Dados para Validação e Teste

Seguindo as melhores práticas, os dados foram divididos em conjuntos de treinamento e teste. Isso permite a validação cruzada dos modelos e uma avaliação mais robusta do desempenho do modelo desenvolvido.

### Tratamento de Dados Temporais:

#### Indexação Temporal

Dada a natureza temporal dos dados, utilizamos um índice temporal para categorizar os registros por hora. Por exemplo, se a contagem começou em 2017 às 00:00, ela será indexada de acordo com a hora até 2021 às 00:00:

```
base['timestamp'] = pd.to_datetime(base['timestamp'])
base.set_index('timestamp', inplace=True)

```

#### Visualização de Dados

Para garantir a qualidade e compatibilidade dos dados, foram criados gráficos que incluem:

- Mapas de Calor: Foram gerados mapas de calor utilizando as medidas de média e mediana das variáveis ao longo do tempo, permitindo uma visualização mais clara dos padrões climáticos.
- Gráficos de Variáveis: Além dos mapas de calor, foram criados gráficos para cada variável individual, permitindo uma análise mais detalhada de sua distribuição ao longo do período de tempo.

##### Mapa de Calor da Matriz de Correlação

Para garantir a qualidade e a compatibilidade dos dados, foi criado um mapa de calor que visualiza a correlação entre as variáveis numéricas. Este gráfico ajuda a identificar relações significativas entre os atributos do dataset.

1) Primeiro, removemos as colunas não numéricas para calcular a matriz de correlação:

```
colunas_nao_numericas = ['index', 'Data', 'Hora', 'station_code', 'latitude', 'longitude', 'height', 'region', 'state', 'station']
base_sem_nan = base.drop(columns=colunas_nao_numericas)

```

2) Em seguida, calculamos a matriz de correlação:

```
correlation_matrix = base_sem_nan.corr()
```

3) Utilizamos a biblioteca Seaborn para criar o mapa de calor:

- Definindo o tamanho da figura
```
fig, ax = plt.subplots(figsize=(12, 10))
```

- Plotando o mapa de calor com paleta de cores do branco ao azul escuro
```
heatmap = sns.heatmap(correlation_matrix, annot=True, cmap='Blues', fmt=".2f", cbar_kws={'extend': 'both'}, center=0, ax=ax)
```

- Abreviando os rótulos dos eixos x e y

```
heatmap.set_xticklabels(heatmap.get_xticklabels(), rotation=45, ha='right')
heatmap.set_yticklabels(heatmap.get_yticklabels(), rotation=0)

plt.title('Mapa de Calor da Matriz de Correlação (sem colunas não numéricas)')
plt.tight_layout(rect=[0, 0, 0.8, 0.8]) # Ajustando o layout para 20% menor
plt.show()

```

O mapa de calor resultante fornece uma visualização clara das correlações entre variáveis, facilitando a identificação de padrões e relações significativas nos dados.

A análise inicial dos dados climáticos de Belo Horizonte revelou que, após a limpeza dos dados, não foi necessária a conversão ou alteração adicional dos mesmos. As técnicas utilizadas garantiram a integridade e a qualidade dos dados, possibilitando uma análise robusta dos padrões climáticos ao longo dos últimos cinco anos.

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
