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
A regressão linear simples foi escolhida pela sua interpretabilidade e facilidade de implementação. O ajuste foi feito minimizando o MSE, o que é um procedimento padrão para este tipo de modelo.

# Avaliação dos modelos criados

## Métricas utilizadas

Nesta seção, as métricas utilizadas para avaliar os modelos desenvolvidos deverão ser apresentadas (p. ex.: acurácia, precisão, recall, F1-Score, MSE etc.). A escolha de cada métrica deverá ser justificada, pois esta escolha é essencial para avaliar de forma mais assertiva a qualidade do modelo construído. 

## Discussão dos resultados obtidos

Nesta seção, discuta os resultados obtidos pelos modelos construídos, no contexto prático em que os dados se inserem, promovendo uma compreensão abrangente e aprofundada da qualidade de cada um deles. Lembre-se de relacionar os resultados obtidos ao problema identificado, a questão de pesquisa levantada e estabelecendo relação com os objetivos previamente propostos. 

# Pipeline de pesquisa e análise de dados

## algoritmo K-Nearest Neighbors (KNN)
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

