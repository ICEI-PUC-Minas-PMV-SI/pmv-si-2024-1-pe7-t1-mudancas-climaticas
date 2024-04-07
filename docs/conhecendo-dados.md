# Conhecendo os dados

Nesta seção, você deverá registrar uma detalhada análise descritiva e exploratória sobre a base de dados selecionada na Etapa 1 com o objetivo de compreender a estrutura dos dados, detectar eventuais _outliers_ e também, avaliar/detectar as relações existentes entre as variáveis analisadas.

Para isso, sugere-se que você utilize cálculos de medidas de tendência central, como média, mediana e moda, para entender a centralidade dos dados; explorem medidas de dispersão como desvio padrão e intervalos interquartil para avaliar a variabilidade dos dados; utilizem gráficos descritivos como histogramas e box plots, para representar visualmente as características essenciais dos dados, pois essas visualizações podem facilitar a identificação de padrões e anomalias; analisem a relação aparente entre as variáveis por meio de análise de correlação ou gráficos de dispersões, entre outras técnicas. 

Inclua nesta seção, gráficos, tabelas e demais artefatos que você considere relevantes para entender os dados com os quais você irá trabalhar.

![Mapa de Calor](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/blob/main/docs/img/mapa%20de%20calor.jpg)

### Visual dos Dados
Após o tratamento da base de dados foram gerados gráficos em linha para a análise de tendências.

Primeiramente foram agrupados os dados de maneira sequêncial, em seguida calculamos as médias mensais de todo o período coletado.

Após a definições das médias, foram gerados gráficos com tendências de movimentação (EMA) utilizando a seguinte fórmula:

```
EMA 
t
​
 =α×(Valor no per 
ı
ˊ
 odo t)+(1−α)×EMA 
t−1
​
 
```
![Preciptação](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/90010232/e7fb871b-13f0-4e4f-9ea4-e166f5d9506d)
Com re

## Descrição dos achados

A partir da análise descrita e exploratória realizada, descreva todos os achados considerados relevantes para o contexto em que o trabalho se insere. Por exemplo: com relação à centralidade dos dados algo chamou a sua atenção? foi possível identificar correlação entre os atributos?

### Centralidade dos Dados


### Identificação de Correlação:


#### Coeficiente de Correlação de Pearson:

Para cada par de variáveis do data set, calculamos o coeficiente de correlação de Pearson (r). Este coeficiente indica a força e a direção da relação linear entre as variáveis.

##### Interpretação do Coeficiente de Correlação:

- Valor próximo de 0: Indica que não há correlação linear entre as variáveis.
- Valor positivo: Indica que existe uma correlação linear positiva. Ou seja, quando uma variável aumenta, a outra também tende a aumentar.
- Valor negativo: Indica que existe uma correlação linear negativa. Ou seja, quando uma variável aumenta, a outra tende a diminuir.
- Valor absoluto próximo de 1: Indica uma forte correlação linear, seja positiva ou negativa.

#### Cálculo do Coeficiente de Correlação:

O coeficiente de correlação de Pearson pode ser calculado usando a seguinte fórmula:

- Criando matriz de correlação
```cor <- cor(dados)```

- Visualizando a matriz de correlação
```cor```

- Selecionando um par de variáveis de interesse

```
x <- dados$Precipitacao_total_horaria
y <- dados$Umidade_relativa_do_ar_horaria
```
- Calculando o coeficiente de correlação e p-valor

```
cor_teste <- cor.test(x, y)
```

- Visualizando os resultados

```
cor_teste
```

```# Teste de correlação entre Precipitação Total Horária e Umidade Relativa do Ar Horária
cor_teste_1 <- cor.test(dados$PRECIPITAÇÃO.TOTAL..HORÁRIO..mm., dados$UMIDADE.RELATIVA.DO.AR..HORARIA....)

# Teste de correlação entre Temperatura do Ar Bulbo Seco Horária e Radiação Global
cor_teste_2 <- cor.test(dados$TEMPERATURA.DO.AR...BULBO.SECO..HORARIA...C., dados$RADIACAO.GLOBAL..Kj.m..)
 
# Teste de correlação entre Temperatura do Ar Bulbo Seco Horária e Umidade Relativa do Ar Horária
cor_teste_3 <- cor.test(dados$TEMPERATURA.DO.AR...BULBO.SECO..HORARIA...C., dados$UMIDADE.RELATIVA.DO.AR..HORARIA....)
 
# Teste de correlação entre Vento, Rajada Máxima e Vento, Velocidade Horária
cor_teste_4 <- cor.test(dados$VENTO..RAJADA.MAXIMA..m.s., dados$VENTO..VELOCIDADE.HORARIA..m.s.)
 
# Teste de correlação entre Temperatura do Ar Bulbo Seco Horária e Pressão Atmosférica ao Nível da Estação
cor_teste_5 <- cor.test(dados$TEMPERATURA.DO.AR...BULBO.SECO..HORARIA...C., dados$PRESSAO.ATMOSFERICA.AO.NIVEL.DA.ESTACAO..HORARIA..mB.)

 # Visualizando os resultados
cor_teste_1
cor_teste_2
cor_teste_3
cor_teste_4
cor_teste_5
```

Onde:

- r: Coeficiente de correlação de Pearson
- x: Valores da primeira variável
- y: Valores da segunda variável


Coeficiente de correlação (r): Indica a força e direção da relação entre as variáveis.
- r = 0: Sem correlação.
- 0 < r < 1: Correlação positiva.
- -1 < r < 0: Correlação negativa.

- Nível de significância (p-valor): Indica a probabilidade da correlação ser aleatória.
- p-valor < 0,05: Correlação significativa (rejeita-se a hipótese nula de que a correlação é igual a zero).
- p-valor > 0,05: Correlação não significativa (não há evidências para rejeitar a hipótese nula).

```
> cor_teste_1

Pearson's product-moment correlation

data:  dados$PRECIPITAÇÃO.TOTAL..HORÁRIO..mm. and dados$UMIDADE.RELATIVA.DO.AR..HORARIA....
t = 26.229, df = 19747, p-value < 2.2e-16
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 0.1699699 0.1969250
sample estimates:
     cor 
0.183482 

> cor_teste_2

Pearson's product-moment correlation

data:  dados$TEMPERATURA.DO.AR...BULBO.SECO..HORARIA...C. and dados$RADIACAO.GLOBAL..Kj.m..
t = 127.89, df = 19747, p-value < 2.2e-16
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 0.6653718 0.6806304
sample estimates:
      cor 
0.6730727 

> cor_teste_3

Pearson's product-moment correlation

data:  dados$TEMPERATURA.DO.AR...BULBO.SECO..HORARIA...C. and dados$UMIDADE.RELATIVA.DO.AR..HORARIA....
t = -123.24, df = 19747, p-value < 2.2e-16
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 -0.6671669 -0.6513984
sample estimates:
       cor 
-0.6593551 

> cor_teste_4

Pearson's product-moment correlation

data:  dados$VENTO..RAJADA.MAXIMA..m.s. and dados$VENTO..VELOCIDADE.HORARIA..m.s.
t = 230.46, df = 19747, p-value < 2.2e-16
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 0.8499685 0.8575298
sample estimates:
      cor 
0.8537942 

> cor_teste_5

Pearson's product-moment correlation

data:  dados$TEMPERATURA.DO.AR...BULBO.SECO..HORARIA...C. and dados$PRESSAO.ATMOSFERICA.AO.NIVEL.DA.ESTACAO..HORARIA..mB.
t = -42.076, df = 19747, p-value < 2.2e-16
alternative hypothesis: true correlation is not equal to 0
95 percent confidence interval:
 -0.2995914 -0.2739921
sample estimates:
      cor 
-0.286843 
```
#### Identificação das Correlações Mais Fortes e Significativas:

Critérios para Identificação:

- Valor absoluto do coeficiente de correlação: Priorizar pares de variáveis com valores absolutos de r próximos de 1.
- Nível de significância: Considerar o nível de significância (p-valor) para verificar se a correlação é estatisticamente significativa. Um p-valor menor que 0.05 geralmente indica uma correlação significativa.


#### Interpretação das Correlações:

- Correlação positiva forte: Uma variável aumenta quando a outra aumenta.
- Correlação negativa forte: Uma variável aumenta quando a outra diminui.
- Correlação fraca: A relação entre as variáveis não é significativa.

Com base nos valores de r e p-valor, identifiquei as seguintes correlações mais fortes e significativas (p-valor < 0,05):

- Teste de correlação entre Precipitação Total Horária e Umidade Relativa do Ar Horária (cor_teste_1):
```
Correlação (r): 0.183
Indica uma correlação positiva fraca entre a precipitação total horária e a umidade relativa do ar horária.
P-value: < 2.2e-16 (muito próximo de zero)
```
Isso significa que a correlação observada é estatisticamente significativa (rejeita-se a hipótese nula de que não há correlação entre as variáveis.

- Teste de correlação entre Temperatura do Ar Bulbo Seco Horária e Radiação Global (cor_teste_2):
```
Correlação (r): 0.673
Indica uma correlação positiva forte entre a temperatura do ar bulbo seco horária e a radiação global.
P-value: < 2.2e-16 (muito próximo de zero)
```
Isso significa que a correlação observada é estatisticamente significativa (rejeita-se a hipótese nula de que não há correlação entre as variáveis.

- Teste de correlação entre Temperatura do Ar Bulbo Seco Horária e Umidade Relativa do Ar Horária (cor_teste_3):
```
Correlação (r): -0.659
Indica uma correlação negativa forte entre a temperatura do ar bulbo seco horária e a umidade relativa do ar horária.
P-value: < 2.2e-16 (muito próximo de zero)
```
Isso significa que a correlação observada é estatisticamente significativa (rejeita-se a hipótese nula de que não há correlação entre as variáveis.

- Teste de correlação entre Vento, Rajada Máxima e Vento, Velocidade Horária (cor_teste_4):
```
Correlação (r): 0.854
Indica uma correlação positiva muito forte entre a velocidade máxima do vento em rajada e a velocidade horária do vento.
P-value: < 2.2e-16 (muito próximo de zero)
```
Isso significa que a correlação observada é estatisticamente significativa (rejeita-se a hipótese nula de que não há correlação entre as variáveis.

- Teste de correlação entre Temperatura do Ar Bulbo Seco Horária e Pressão Atmosférica ao Nível da Estação (cor_teste_5):

```
Correlação (r): -0.287
Indica uma correlação negativa moderada entre a temperatura do ar bulbo seco horária e a pressão atmosférica ao nível da estação.
P-value: < 2.2e-16 (muito próximo de zero)
```
Isso significa que a correlação observada é estatisticamente significativa (rejeita-se a hipótese nula de que não há correlação entre as variáveis.



## Ferramentas utilizadas

Existem muitas ferramentas diferentes que podem ser utilizadas para fazer a análise dos dados. Nesta seção, descreva as ferramentas/tecnologias utilizadas e sua aplicação.

