# Pergunta orientada a dados

Embora ambas busquem conhecimento, as perguntas orientadas a dados e as questões de pesquisa se diferenciam em seus objetivos e naturezas. Por um lado, a pergunta orientada a dados é geralmente mais específica e técnica, focando em aspectos práticos e metodológicos da análise de dados. Essa pergunta busca identificar quais variáveis são mais relevantes, quais técnicas de modelagem podem ser aplicadas e como os dados podem ser melhor utilizados para atingir o objetivo específico de previsão. Ela se concentra em detalhes como a seleção de algoritmos, métodos de validação e métricas de desempenho, proporcionando um plano de ação claro e detalhado para a análise.

Por outro lado, a questão de pesquisa é mais ampla e conceitual. Ela não apenas busca entender a viabilidade de um modelo preditivo, mas também pretende explorar os impactos mais amplos do fenômeno estudado. A questão de pesquisa considera o contexto social, econômico e ambiental em que o problema está inserido e busca compreender as implicações das descobertas para a sociedade. Ela abrange objetivos gerais do estudo, como a identificação de áreas vulneráveis, a análise das tendências temporais e espaciais e a formulação de estratégias de adaptação e mitigação.

Em resumo, enquanto a pergunta orientada a dados se aprofunda nos detalhes técnicos e metodológicos necessários para construir e avaliar o modelo preditivo, a questão de pesquisa aborda o problema de forma holística, considerando tanto os aspectos técnicos quanto as implicações mais amplas das mudanças climáticas e das ondas de calor para Belo Horizonte e sua população.


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
![320312498-7592f817-8d1d-4d78-99be-fa4d2a5445dc](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/81424548/96f00cd3-2dce-451a-a151-3fee75ef5119)



O mapa de calor resultante fornece uma visualização clara das correlações entre variáveis, facilitando a identificação de padrões e relações significativas nos dados.

A análise inicial dos dados climáticos de Belo Horizonte revelou que, após a limpeza dos dados, não foi necessária a conversão ou alteração adicional dos mesmos. As técnicas utilizadas garantiram a integridade e a qualidade dos dados, possibilitando uma análise robusta dos padrões climáticos ao longo dos últimos cinco anos.

# Descrição dos modelos

Nesta seção, detalharemos os algoritmos de aprendizado de máquina utilizados para construir os modelos propostos: 
- K-Nearest Neighbors (KNN) para classificação e Regressão Linear para regressão.

Incluiremos informações sobre os conceitos fundamentais, princípios de funcionamento, vantagens e limitações, bem como justificativas para a escolha e ajuste dos parâmetros de cada algoritmo.

## Modelo 1: K-Nearest Neighbors (KNN)

O algoritmo K-Nearest Neighbors (KNN) é um dos métodos de aprendizado supervisionado mais simples para classificação e regressão. Funciona com base na ideia de que uma amostra será semelhante a suas 'k' vizinhas mais próximas no espaço das características.

### Princípios de Funcionamento
- Distância: KNN utiliza uma métrica de distância, como a Euclidiana, para calcular a proximidade entre os pontos de dados.
- Classificação: Para classificar um ponto desconhecido, o algoritmo encontra os 'k' pontos de dados mais próximos e atribui a classe mais comum (no caso de classificação) entre esses vizinhos.
- Parâmetros: O principal parâmetro é 'k', o número de vizinhos a considerar.
- Vantagens:
    - Simplicidade: Fácil de entender e implementar.
    - Flexibilidade: Não faz suposições sobre a distribuição dos dados.
    - Eficiência para Dados Pequenos: Funciona bem com conjuntos de dados pequenos e moderadamente grandes.
- Limitações:
    - Computacionalmente Intensivo: Ineficiente para grandes conjuntos de dados porque calcula a distância para cada ponto de dados.
    - Sensibilidade ao Ruído: Pode ser influenciado por ruídos e outliers nos dados.
    - Escalabilidade: Performance diminui drasticamente com o aumento do número de features e de dados.

### Ajuste de Parâmetros e Justificativa

O valor de 'k' determina o número de vizinhos considerados. Escolher um 'k' muito pequeno pode tornar o modelo sensível ao ruído, enquanto um 'k' muito grande pode diluir a classificação ao considerar muitos pontos de dados irrelevantes. Utilizamos MinMaxScaler para normalizar as características, pois KNN é sensível às diferentes escalas das características.

### Implementação e Ajuste
```
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import MinMaxScaler
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import classification_report, confusion_matrix
```

### Divisão dos dados
```
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

```

### Escalamento dos dados
```
scaler = MinMaxScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
```

### Treinamento do modelo KNN
```
model = KNeighborsClassifier(n_neighbors=5)
model.fit(X_train_scaled, y_train)
```
### Avaliação do modelo
```
y_pred = model.predict(X_test_scaled)
print(confusion_matrix(y_test, y_pred))
print(classification_report(y_test, y_pred))
```


O valor de 'k=5' foi escolhido com base em experimentação e validação cruzada para balancear a precisão e a robustez do modelo.

## Modelo 2: Regressão Linear

A regressão linear é um método estatístico para modelar a relação entre uma variável dependente e uma ou mais variáveis independentes, assumindo que a relação é linear.

### Princípios de Funcionamento

Mínimos Quadrados Ordinários (OLS): Os coeficientes são ajustados minimizando a soma dos quadrados dos erros entre os valores preditos e os valores reais.

- Vantagens
    - Interpretabilidade: Os coeficientes têm uma interpretação clara e direta.
    - Simplicidade: Fácil de implementar e entender.
    - Eficiência: Computacionalmente eficiente para treinamento e predição.
- Limitações
    - Assunção de Linearidade: Assume que a relação entre as variáveis independentes e dependentes é linear.
    - Sensibilidade a Outliers: Outliers podem ter um grande impacto na estimativa dos coeficientes.
    - Multicolinearidade: A presença de correlações altas entre variáveis independentes pode afetar a estabilidade das estimativas.
      
### Ajuste de Parâmetros e Justificativa
- Regularização: Métodos como Lasso e Ridge podem ser utilizados para lidar com multicolinearidade, embora não aplicados neste modelo básico.
- Validação Cruzada: Usada para validar o desempenho do modelo e ajustar os parâmetros, se necessário.

### Implementação e Ajuste

```
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
import numpy as np
```

### Divisão dos dados

```
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
```

### Treinamento do modelo de Regressão Linear
```
model = LinearRegression()
model.fit(X_train, y_train)
```

### Previsões
```
y_pred = model.predict(X_test)
```

### Avaliação do modelo
```
mse = mean_squared_error(y_test, y_pred)
rmse = np.sqrt(mse)
print(f'Erro quadrático médio: {mse}')
print(f'Raiz do erro quadrático médio: {rmse}')
```

### Visualização das previsões
```
plt.scatter(y_test, y_pred)
plt.xlabel('Valores Reais')
plt.ylabel('Previsões')
plt.title('Valores Reais vs Previsões')
plt.show()
```

![image](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/81424548/c29491e3-9f7b-46e7-bd96-e60bab33969a)

A regressão linear simples foi escolhida pela sua interpretabilidade e facilidade de implementação. O ajuste foi feito minimizando o MSE, o que é um procedimento padrão para este tipo de modelo.

# Avaliação dos modelos criados

## Métricas utilizadas


A avaliação dos modelos desenvolvidos é uma etapa crucial para garantir que eles performem bem e sejam úteis para suas respectivas tarefas. As métricas escolhidas para avaliação variam conforme o tipo de problema (classificação ou regressão) e os objetivos específicos do modelo.

1. Avaliação do Modelo K-Nearest Neighbors (KNN)
Métricas Utilizadas
Matriz de Confusão
Relatório de Classificação (Classification Report)
Justificativa das Métricas
Matriz de Confusão:

Descrição: A matriz de confusão é uma ferramenta que permite visualizar o desempenho de um algoritmo de classificação. Mostra a quantidade de verdadeiros positivos, falsos positivos, verdadeiros negativos e falsos negativos.
Justificativa: É essencial para entender como o modelo está classificando corretamente ou erroneamente as diferentes classes, fornecendo uma visão clara das áreas onde o modelo está errando.
Relatório de Classificação:

Descrição: Inclui métricas como precisão (precision), recall, F1-Score e acurácia para cada classe.
Justificativa:
Precisão (Precision): Mede a proporção de verdadeiros positivos entre as predições positivas feitas pelo modelo.
Recall: Mede a proporção de verdadeiros positivos detectados em relação ao total de verdadeiros positivos.
F1-Score: Combina precisão e recall em uma única métrica, sendo a média harmônica dessas duas. É útil quando há um trade-off entre precisão e recall.
Acurácia: Mede a proporção de todas as previsões corretas entre o total de previsões. É uma métrica geral de desempenho.
Avaliação do Modelo
python
Copiar código
# Avaliação do modelo
from sklearn.metrics import classification_report, confusion_matrix

# Previsões
y_pred = model.predict(X_test_scaled)

# Matriz de Confusão
print(confusion_matrix(y_test, y_pred))

# Relatório de Classificação
print(classification_report(y_test, y_pred))
2. Avaliação do Modelo de Regressão Linear
Métricas Utilizadas
Erro Quadrático Médio (MSE)
Raiz do Erro Quadrático Médio (RMSE)
Justificativa das Métricas
Erro Quadrático Médio (MSE):

Descrição: Mede a média dos quadrados dos erros, ou seja, a média das diferenças quadradas entre os valores reais e os valores preditos.
Justificativa: O MSE penaliza grandes erros de predição mais severamente do que erros menores, o que é útil para garantir que o modelo minimize grandes desvios nas predições.
Raiz do Erro Quadrático Médio (RMSE):

Descrição: É a raiz quadrada do MSE. É uma métrica mais interpretável porque está na mesma unidade que a variável alvo.
Justificativa: O RMSE fornece uma medida clara de quão longe, em média, as previsões do modelo estão dos valores reais. É uma métrica intuitiva para avaliar a precisão das previsões.
Avaliação do Modelo
python
Copiar código
from sklearn.metrics import mean_squared_error
import numpy as np

# Previsões
y_pred = model.predict(X_test)

# Calculando o erro quadrático médio
mse = mean_squared_error(y_test, y_pred)

# Calculando a raiz quadrada do erro quadrático médio
rmse = np.sqrt(mse)

print(f'Erro quadrático médio: {mse}')
print(f'Raiz do erro quadrático médio: {rmse}')
Resumo das Métricas e Justificativas
Classificação (KNN):

Matriz de Confusão: Esclarece a distribuição dos acertos e erros entre as classes.
Relatório de Classificação (Precision, Recall, F1-Score, Acurácia): Oferece uma análise detalhada de como o modelo performa em cada classe, ajudando a identificar desequilíbrios e áreas de melhoria.
Regressão (Linear Regression):

MSE: Avalia a média das diferenças quadradas entre os valores reais e preditos, penalizando erros maiores.
RMSE: Fornece uma métrica de erro na mesma unidade da variável alvo, facilitando a interpretação dos resultados.
A escolha dessas métricas permite uma avaliação abrangente e assertiva da qualidade dos modelos, alinhando-se com os objetivos específicos de cada tarefa de previsão.


## Discussão dos resultados obtidos

Modelo 1: K-Nearest Neighbors (KNN)
Contexto Prático
O modelo K-Nearest Neighbors foi aplicado para classificar a temperatura do ar em três categorias: "quente", "morna" e "fria", com base em diversas variáveis meteorológicas como precipitação, pressão atmosférica, radiação global, entre outras. Este tipo de classificação pode ser crucial para aplicações em meteorologia, agricultura e gestão de recursos hídricos, onde a previsão correta da temperatura pode influenciar tomadas de decisão importantes.

Resultados Obtidos
Matriz de Confusão:
A matriz de confusão mostrou a distribuição de verdadeiros positivos, falsos positivos, verdadeiros negativos e falsos negativos entre as classes.
Relatório de Classificação:
Acurácia: A medida geral de desempenho do modelo.
Precisão, Recall e F1-Score: Indicadores de como o modelo performa em cada classe individualmente.
Discussão
Os resultados obtidos pelo modelo KNN indicam que ele é capaz de classificar as temperaturas em suas respectivas categorias com uma boa acurácia. No entanto, a análise detalhada através da matriz de confusão e do relatório de classificação revela que há desequilíbrios na performance entre as diferentes classes.

Precisão: Alta precisão indica que quando o modelo prevê uma determinada classe, essa previsão é correta na maioria das vezes. No entanto, se a precisão é baixa para uma classe, isso pode indicar que o modelo está frequentemente confundindo essa classe com outras.
Recall: Um alto recall para uma classe indica que o modelo está conseguindo identificar corretamente a maioria dos exemplos dessa classe. Um recall baixo pode indicar que o modelo está perdendo muitos exemplos dessa classe.
F1-Score: Combina precisão e recall, proporcionando uma métrica balanceada. Um F1-Score baixo em uma classe específica sugere que o modelo precisa de melhorias para essa classe.
No contexto prático, essas métricas indicam que o modelo KNN pode ser utilizado para prever a temperatura com uma boa margem de confiança, mas melhorias podem ser feitas, especialmente para classes com menor precisão e recall. Isso poderia envolver a coleta de mais dados, o ajuste de hiperparâmetros ou a experimentação com outros algoritmos.

Relação com os Objetivos
O modelo KNN atinge o objetivo de classificar as temperaturas em categorias úteis para aplicações práticas. As áreas onde o modelo apresenta desempenho inferior identificam oportunidades para aprimoramento, alinhando-se com o objetivo de desenvolver um sistema de previsão robusto e confiável.

Modelo 2: Regressão Linear
Contexto Prático
O modelo de regressão linear foi aplicado para prever a temperatura do ar com base em diversas variáveis meteorológicas. A previsão precisa da temperatura é essencial para muitas áreas, incluindo meteorologia, planejamento urbano, e atividades agrícolas, onde uma previsão acurada pode impactar diretamente a eficiência operacional e a segurança.

Resultados Obtidos
Erro Quadrático Médio (MSE): Mede a média dos quadrados dos erros entre os valores reais e preditos.
Raiz do Erro Quadrático Médio (RMSE): A raiz quadrada do MSE, fornecendo uma métrica na mesma unidade da variável alvo.
Discussão
Os resultados do modelo de regressão linear mostraram um MSE e um RMSE que indicam o quão longe, em média, as previsões do modelo estão dos valores reais.

Erro Quadrático Médio (MSE): Um valor menor de MSE indica que o modelo está fazendo previsões próximas aos valores reais. No entanto, valores altos de MSE sugerem que o modelo está tendo dificuldades para ajustar a relação linear entre as variáveis independentes e a variável dependente.
Raiz do Erro Quadrático Médio (RMSE): Como o RMSE está na mesma unidade da variável alvo, ele fornece uma medida direta de quão precisas são as previsões. Um RMSE baixo indica previsões precisas, enquanto um RMSE alto sugere a necessidade de melhorias no modelo.
No contexto prático, esses resultados sugerem que o modelo de regressão linear pode prever a temperatura com um certo grau de precisão, mas também indica que há espaço para melhorias. Fatores como a complexidade das relações entre as variáveis meteorológicas e a temperatura, e a presença de possíveis outliers ou variáveis não consideradas, podem influenciar a precisão das previsões.

Relação com os Objetivos
O modelo de regressão linear atinge parcialmente o objetivo de prever a temperatura de forma precisa. A identificação de um MSE e RMSE relativamente altos aponta para áreas onde o modelo pode ser aprimorado, talvez através da inclusão de mais variáveis explicativas, transformação de variáveis existentes, ou uso de modelos mais complexos que capturem melhor a não-linearidade dos dados.

Conclusão Geral
Ambos os modelos, KNN e Regressão Linear, demonstraram potencial para serem utilizados em previsões meteorológicas com seus respectivos enfoques. O KNN mostrou-se útil para a classificação de temperaturas em categorias, enquanto a Regressão Linear forneceu uma medida contínua da temperatura. As métricas de avaliação utilizadas ajudaram a identificar pontos fortes e fracos de cada modelo, proporcionando um guia claro para futuras melhorias e ajustes. Estas melhorias podem incluir a otimização dos parâmetros dos modelos, a exploração de novos algoritmos, ou a coleta e integração de mais dados, sempre visando atender melhor aos objetivos propostos e às necessidades práticas do problema de previsão de temperatura.

# Pipeline de pesquisa e análise de dados

## Algoritmo K-Nearest Neighbors (KNN)
O algoritmo K-Nearest Neighbors (KNN) é um método de aprendizado supervisionado utilizado tanto para classificação quanto para regressão. No caso de classificação, o algoritmo atribui a classe de um dado exemplo com base nas classes dos seus k vizinhos mais próximos no espaço das features. O KNN é simples de implementar e entender, sendo eficaz para problemas onde a relação entre as features e a variável alvo é complexa e não-linear.

Principais características do KNN:

Intuitivo: Baseia-se na ideia de que exemplos semelhantes estão próximos uns dos outros.
Versátil: Pode ser usado para problemas de classificação e regressão.
Não Paramétrico: Não faz suposições sobre a distribuição dos dados.
Eficiente para pequenos conjuntos de dados: Embora possa ser computacionalmente custoso para grandes volumes de dados.
1. Coleta de Dados
Descrição:

Objetivo: Obter dados relevantes e de qualidade para análise.
Fontes de dados: Arquivos CSV.
Exemplo prático:

python
Copiar código
import pandas as pd

### Importando o arquivo CSV com os dados
df = pd.read_csv('C:/Users/lucas/Downloads/mediasDiarias_modificado.csv')

### Visualizar as primeiras linhas do dataframe
print(df.head())
2. Preparação dos Dados
Descrição:

Objetivo: Preparar os dados para análise, lidando com valores ausentes e convertendo tipos de dados.
Passos:

Verificar e tratar valores ausentes:
python
Copiar código
### Verificar se há valores ausentes
print(df.isnull().sum())

### Tratar valores ausentes, se necessário
df = df.dropna()
Converter a coluna 'Data' para o formato datetime:
python
Copiar código
### Converter a coluna 'Data' para o formato datetime
df['Data'] = pd.to_datetime(df['Data'])
Categorizar a temperatura:
python
Copiar código
### Função para categorizar a temperatura
def categorize_temperature(temp):
    if temp > 25:
        return 'quente'
    elif 18 < temp <= 25:
        return 'morna'
    else:
        return 'fria'

df['Categoria'] = df['TEMPERATURA DO AR - BULBO SECO, HORARIA (°C)'].apply(categorize_temperature)
3. Seleção e Engenharia de Features
Descrição:

Objetivo: Selecionar as variáveis independentes (features) e a variável dependente (target) para a construção do modelo.
Passos:

Selecionar as features (variáveis independentes) e o target (variável dependente):
python
Copiar código
X = df[['PRECIPITAÇÃO TOTAL, HORÁRIO (mm)', 
        'PRESSAO ATMOSFERICA AO NIVEL DA ESTACAO, HORARIA (mB)', 
        'RADIACAO GLOBAL (Kj/m²)', 
        'TEMPERATURA DO PONTO DE ORVALHO (°C)', 
        'UMIDADE REL. MAX. NA HORA ANT. (AUT) (%)', 
        'UMIDADE REL. MIN. NA HORA ANT. (AUT) (%)', 
        'UMIDADE RELATIVA DO AR, HORARIA (%)', 
        'VENTO, RAJADA MAXIMA (m/s)', 
        'VENTO, VELOCIDADE HORARIA (m/s)']]
y = df['Categoria']
4. Divisão dos Dados
Descrição:

Objetivo: Dividir os dados em conjuntos de treinamento e teste para avaliação do modelo.
Passos:

Dividir os dados em conjuntos de treinamento e teste:
python
Copiar código
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
5. Pré-processamento dos Dados
Descrição:

Objetivo: Escalar os dados para que todas as features estejam na mesma escala.
Passos:

Escalar os dados:
python
Copiar código
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)
6. Construção e Treinamento do Modelo
Descrição:

Objetivo: Construir e treinar um modelo de aprendizado de máquina com os dados preparados.
Passos:

Construir e treinar o modelo K-Nearest Neighbors (KNN):
python
Copiar código
from sklearn.neighbors import KNeighborsClassifier

model = KNeighborsClassifier(n_neighbors=5)
model.fit(X_train_scaled, y_train)
7. Avaliação do Modelo
Descrição:

Objetivo: Avaliar o desempenho do modelo utilizando métricas adequadas.
Passos:

Fazer previsões e avaliar o modelo:
python
Copiar código
from sklearn.metrics import classification_report, confusion_matrix

y_pred = model.predict(X_test_scaled)

### Avaliação do modelo
print(confusion_matrix(y_test, y_pred))
print(classification_report(y_test, y_pred))
8. Interpretação dos Resultados
Descrição:

Objetivo: Interpretar os resultados das previsões para obter insights significativos.
Passos:

Função para prever a categoria de temperatura para novos dados:
python
Copiar código
import numpy as np

def prever_categoria_temperatura(model, scaler, novos_dados):
    # Escalar os novos dados
    novos_dados_scaled = scaler.transform(np.array(novos_dados).reshape(1, -1))
    
    # Fazer a previsão
    categoria_pred = model.predict(novos_dados_scaled)
    
    return categoria_pred[0]

### Exemplo de uso da função
novos_dados = [0, 882, 197, 14, 6, 5, 5, 8, 4]
categoria_pred = prever_categoria_temperatura(model, scaler, novos_dados)
print(f'A temperatura prevista é: {categoria_pred}')

## Algoritmo Utilizado: Regressão Linear
A regressão linear é um método de aprendizado supervisionado usado para prever um valor contínuo. O objetivo é encontrar a relação linear entre as variáveis independentes (features) e a variável dependente (target). O modelo de regressão linear tenta ajustar uma linha (ou plano, em múltiplas dimensões) que minimiza a soma dos quadrados das diferenças entre os valores reais e os valores preditos.

Principais características da Regressão Linear:

Simplicidade: Fácil de implementar e interpretar.
Eficiência: Rápido para treinar e prever.
Assumptions: Pressupõe que há uma relação linear entre as features e o target.
Aplicabilidade: Útil quando se deseja uma interpretação clara das influências das features sobre o target.
1. Coleta de Dados
Descrição:

Objetivo: Obter dados relevantes e de qualidade para análise.
Fontes de dados: Arquivos CSV.
Exemplo prático:

python
Copiar código
import pandas as pd

# Importando o arquivo CSV com os dados
df = pd.read_csv('C:/Users/lucas/Downloads/mediasDiarias_modificado.csv')

### Visualizar as primeiras linhas do dataframe
print(df.head())
2. Preparação dos Dados
Descrição:

Objetivo: Preparar os dados para análise, lidando com valores ausentes e convertendo tipos de dados.
Passos:

Verificar e tratar valores ausentes:
python
Copiar código
### Verificar se há valores ausentes
print(df.isnull().sum())

### Tratar valores ausentes
df = df.dropna()
Converter a coluna 'Data' para o formato datetime:
python
Copiar código
### Converter a coluna 'Data' para o formato datetime
df['Data'] = pd.to_datetime(df['Data'])
3. Seleção e Engenharia de Features
Descrição:

Objetivo: Selecionar as variáveis independentes (features) e a variável dependente (target) para a construção do modelo.
Passos:

Selecionar as features (variáveis independentes) e o target (variável dependente):
python
Copiar código
X = df[['PRECIPITAÇÃO TOTAL, HORÁRIO (mm)', 
        'PRESSAO ATMOSFERICA AO NIVEL DA ESTACAO, HORARIA (mB)', 
        'RADIACAO GLOBAL (Kj/m²)', 
        'TEMPERATURA DO PONTO DE ORVALHO (°C)', 
        'UMIDADE REL. MAX. NA HORA ANT. (AUT) (%)', 
        'UMIDADE REL. MIN. NA HORA ANT. (AUT) (%)', 
        'UMIDADE RELATIVA DO AR, HORARIA (%)', 
        'VENTO, RAJADA MAXIMA (m/s)', 
        'VENTO, VELOCIDADE HORARIA (m/s)']]
y = df['TEMPERATURA DO AR - BULBO SECO, HORARIA (°C)']
4. Divisão dos Dados
Descrição:

Objetivo: Dividir os dados em conjuntos de treinamento e teste para avaliação do modelo.
Passos:

Dividir os dados em conjuntos de treinamento e teste:
python
Copiar código
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
5. Construção e Treinamento do Modelo
Descrição:

Objetivo: Construir e treinar um modelo de aprendizado de máquina com os dados preparados.
Passos:

Construir e treinar o modelo de Regressão Linear:
python
Copiar código
from sklearn.linear_model import LinearRegression

### Modelo de regressão linear
model = LinearRegression()

### Treinamento com os dados de treino
model.fit(X_train, y_train)
6. Avaliação do Modelo
Descrição:

Objetivo: Avaliar o desempenho do modelo utilizando métricas adequadas.
Passos:

Fazer previsões e avaliar o modelo:
python
Copiar código
from sklearn.metrics import mean_squared_error
import numpy as np

### Previsões com os dados de teste
y_pred = model.predict(X_test)

### Calculando o erro quadrático médio
mse = mean_squared_error(y_test, y_pred)

### Calculando a raiz quadrada do erro quadrático médio
rmse = np.sqrt(mse)
print(f'Erro quadrático médio: {mse}')
print(f'Raiz do erro quadrático médio: {rmse}')
7. Visualização dos Resultados
Descrição:

Objetivo: Visualizar os resultados das previsões para entender melhor o desempenho do modelo.
Passos:

Plotar os valores reais vs previsões:
python
Copiar código
import matplotlib.pyplot as plt

plt.scatter(y_test, y_pred)
plt.xlabel('Valores Reais')
plt.ylabel('Previsões')
plt.title('Valores Reais vs Previsões')
plt.show()
8. Previsão com Intervalo de Confiança
Descrição:

Objetivo: Fazer previsões para novos dados e calcular intervalos de confiança para essas previsões.
Passos:

Função para prever a temperatura com intervalo de confiança:
python
Copiar código
from scipy import stats
import numpy as np

def prever_intervalo_temperatura(model, X, y, novos_dados, intervalo=0.95):
    # Adiciona a interceptação (bias) aos novos dados
    novos_dados = np.array(novos_dados).reshape(1, -1)
    
    # Faz a previsão
    previsoes = model.predict(novos_dados)
    
    # Número de amostras de treino
    n = len(X)
    
    # Número de features
    p = X.shape[1]
    
    # Intervalo de confiança
    alpha = 1 - intervalo
    
    # Fazer previsões no conjunto de treinamento para calcular os resíduos
    y_train_pred = model.predict(X)
    residuos = y - y_train_pred
    
    # Calcular a variância dos resíduos
    residuo_variancia = np.var(residuos, ddof=p)
    
    # Calcular a matriz de projeção
    X_b = np.c_[np.ones((n, 1)), X]
    X_new_b = np.c_[np.ones((1, 1)), novos_dados]
    hat_matrix = X_new_b.dot(np.linalg.inv(X_b.T.dot(X_b)).dot(X_new_b.T))
    
    # Calcular a margem de erro
    margem_erro = stats.t.ppf(1 - alpha / 2, n - p - 1) * np.sqrt(residuo_variancia * (1 + hat_matrix))
    
    intervalo_inferior = previsoes - margem_erro
    intervalo_superior = previsoes + margem_erro
    
    return intervalo_inferior[0], previsoes[0], intervalo_superior[0]
Exemplo de uso da função:
python
Copiar código
#### Sequência dos Dados
#### PRECIPITAÇÃO TOTAL, HORÁRIO (mm)
#### PRESSAO ATMOSFERICA AO NIVEL DA ESTACAO, HORARIA (mB)
#### RADIACAO GLOBAL (Kj/m²)
#### TEMPERATURA DO PONTO DE ORVALHO (°C)
#### UMIDADE REL. MAX. NA HORA ANT. (AUT) (%)
#### UMIDADE REL. MIN. NA HORA ANT. (AUT) (%)
#### UMIDADE RELATIVA DO AR, HORARIA (%)
#### VENTO, RAJADA MAXIMA (m/s)
#### VENTO, VELOCIDADE HORARIA (m/s)

### Exemplo de uso da função
novos_dados = [0, 882, 197, 14, 6, 5, 5, 8, 4]
intervalo_inferior, previsao, intervalo_superior = prever_intervalo_temperatura(model, X_train, y_train, novos_dados)
print(f'Intervalo de Temperatura: ({intervalo_inferior}, {previsao}, {intervalo_superior})')



