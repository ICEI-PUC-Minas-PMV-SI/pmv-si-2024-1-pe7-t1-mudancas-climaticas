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

