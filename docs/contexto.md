# Introdução

Ondas de calor: um desafio crescente para a região sudeste do Brasil.

O clima da Terra está em constante mudança, e os impactos das mudanças climáticas são cada vez mais evidentes em todo o mundo. A região sudeste do Brasil, por sua vez, é particularmente vulnerável a eventos climáticos extremos, como secas, inundações e ondas de calor.

Compreender a variabilidade espacial e temporal do clima na região sudeste é crucial para a tomada de decisões em diversos setores da sociedade, como planejamento urbano e regional, gestão de recursos hídricos, agricultura e saúde pública.

Este projeto, utilizando o dataset [Hourly Weather Surface Brazil Southeast Region](https://www.kaggle.com/datasets/PROPPG-PPG/hourly-weather-surface-brazil-southeast-region?resource=download&select=southeast.csv), busca analisar em detalhes as ondas de calor na região, com o objetivo de:

- Avaliar a variabilidade espacial e temporal do clima na região sudeste do Brasil.
- Identificar áreas mais suscetíveis a eventos climáticos extremos.

## Problema

A região sudeste do Brasil, com mais de 80 milhões de habitantes, concentra grande parte da atividade econômica do país, mas também se destaca como uma área altamente vulnerável aos impactos das mudanças climáticas (IPCC, 2021). Eventos climáticos extremos, como secas, inundações e ondas de calor, tornaram-se frequentes e intensos no Brasil, causando danos à infraestrutura, à agricultura e à saúde pública (Marengo, 2023)

Compreender a variabilidade espacial e temporal do clima na região sudeste é crucial para a tomada de decisões em diversos setores da sociedade, como planejamento urbano e regional, gestão de recursos hídricos, agricultura e saúde pública (Marengo, 2020). No entanto, ainda há uma lacuna de conhecimento sobre o clima da região, especialmente em relação aos impactos das mudanças climáticas (CPTEC, 2023).

Este projeto visa analisar a variabilidade climática na região sudeste do Brasil, com foco em:

- Avaliar a variabilidade espacial e temporal do clima:
    - Identificar áreas com diferentes padrões climáticos.
    - Analisar as mudanças climáticas ao longo do tempo.
- Identificar áreas mais suscetíveis a eventos climáticos extremos:
    - Avaliar a vulnerabilidade de diferentes regiões a secas, inundações, ondas de calor e outros eventos.
    - Delinear zonas de risco e auxiliar na tomada de decisões para prevenir e mitigar os impactos desses eventos.
 
A análise da variabilidade climática na região sudeste do Brasil é um tema crucial para a construção de um futuro mais resiliente às mudanças climáticas. Este projeto, ao contribuir para a compreensão do clima da região e seus impactos, espera fornecer subsídios para a tomada de decisões mais eficazes em diversas áreas.

Referências:

- IPCC - Painel Intergovernamental sobre Mudanças Climáticas. Disponível em: https://www.ipcc.ch/report/ar6/wg1/. Acesso em: [03/03/2024].
- Marengo, J. A. (2023). Mudanças climáticas e eventos extremos no Brasil. In: Mudanças Climáticas no Brasil: Causas, Efeitos e Soluções (p. 110). Editora Blucher.
- MARENGO, J.; NOBRE, C.; et al. Mudanças climáticas e seus impactos na região sudeste do Brasil. Revista Brasileira de Meteorologia, v. 35, n. 4, p. 597-612, 2020.
- CENTRO DE PREVISÃO DE TEMPO E ESTUDOS CLIMÁTICOS (CPTEC). Estudos climáticos para a região sudeste do Brasil. Brasília: Ministério da Ciência, Tecnologia e Inovações, 2023.

## Questão de pesquisa

**Quais são os padrões espaciais identificados nas áreas da região sudeste com diferentes frequências e intensidades de ondas de calor, e de que maneira esses padrões têm evoluído ao longo do tempo?**

Essa questão de pesquisa pretende mergulhar na análise das ondas de calor na região sudeste do Brasil, buscando compreender os padrões espaciais que se manifestam em diferentes localidades em termos de frequência e intensidade desses eventos climáticos. A intenção é explorar variáveis como latitude, altitude, cobertura vegetal e características geográficas para identificar regiões que apresentam comportamentos distintos em relação às ondas de calor.

Ela visa ainda delinear as áreas geográficas mais propensas a eventos climáticos extremos, com foco especial em ondas de calor na região sudeste do Brasil. Identificar padrões espaciais e temporais desses eventos é crucial para o desenvolvimento de estratégias de adaptação e mitigação.

Além disso, a pesquisa almeja investigar a evolução desses padrões ao longo do tempo, estabelecendo conexões entre a dinâmica espacial e possíveis mudanças climáticas. Essa abordagem mais aprofundada permitirá uma compreensão mais refinada das peculiaridades de diferentes áreas na região sudeste em relação às ondas de calor.

Consederando isso a abordagem adotada permitirá a criação de mapas que destacam as áreas mais suscetíveis a ondas de calor, facilitando a comunicação de informações cruciais para tomadores de decisão e comunidades locais.

Tal análise temporal,será então, crucial para observar tendências, padrões cíclicos e possíveis anomalias climáticas que possam estar impactando a frequência e intensidade das ondas de calor. Esses insights serão fundamentais não apenas para um entendimento mais preciso do clima na região, mas também para orientar estratégias de adaptação e mitigação diante dos desafios impostos pelas mudanças climáticas. Em última análise, o objetivo é fornecer informações substanciais para tomadas de decisões embasadas em dados concretos, contribuindo para a resiliência da região frente às variações climáticas.

## Objetivos preliminares

### Objetivo Geral:

Analisar a variabilidade climática na região sudeste do Brasil, com foco em ondas de calor, para contribuir com a construção de um futuro mais resiliente às mudanças climáticas, utilizando o dataset "Hourly Weather Surface Brazil Southeast Region" e técnicas de Machine Learning.

### Objetivos Específicos:

1. Avaliar a variabilidade espacial e temporal das ondas de calor na região sudeste do Brasil:

- Identificar áreas com diferentes padrões de frequência e intensidade de ondas de calor.
- Analisar as mudanças na frequência, intensidade e duração das ondas de calor ao longo do tempo.
- Quantificar os impactos das ondas de calor em diferentes setores da sociedade, como saúde, agricultura e infraestrutura.

2. Identificar áreas mais suscetíveis a ondas de calor:

- Delinear zonas de risco para eventos de ondas de calor, considerando fatores como temperatura, precipitação, cobertura vegetal e topografia.
- Avaliar a vulnerabilidade de diferentes regiões e populações aos impactos das ondas de calor.
- Propor medidas de adaptação e mitigação para reduzir os impactos das ondas de calor nas áreas mais suscetíveis.

3. Desenvolver um modelo preditivo para a ocorrência de ondas de calor:

- Selecionar variáveis climáticas e socioeconômicas relevantes para a previsão de ondas de calor.
- Aplicar técnicas de aprendizado de máquina para desenvolver um modelo preditivo robusto e confiável.
- Validar o modelo preditivo em diferentes cenários e temporalidades.

4. Considerações Éticas e Sociais:

- A pesquisa será conduzida em conformidade com os princípios éticos da pesquisa científica.
- Os resultados da pesquisa serão divulgados de forma transparente e acessível à comunidade científica e à sociedade em geral.
- Os impactos sociais e éticos da pesquisa serão considerados e mitigados.

Referências:
- Blog Mettzer - Diferença entre Objetivo geral e Objetivo Específico. Disponível em: https://blog.mettzer.com/diferenca-entre-objetivo-geral-e-objetivo-especifico/. Acesso em 02/03/2024.
- Kotler, P., & Armstrong, G. (2018). Principles of marketing (17th ed.). Pearson.

## Justificativa

A compreensão precisa dos padrões climáticos é crucial para diversas esferas da sociedade, incluindo planejamento urbano, agrícola e prevenção de desastres naturais (Fonte: WMO, 2020). No entanto, as mudanças climáticas têm aumentado a volatilidade desses padrões, tornando essencial o desenvolvimento de métodos avançados de previsão (IPCC, 2019). Nesse contexto, a aplicação de técnicas de machine learning em dados climáticos históricos se mostra relevante (NOAA, 2018).

A precisão das previsões climáticas é fundamental para a preparação e adaptação às condições meteorológicas extremas (Fonte: IPCC, 2018). Além disso, a capacidade de antecipar mudanças climáticas de longo prazo é essencial para o planejamento eficaz em diversas áreas (WMO, 2021).

### Objetivos Específicos:

- Precisão das Previsões: A utilização de machine learning em dados climáticos pode identificar padrões sutis, resultando em previsões mais precisas e confiáveis (NOAA, 2019).

- Adaptação e Mitigação: Compreender os padrões climáticos permite uma melhor adaptação às mudanças climáticas e implementação de medidas de mitigação mais eficazes (IPCC, 2020).

- Alerta de Desastres Naturais: Modelos de machine learning podem auxiliar na detecção precoce de eventos climáticos extremos, facilitando o planejamento e a resposta a desastres (WMO, 2019).

### Profundidade do Estudo:

O estudo das mudanças climáticas e seus impactos é crucial, especialmente considerando o aumento da frequência e intensidade de eventos climáticos extremos (IPCC, 2021). Além disso, tais eventos têm um impacto significativo na saúde pública e na economia (Fonte: NOAA, 2020).

### Impacto na Sociedade:

A melhoria das previsões climáticas reduz os riscos para a vida e a propriedade, aumentando a resiliência das comunidades (WMO, 2022). Além disso, contribui para uma melhor qualidade de vida ao garantir acesso a recursos essenciais, mesmo em situações adversas (IPCC, 2017).

Referências:

IPCC. (2017). Relatório Especial sobre Aquecimento Global de 1,5 °C.
NOAA. (2020). National Oceanic and Atmospheric Administration.
WMO. (2022). World Meteorological Organization.

## Público-Alvo

### Perfil dos Usuários e sua Relação com a Tecnologia:


- Agricultores e produtores rurais têm conhecimento prático das condições climáticas que afetam suas safras, mas podem não possuir conhecimento científico especializado em meteorologia. Eles estão abertos a adotar tecnologias que os ajudem a melhorar a produtividade e a mitigar os riscos climáticos em suas operações agrícolas.


- Gestores de recursos naturais e ambientais possuem um conhecimento mais profundo dos padrões climáticos e sua interação com os ecossistemas naturais. Estão familiarizados com tecnologias de monitoramento ambiental e estão abertos à adoção de soluções baseadas em machine learning para melhorar a gestão e conservação dos recursos naturais.


- Cientistas e pesquisadores em climatologia têm um alto nível de especialização na área e estão interessados em explorar novas abordagens, como machine learning, para melhorar a precisão das previsões climáticas.


- Administradores públicos e tomadores de decisão possuem um entendimento básico das questões climáticas e estão focados em políticas públicas e tomada de decisões relacionadas ao meio ambiente e desenvolvimento sustentável. Reconhecem a importância da tecnologia como uma ferramenta para embasar suas decisões e políticas.


O público em geral possui um entendimento básico das mudanças climáticas e está aberto a utilizar tecnologias que os ajudem a se preparar para eventos climáticos extremos e tomar decisões informadas sobre suas atividades diárias. Geralmente buscam facilidade de uso e acesso simplificado às informações climáticas.

## Estado da arte

### Abordagens na Literatura para Previsão do Tempo

Nesta seção, apresentaremos um panorama de pesquisas relacionadas à previsão do tempo, com foco em trabalhos que utilizaram dados em contexto similar ao dataset "Hourly Weather Surface Brazil Southeast Region". Abordaremos o problema em questão, detalharemos os datasets, descreveremos as metodologias e algoritmos empregados, as métricas de avaliação utilizadas e os resultados obtidos em cada estudo.

1. Big Data Analytics using Deep LSTM Networks: A Case Study for Weather Prediction

- Problema: O estudo demonstra o potencial de redes neurais LSTM para previsão do tempo, utilizando um conjunto de dados global.

- Dataset: Base de dados pública com dados climáticos de diferentes regiões do mundo, incluindo temperatura, precipitação e vento.

- Abordagem/Algoritmo: Redes Neurais Recorrentes com Memória de Longo Prazo (LSTMs).

- Métricas de Avaliação: Erro Médio Quadrático (MSE) e Coeficiente de Correlação (R²).

- Resultados: O modelo LSTM obteve um MSE de 1,5 °C e um R² de 0,95 na previsão da temperatura, demonstrando sua capacidade de generalização para diferentes regiões.

Referência:

Sangwan, O., & Kumar, A. (2020). Big Data Analytics using Deep LSTM Networks: A Case Study for Weather Prediction. International Journal of Advanced Research in Computer and Communication Engineering, 9(21), 4641-4646. Disponível em : <https://www.researchgate.net/profile/Om-Sangwan/publication/339857640_Big_Data_Analytics_using_Deep_LSTM_Networks_A_Case_Study_for_Weather_Prediction/links/5ea42643a6fdccd79451e02a/Big-Data-Analytics-using-Deep-LSTM-Networks-A-Case-Study-for-Weather-Prediction.pdf>. Acesso em 04.03.2024

2. Análise da Variabilidade da Precipitação para o Estado de Minas Gerais (1981-2017).

- Problema: O estado de Minas Gerais, localizado na região sudeste do Brasil, enfrenta desafios significativos relacionados à variabilidade da precipitação, que afetam diretamente diversos setores econômicos e a gestão de recursos hídricos. Compreender a distribuição temporal e espacial da precipitação é essencial para o planejamento adequado e a tomada de decisões em face das mudanças climáticas e seus impactos.
- Dataset: O estudo utilizou dados de precipitação mensal do produto Climate Hazards Group InfraRed Precipitation with Stations (CHIRPS) para o período de 1981 a 2017. Esses dados oferecem uma cobertura global e são baseados em uma combinação de dados de satélite e observações de estações meteorológicas terrestres.
  
- Dataset Utilizado: O estudo utilizou dados de precipitação mensal do produto Climate Hazards Group InfraRed Precipitation with Stations (CHIRPS) para o período de 1981 a 2017. Esses dados oferecem uma cobertura global e são baseados em uma combinação de dados de satélite e observações de estações meteorológicas terrestres.

- Abordagens/Algoritmos Utilizados:
    - Análise de Componentes Principais (ACP): Utilizada para agrupar o estado de Minas Gerais em regiões homogêneas, removendo redundâncias de informações e facilitando a análise.
    - Técnica de Mínimos Quadrados: Aplicada para calcular a tendência espacial da precipitação, utilizando a função ltrend no aplicativo Grads.
    - Estimativa do Início e Término da Estação Chuvosa: Utilizou-se a técnica descrita em Liebmann et al. (2012) para determinar o início e término da estação chuvosa em cada região.

- Métricas de Avaliação: As métricas de avaliação utilizadas no estudo não foram explicitamente mencionadas, mas podem incluir medidas de tendência, como inclinação das linhas de tendência para determinar mudanças na duração da estação chuvosa ao longo do tempo, e comparação das características climáticas entre diferentes regiões de Minas Gerais.

- Resultados Obtidos: Os resultados indicam que Minas Gerais foi dividido em sete regiões climáticas distintas, cada uma apresentando características próprias de precipitação. De forma geral, o estado possui uma estação úmida que ocorre de outubro a março e uma estação seca de abril a setembro. A duração média da estação chuvosa varia nas diferentes regiões, com uma média aproximada de 183 dias. A análise da tendência da duração chuvosa mostra variações significativas entre as regiões, com algumas apresentando uma tendência de diminuição da estação chuvosa, enquanto outras mostram uma tendência de aumento. Esses resultados fornecem insights importantes para o entendimento da variabilidade da precipitação em Minas Gerais e têm implicações significativas para o planejamento e gestão de recursos hídricos.

Referência:
Pereira, Gabriel et al. "Análise da Variabilidade da Precipitação para o Estado de Minas Gerais (1981-2017)." Revista Brasileira de Climatologia, v. 32, n. 2, p. 213-228, ano não especificado. Disponível em: <https://ojs.ufgd.edu.br/index.php/rbclima/article/view/14068/7309>. Acesso em: 09.03.2024.

3. A Vulnerabilidade Social da Região Sudeste do Brasil Frente à Variabilidade Climática

- Problema: A compreensão da relação entre vulnerabilidade social e os efeitos das mudanças climáticas é crucial para a adaptação e mitigação dos impactos dessas mudanças. O estudo realizado por Kuroki et al. (ano não especificado) tem como objetivo correlacionar a precipitação e as temperaturas máxima e mínima dos estados da região Sudeste do Brasil com o índice de vulnerabilidade social na região.

- Dataset Utilizado: O estudo utilizou dados de precipitação e temperaturas máxima e mínima dos estados da região Sudeste do Brasil, no período de 2010 a 2019. Os dados de vulnerabilidade social foram obtidos a partir do Índice de Vulnerabilidade Social (IVS) da região.

- Abordagens/Algoritmos Utilizados: Correlação de Pearson: Foi realizada uma correlação simples de Pearson entre a variabilidade climática (precipitação, temperaturas máxima e mínima) e o Índice de Vulnerabilidade Social (IVS) da região Sudeste do Brasil.
  
- Métricas de Avaliação: A métrica utilizada foi o coeficiente de correlação de Pearson (r), que varia de -1 a +1, onde valores próximos de +1 indicam uma correlação positiva entre as variáveis, ou seja, à medida que uma variável aumenta, a outra também aumenta.

- Resultados Obtidos: Os resultados mostraram que, em termos de vulnerabilidade a eventos climáticos, a região Sudeste do Brasil é mais sensível e suscetível aos danos ocasionados pelas chuvas em comparação aos impactos decorrentes da variação de temperatura na região. Quanto à correlação entre a variabilidade climática e a vulnerabilidade social, identificou-se uma relação positiva, com valores de correlação de até +0,51, entre a variabilidade climática e as chuvas persistentes típicas do fenômeno Zona de Convergência do Atlântico Sul (ZCAS). Isso reforça que a precipitação é uma variável meteorológica influente sobre a vulnerabilidade social na região Sudeste do Brasil. Além disso, os resultados destacam que a mudança global do clima pode influenciar negativamente o clima em escala regional e local, trazendo danos à sociedade associados à sua resiliência e capacidade adaptativa.

Referência:
Kuroki, Larissa Yumi et al. "A Vulnerabilidade Social da Região Sudeste do Brasil Frente à Variabilidade Climática." Revista Brasileira de Climatologia, ano não especificado. Disponível em: <https://ojs.ufgd.edu.br/index.php/rbclima/article/view/15903/9032>. Acesso em: 09.03.2024.

# Descrição do _dataset_ selecionado

- **Link de Acesso:** [Hourly Weather Surface Brazil Southeast Region](https://www.kaggle.com/datasets/PROPPG-PPG/hourly-weather-surface-brazil-southeast-region?resource=download&select=southeast.csv)
- **Nome do Dataset:** Hourly Weather Surface Brazil Southeast Region
- **Número de Registros:** 9.466.848
- **Número de Atributos:** 24

## Descrição dos Atributos:

| Nome do Atributo             | Tipo             | Descrição                                          |
|------------------------------|------------------|----------------------------------------------------|
| Data                         | datetime64[ns]   | Data e hora da medição                             |
| Estação                      | int64            | Identificador único da estação meteorológica       |
| Latitude                     | float64          | Latitude da estação meteorológica                  |
| Longitude                    | float64          | Longitude da estação meteorológica                 |
| Altitude                     | float64          | Altitude da estação meteorológica                  |
| Temperatura (°C)             | float64          | Temperatura do ar em graus Celsius                 |
| Ponto de Orvalho (°C)        | float64          | Ponto de orvalho em graus Celsius                  |
| Umidade Relativa (%)         | float64          | Umidade relativa do ar em porcentagem              |
| Pressão Atmosférica (hPa)    | float64          | Pressão atmosférica em hectopascal                 |
| Radiação Solar Global (W/m²) | float64          | Radiação solar global em watts por metro quadrado   |
| Velocidade do Vento (m/s)    | float64          | Velocidade do vento em metros por segundo          |
| Direção do Vento (°)         | float64          | Direção do vento em graus                          |
| Precipitação Total (mm)      | float64          | Precipitação total em milímetros                   |
| Precipitação Convectiva (mm) | float64          | Precipitação convectiva em milímetros              |
| Precipitação Estratiforme (mm)| float64          | Precipitação estratiforme em milímetros            |
| Neve Total (mm)              | float64          | Neve total em milímetros                           |
| Cobertura de Nuvens (%)      | float64          | Cobertura de nuvens em porcentagem                 |
| Visibilidade (km)            | float64          | Visibilidade em quilômetros                        |
| Qualidade do Ar              | int64            | Qualidade do ar (0-100)                            |
| Sensação Térmica (°C)        | float64          | Sensação térmica em graus Celsius                  |
| Índice UV                    | float64          | Índice UV                                          |

## Atributos faltantes:
O dataset não possui atributos faltantes.

## Distribuição dos Atributos:
A distribuição dos atributos pode ser visualizada no notebook disponibilizado no Kaggle.

## Formatos dos Atributos:
Todos os atributos são numéricos, com exceção de "Data" e "Qualidade do Ar".

## Considerações:
- O dataset é uma excelente fonte de dados para estudos sobre o clima da região sudeste do Brasil.
- A grande quantidade de registros e a variedade de atributos permitem realizar análises complexas e detalhadas.
- O dataset está disponível em formato CSV, o que facilita o acesso e a manipulação dos dados.

## Referências:
- Kaggle - Hourly Weather Surface Brazil Southeast Region. Disponível em: <https://www.kaggle.com/datasets/PROPPG-PPG/hourly-weather-surface-brazil-southeast-region>
- Alves, L. M., & Pereira, J. M. C. (2023). Hourly Weather Surface Brazil Southeast Region. Kaggle. Disponível em: <https://www.kaggle.com/datasets/PROPPG-PPG/hourly-weather-surface-brazil-southeast-region>


# Canvas analítico

Nesta seção, você deverá estruturar o seu Canvas Analítico. O Canvas Analítico tem o papel de registrar a organização das ideias e apresentar o modelo de negócio.

> **Links Úteis**:
> - [Modelo do Canvas Analítico](https://github.com/ICEI-PUC-Minas-PMV-SI/PesquisaExperimentacao-Template/blob/main/help/Software-Analtics-Canvas-v1.0.pdf)

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho utilizando o padrão ABNT.

- Alves, L. M., & Pereira, J. M. C. (2023). Hourly Weather Surface Brazil Southeast Region. Kaggle. Disponível em: <https://www.kaggle.com/datasets/PROPPG-PPG/hourly-weather-surface-brazil-southeast-region>
- Blog Mettzer - Diferença entre Objetivo geral e Objetivo Específico. Disponível em: <https://blog.mettzer.com/diferenca-entre-objetivo-geral-e-objetivo-especifico/>. Acesso em 02/03/2024.
- CENTRO DE PREVISÃO DE TEMPO E ESTUDOS CLIMÁTICOS (CPTEC). Estudos climáticos para a região sudeste do Brasil. Brasília: Ministério da Ciência, Tecnologia e Inovações, 2023.
- IPCC - Painel Intergovernamental sobre Mudanças Climáticas. Disponível em: <https://www.ipcc.ch/report/ar6/wg1/>. Acesso em: [03/03/2024].
- Kaggle - Hourly Weather Surface Brazil Southeast Region. Disponível em: <https://www.kaggle.com/datasets/PROPPG-PPG/hourly-weather-surface-brazil-southeast-region>
- Kuroki, Larissa Yumi et al. "A Vulnerabilidade Social da Região Sudeste do Brasil Frente à Variabilidade Climática." Revista Brasileira de Climatologia, ano não especificado. Disponível em: <https://ojs.ufgd.edu.br/index.php/rbclima/article/view/15903/9032>. Acesso em: 09.03.2024.
- Kotler, P., & Armstrong, G. (2018). Principles of marketing (17th ed.). Pearson.
- Marengo, J. A. (2023). Mudanças climáticas e eventos extremos no Brasil. In: Mudanças Climáticas no Brasil: Causas, Efeitos e Soluções (p. 110). Editora Blucher.
- MARENGO, J.; NOBRE, C.; et al. Mudanças climáticas e seus impactos na região sudeste do Brasil. Revista Brasileira de Meteorologia, v. 35, n. 4, p. 597-612, 2020.
- Pereira, Gabriel et al. "Análise da Variabilidade da Precipitação para o Estado de Minas Gerais (1981-2017)." Revista Brasileira de Climatologia, v. 32, n. 2, p. 213-228, ano não especificado. Disponível em: <https://ojs.ufgd.edu.br/index.php/rbclima/article/view/14068/7309>. Acesso em: 09.03.2024.
- Sangwan, O., & Kumar, A. (2020). Big Data Analytics using Deep LSTM Networks: A Case Study for Weather Prediction. International Journal of Advanced Research in Computer and Communication Engineering, 9(21), 4641-4646. Disponível em : <https://www.researchgate.net/profile/Om-Sangwan/publication/339857640_Big_Data_Analytics_using_Deep_LSTM_Networks_A_Case_Study_for_Weather_Prediction/links/5ea42643a6fdccd79451e02a/Big-Data-Analytics-using-Deep-LSTM-Networks-A-Case-Study-for-Weather-Prediction.pdf>. Acesso em 04.03.2024






