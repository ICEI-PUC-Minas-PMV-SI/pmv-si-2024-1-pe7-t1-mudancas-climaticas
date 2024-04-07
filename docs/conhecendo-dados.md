# Conhecendo os dados

### Estrutura dos Dados

O dataset contém 37.946 linhas e 23 colunas, com informações horárias sobre diversas variáveis climáticas, como:

1. Variáveis Climáticas:

- Precipitação total horária (mm)
- Pressão atmosférica ao nível da estação, horária (mb)
- Pressão atmosférica máxima na hora anterior (AUT) (mb)
- Pressão atmosférica mínima na hora anterior (AUT) (mb)
- Radiação global (Kj/m²)
- Temperatura do ar bulbo seco, horária (°C)
- Temperatura do ponto de orvalho (°C)
- Temperatura máxima na hora anterior (AUT) (°C)
- Temperatura mínima na hora anterior (AUT) (°C)
- Temperatura orvalho máxima na hora anterior (AUT) (°C)
- Temperatura orvalho mínima na hora anterior (AUT) (°C)
- Umidade relativa do ar, horária (%)
- Umidade relativa máxima na hora anterior (AUT) (%)
- Umidade relativa mínima na hora anterior (AUT) (%)
- Vento, direção horária (gr) (° (gr))
- Vento, rajada máxima (m/s)
- Vento, velocidade horária (m/s)

2. Variáveis Temporais:
   
- Ano

3. Variáveis Derivadas:
   
- Amplitude térmica

-  ### Medidas de Tendência Central



  #### Mapa de Calor

![Captura de tela 2024-04-07 174045](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/81424548/7592f817-8d1d-4d78-99be-fa4d2a5445dc)

##### Interpretando as Correlações:

- Azul escuro: Correlação positiva. Aumento em uma variável está associado ao aumento na outra.
- Azul turquesa escuro: Correlação positiva forte.
- Azul turquesa: Correlação positiva fraca.
- Azul turquesa claro: Correlação negativa. Aumento em uma variável está associado à diminuição na outra.
- Azul céu: Correlação negativa forte.
- Azul claro: Correlação negativa fraca.
- Azul claro: Ausência de correlação.

  #### Resumo dos Achados:

##### Pressao e Vento

A correlação entre as variáveis de Precipitação, Pressão Atmosférica, Pressão Máxima e Pressão Mínima, todas com correlações acima de 0.94, é um reflexo da interdependência desses parâmetros meteorológicos. Mudanças na pressão atmosférica podem indicar a chegada de sistemas de alta ou baixa pressão, que por sua vez influenciam a formação de nuvens e a ocorrência de precipitação. Portanto, é esperado que essas variáveis apresentem forte correlação entre si.

Por outro lado, a correlação de acima de 0.84 entre Direção do Vento, Rajada Máxima e Velocidade do Vento sugere uma associação moderada entre esses parâmetros. A direção e a intensidade do vento podem ser influenciadas tanto pela topografia local quanto pelos padrões de pressão atmosférica. Por exemplo, em áreas montanhosas, a direção e a intensidade do vento podem ser influenciadas pela orientação das montanhas. Além disso, a pressão atmosférica pode influenciar os padrões de vento devido ao movimento do ar de áreas de alta pressão para áreas de baixa pressão.

Portanto, é razoável esperar uma correlação entre esses conjuntos de variáveis, pois todas estão intrinsecamente ligadas às condições atmosféricas locais e regionais. No entanto, a correlação de 0.84 pode indicar que outros fatores além desses estão influenciando as variações nas direções e velocidades do vento. Talvez a topografia local, a presença de corpos d'água ou a sazonalidade também desempenhem um papel significativo na determinação dos padrões de vento observados.

##### Temperatura

A correlação extremamente alta de mais de 0.98 entre a Temperatura e as temperaturas máxima e mínima (TempMax e TempMin) é esperada e indicativa de um forte relacionamento entre essas variáveis. A temperatura do ar é uma medida direta da energia térmica presente na atmosfera em um determinado local e momento, e as temperaturas máxima e mínima representam os extremos alcançados ao longo de um período específico.

A alta correlação entre a Temperatura e as temperaturas máxima e mínima sugere que elas variam juntas de maneira consistente. Isso é coerente com o conceito de que a temperatura do ar durante o dia tende a atingir seu valor máximo (TempMax) e diminuir até o mínimo (TempMin) durante a noite. Portanto, é esperado que essas variáveis estejam altamente correlacionadas, refletindo as mudanças diárias e sazonais na temperatura do ar.

Além disso, a alta correlação indica que as mudanças na temperatura do ar são bem representadas pelas variações nas temperaturas máxima e mínima. Essa forte associação pode ser útil para prever as condições meteorológicas e entender melhor os padrões climáticos locais e regionais.

##### Ponto de Orvalho e Humidade


A alta correlação de mais de 0.92 entre as variáveis relacionadas ao ponto de orvalho (TempOrvalhoMax e TempOrvalhoMin) e à umidade relativa do ar (UmidadeMax, UmidadeMin e UmidadeRelativa), juntamente com a temperatura, indica uma forte associação entre esses parâmetros meteorológicos.

O ponto de orvalho é a temperatura na qual o vapor de água presente no ar se condensa para formar gotículas de água, e a umidade relativa do ar é a medida da quantidade de vapor de água presente na atmosfera em relação à quantidade máxima que poderia ser retida a uma determinada temperatura. Portanto, é esperado que essas variáveis estejam intimamente relacionadas, pois todas estão relacionadas à quantidade de umidade na atmosfera.

A alta correlação entre o ponto de orvalho máximo e mínimo e a umidade relativa sugere que essas variáveis tendem a variar juntas de maneira consistente. Quando a umidade relativa do ar aumenta, a temperatura na qual o orvalho se forma (ponto de orvalho) também tende a aumentar, pois há mais vapor de água na atmosfera. Da mesma forma, quando a umidade relativa diminui, o ponto de orvalho também tende a diminuir.


A partir da análise descrita e exploratória realizada, descreva todos os achados considerados relevantes para o contexto em que o trabalho se insere. Por exemplo: com relação à centralidade dos dados algo chamou a sua atenção? foi possível identificar correlação entre os atributos?

### Visual dos Dados
Após o tratamento da base de dados foram gerados gráficos em linha para a análise de tendências.

Primeiramente foram agrupados os dados de maneira sequêncial, em seguida calculamos as médias mensais de todo o período coletado.

Após a definições das médias, foram gerados gráficos com tendências de movimentação (EMA) utilizando a seguinte fórmula:

![image](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/90010232/3a469fb6-5c3f-4aff-80ba-e91b486be253)

Onde:

- EMAt é a Média Móvel Exponencial para o período t.
- Valor no período t é o valor da série temporal no período t.
- EMAt−1 é a EMA calculada para o período anterior t−1.
- α é o fator de suavização calculado na etapa 1.

#### Tendência de Movimentação da Precipitação
![Preciptação](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/90010232/e7fb871b-13f0-4e4f-9ea4-e166f5d9506d)
Após analisar o gráfico podemos perceber que o maior volume de precipitação tende a ser entre os meses de Outubro e Abril, sendo as estações de primavera e verão.

Importante indicar o alto volume indicado no início de 2020 e de 2021, sendo muito acima da linha de tendência calculada.

### Tendência de Movimentação da Pressão Atmosférica
![Pressao Atmosferica](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/90010232/e552475c-2ffd-4948-9f5a-6438ff1491f1)
Após análise do grafico, percebece que os valores mais baixos são apresentados nos entre os meses de Outubro e Abril. Quanto aos valores mais altos estão presentes entre Maio e Setembro.

### Tendência de Movimentação da Radiação Global
![Radiação](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/90010232/3f16398e-1164-4e60-87ea-38304e7c2266)
Ao analisar os dados da radiação global percebe-se uma queda brusca nos valores coletados a partir de 2021, indicando uma possível falha na coleta dos dados

### Tendência de Movimentação da Temperatura
![Temperatura](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/90010232/f825e72c-c6d8-4308-9c8e-422169f8beca)
Após análise da tendência da temperatura percebece que as temperaturas mais baixas estão presentes nos meses de Maio a Agosto. Quanto aos valores mais altos, estão presentes picos esporádicos em diferentes momentos do ano.

### Tendência de Movimentação da Umidade
![Umidade Relativa](https://github.com/ICEI-PUC-Minas-PMV-SI/pmv-si-2024-1-pe7-t1-mudancas-climaticas/assets/90010232/3ca60a05-cd58-4f57-9a99-3e4203a14728)
Quando analisado, o gráfico de movimentação da umidade apresenta seus valores mais altos entre os meses de Outubro a Abril e seus valores mais baixos nos meses de Maio a Setembro.

## Conclusões das Análises

- As variáveis temperatura, precipitação e umidade estão diretamente ligadas, sendo que todas apresentam uma tendência semelhante em seus movimentos de aumento e queda de valores.
- Os valores da pressão atmosferica tendem a ser bem constantes e não influênciar nas outras variáveis.
- Existe uma possível perda dos dados a partir de 2021, onde podemos perceber uma queda significativa em algumas variáveis.
## Descrição dos achados

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


#### Conclusão

- Correlação entre Precipitação Total Horária e Umidade Relativa do Ar Horária:

Coeficiente de Correlação (r): 0.1835
Interpretation: Existe uma correlação positiva fraca entre a precipitação total horária e a umidade relativa do ar horária. Isso sugere que, em geral, períodos com maior umidade relativa do ar podem estar associados a uma maior precipitação, embora a relação seja relativamente fraca.

- Correlação entre Temperatura do Ar Bulbo Seco Horária e Radiação Global:

Coeficiente de Correlação (r): 0.6731
Interpretation: Existe uma correlação positiva forte entre a temperatura do ar bulbo seco horária e a radiação global. Isso indica que períodos com temperaturas mais altas estão associados a níveis mais elevados de radiação solar.

- Correlação entre Temperatura do Ar Bulbo Seco Horária e Umidade Relativa do Ar Horária:

Coeficiente de Correlação (r): -0.6594
Interpretation: Existe uma correlação negativa forte entre a temperatura do ar bulbo seco horária e a umidade relativa do ar horária. Isso sugere que períodos com temperaturas mais altas estão associados a níveis mais baixos de umidade relativa do ar, e vice-versa.

- Correlação entre Vento, Rajada Máxima e Vento, Velocidade Horária:

Coeficiente de Correlação (r): 0.8538
Interpretation: Existe uma correlação positiva muito forte entre a velocidade máxima do vento e a velocidade horária do vento. Isso indica que, em geral, períodos com ventos mais fortes tendem a ter velocidades horárias mais altas e vice-versa.

- Correlação entre Temperatura do Ar Bulbo Seco Horária e Pressão Atmosférica ao Nível da Estação:

Coeficiente de Correlação (r): -0.2868
Interpretation: Existe uma correlação negativa moderada entre a temperatura do ar bulbo seco horária e a pressão atmosférica ao nível da estação. Isso sugere que períodos com temperaturas mais altas estão associados a níveis mais baixos de pressão atmosférica, e vice-versa.


## Ferramentas utilizadas

- Comprehensive R Archive Network (CRAN): repositório de software que hospeda uma vasta coleção de pacotes e bibliotecas para a linguagem de programação R. Esses pacotes oferecem uma variedade de funcionalidades estatísticas, gráficas e de análise de dados.
  
- Linguagem de Programação: Python
  
- Jupyter, aplicação web de código aberto.
