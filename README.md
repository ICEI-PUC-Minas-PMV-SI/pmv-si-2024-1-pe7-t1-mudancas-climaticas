# MUDANÇAS CLIMÁTICAS

`CURSO: Sistemas de Informação`

`DISCIPLINA: Projeto - Pesquisa e Experimentação em Sistemas de Informação`

`SEMESTRE: 7º`

Descrever resumidamente, em um ou dois parágrafos, o projeto que está sendo desenvolvido.

## Integrantes

* Caroline Clarissa Leite de Aguiar
* Krysthyan Jhonny Ramos da Silva
* Lucas de Paula Martins
* Maria Clara Bethonico Terra


## Orientador

* Luciana de Nardin

# Planejamento

| Etapa         | Atividades |
|  :----:   | ----------- |
| ETAPA 1         |[Documentação de Contexto e levantamento dos dados](docs/contexto.md) <br> |
| ETAPA 2         |[Conhecendo os dados](docs/conhecendo-dados.md) <br> |
| ETAPA 3         |[Preparação dos dados, construção e avaliação dos modelos propostos](docs/construindo-modelos.md) |
| ETAPA 4        |[Implantação e apresentação da solução](docs/implantação-apresentacao.md) <br>  |

## Instruções de utilização

Assim que a primeira versão do sistema estiver disponível, deverá complementar com as instruções de utilização. Descreva como instalar eventuais dependências e como executar a aplicação.

# Código

<li><a href="src/README.md"> Código Fonte</a></li>

## Regressao Linear


import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
import matplotlib.pyplot as plt
from scipy import stats

df = pd.read_csv('C:/Users/lucas/Downloads/mediasDiarias_modificado.csv')


print(df.head())


print(df.isnull().sum())


df = df.dropna()

df['Data'] = pd.to_datetime(df['Data'])

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
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = LinearRegression()

model.fit(X_train, y_train)

y_pred = model.predict(X_test)

mse = mean_squared_error(y_test, y_pred)

rmse = np.sqrt(mse)
print(f'Erro quadrático médio: {mse}')
print(f'Raiz do erro quadrático médio: {rmse}')


plt.scatter(y_test, y_pred)
plt.xlabel('Valores Reais')
plt.ylabel('Previsões')
plt.title('Valores Reais vs Previsões')
plt.show()
def prever_intervalo_temperatura(model, X, y, novos_dados, intervalo=0.95):
   s
    novos_dados = np.array(novos_dados).reshape(1, -1)
    
   
    previsoes = model.predict(novos_dados)
    
  
    n = len(X)
    
   
    p = X.shape[1]
    
   
    alpha = 1 - intervalo
    
   
    y_train_pred = model.predict(X)
    residuos = y - y_train_pred
    
   
    residuo_variancia = np.var(residuos, ddof=p)
    
    
    X_b = np.c_[np.ones((n, 1)), X]
    X_new_b = np.c_[np.ones((1, 1)), novos_dados]
    hat_matrix = X_new_b.dot(np.linalg.inv(X_b.T.dot(X_b)).dot(X_new_b.T))
    

    margem_erro = stats.t.ppf(1 - alpha / 2, n - p - 1) * np.sqrt(residuo_variancia * (1 + hat_matrix))
    
    intervalo_inferior = previsoes - margem_erro
    intervalo_superior = previsoes + margem_erro
    
    return intervalo_inferior[0], previsoes[0], intervalo_superior[0]
#Sequência dos Dados
##PRECIPITAÇÃO TOTAL, HORÁRIO (mm)
##PRESSAO ATMOSFERICA AO NIVEL DA ESTACAO, HORARIA (mB)
##RADIACAO GLOBAL (Kj/m²)
##TEMPERATURA DO PONTO DE ORVALHO (°C)
##UMIDADE REL. MAX. NA HORA ANT. (AUT) (%)
##UMIDADE REL. MIN. NA HORA ANT. (AUT) (%)
##UMIDADE RELATIVA DO AR, HORARIA (%)
##VENTO, RAJADA MAXIMA (m/s)
##VENTO, VELOCIDADE HORARIA (m/s)

# Exemplo de uso da função
novos_dados = [0, 882, 197, 14, 6, 5, 5, 8, 4]
intervalo_inferior, previsao, intervalo_superior = prever_intervalo_temperatura(model, X_train, y_train, novos_dados)
print(f'Intervalo de Temperatura: ({intervalo_inferior}, {previsao}, {intervalo_superior})')


KKN

import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import MinMaxScaler
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import classification_report, confusion_matrix
import matplotlib.pyplot as plt

df = pd.read_csv('C:/Users/lucas/Downloads/mediasDiarias_modificado.csv')


print(df.head())

print(df.isnull().sum())


df = df.dropna()


df['Data'] = pd.to_datetime(df['Data'])


def categorize_temperature(temp):
    if temp > 25:
        return 'quente'
    elif 18 < temp <= 25:
        return 'morna'
    else:
        return 'fria'

df['Categoria'] = df['TEMPERATURA DO AR - BULBO SECO, HORARIA (°C)'].apply(categorize_temperature)


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

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
scaler = MinMaxScaler()

X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

model = KNeighborsClassifier(n_neighbors=5)
model.fit(X_train_scaled, y_train)
y_pred = model.predict(X_test_scaled)


print(confusion_matrix(y_test, y_pred))
print(classification_report(y_test, y_pred))

def prever_categoria_temperatura(model, scaler, novos_dados):

    novos_dados_scaled = scaler.transform(np.array(novos_dados).reshape(1, -1))
    
   
    categoria_pred = model.predict(novos_dados_scaled)
    
    return categoria_pred[0]


#Sequência dos Dados
##PRECIPITAÇÃO TOTAL, HORÁRIO (mm)
##PRESSAO ATMOSFERICA AO NIVEL DA ESTACAO, HORARIA (mB)
##RADIACAO GLOBAL (Kj/m²)
##TEMPERATURA DO PONTO DE ORVALHO (°C)
##UMIDADE REL. MAX. NA HORA ANT. (AUT) (%)
##UMIDADE REL. MIN. NA HORA ANT. (AUT) (%)
##UMIDADE RELATIVA DO AR, HORARIA (%)
##VENTO, RAJADA MAXIMA (m/s)
##VENTO, VELOCIDADE HORARIA (m/s)


novos_dados = [0, 882, 197, 14, 6, 5, 5, 8, 4]
categoria_pred = prever_categoria_temperatura(model, scaler, novos_dados)
print(f'A temperatura prevista é: {categoria_pred}')



# Apresentação

<li><a href="presentation/README.md"> Apresentação da solução</a></li>
