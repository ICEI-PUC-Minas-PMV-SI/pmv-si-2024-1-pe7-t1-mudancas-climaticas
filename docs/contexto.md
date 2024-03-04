# Introdução

Ondas de calor: um desafio crescente para a região sudeste do Brasil.

Caracterizadas por temperaturas anormalmente elevadas por períodos prolongados, as ondas de calor representam uma séria ameaça à saúde humana da região.

Este projeto, utilizando o dataset [Hourly Weather Surface Brazil Southeast Region](https://www.kaggle.com/datasets/PROPPG-PPG/hourly-weather-surface-brazil-southeast-region?resource=download&select=southeast.csv), busca analisar em detalhes as ondas de calor na região, com o objetivo de:

1. Quantificar o Impacto das Ondas de Calor na Mortalidade:

- Analisar a relação entre temperatura e mortalidade:
  - Identificar os grupos mais vulneráveis às ondas de calor.
  - Quantificar o aumento da mortalidade durante eventos de calor extremo.
  - Avaliar o efeito de outros fatores, como idade, sexo e comorbidades.
- Desenvolver modelos preditivos para estimar o aumento da mortalidade:
  - Prever o número de mortes em excesso durante ondas de calor.
  - Identificar áreas de maior risco.
  - Auxiliar na tomada de decisões para proteger a saúde pública.

## Problema

Nesta seção, você deve apresentar o problema que a sua investigação/experimentação busca resolver. Por exemplo, caso o _dataset_ selecionado, seja um _dataset_ que contenha uma série temporal com o preço de diversas ações da bolsa de valores, o problema pode estar relacionado a dificuldade em saber a melhor hora (hora certa??) de comprar ou então, de executar a venda de uma determinada ação.

Descreva ainda o contexto em que essa aplicação será usada, se houver: empresa parceira, tecnologias etc. Novamente, descreva apenas o que de fato existir, pois ainda não é a hora de apresentar requisitos  detalhados ou projetos.

> **Links Úteis**:
> - [Objetivos, Problema de pesquisa e Justificativa](https://medium.com/@versioparole/objetivos-problema-de-pesquisa-e-justificativa-c98c8233b9c3)
> - [Matriz Certezas, Suposições e Dúvidas](https://medium.com/educa%C3%A7%C3%A3o-fora-da-caixa/matriz-certezas-suposi%C3%A7%C3%B5es-e-d%C3%BAvidas-fa2263633655)
> - [Brainstorming](https://www.euax.com.br/2018/09/brainstorming/)

A região sudeste do Brasil enfrenta um desafio crescente: as ondas de calor. Caracterizadas por temperaturas anormalmente elevadas por períodos prolongados, elas representam uma séria ameaça à saúde humana, com impactos significantes na mortalidade, especialmente em grupos vulneráveis. O problema central reside na dificuldade de prever com precisão a ocorrência e a severidade das ondas de calor. Essa imprevisibilidade limita a capacidade de tomar medidas proativas para mitigar seus impactos negativos. A falta de dados precisos e ferramentas de previsão limita a capacidade de tomar medidas eficazes para proteger a população.

Portanto, este projeto busca contribuir para a solução do problema através da análise de dados históricos e da aplicação de técnicas de Machine Learning. O objetivo é desenvolver modelos robustos para prever ondas de calor com maior precisão, possibilitando ações proativas e mitigadoras.

## Questão de pesquisa

A questão de pesquisa é a base de todo o trabalho que será desenvolvido. É ela que motiva a realização da pesquisa e deverá ser adequada ao problema identificado. Ao término de sua pesquisa/experimentação, o objetivo é que seja encontrada a resposta da questão de pesquisa previamente definida.

> **Links Úteis**:
> - [Questão de pesquisa](https://www.enago.com.br/academy/how-to-develop-good-research-question-types-examples/)
> - [Problema de pesquisa](https://blog.even3.com.br/problema-de-pesquisa/)

## Objetivos preliminares

Aqui você deve descrever os objetivos preliminares do trabalho indicando que o objetivo geral é experimentar modelos de aprendizado de máquina adequados para solucionar o problema apresentado acima. 

Apresente também alguns (pelo menos 2) objetivos específicos dependendo de onde você vai querer concentrar a sua prática investigativa, ou como você vai aprofundar no seu trabalho.

Por exemplo: um objetivo específico pode estar relacionado a predizer a tendência de alta, estabilidade ou queda de uma determinada ação em uma determinada janela do tempo ou então, predizer o valor exato de uma determinada ação.
Lembre-se que, à medida que a pesquisa/experimentação evolui, os objetivos podem evoluir também, portanto, não se esqueça de fazer as atualizações necessárias.
 
> **Links Úteis**:
> - [Objetivo geral e objetivo específico: como fazer e quais verbos utilizar](https://blog.mettzer.com/diferenca-entre-objetivo-geral-e-objetivo-especifico/)

### Objetivo Geral:

Analisar e prever ondas de calor na região sudeste do Brasil utilizando o dataset "Hourly Weather Surface Brazil Southeast Region" e técnicas de Machine Learning.

### Objetivos Específicos:

1. Quantificar o Impacto das Ondas de Calor na Mortalidade:

- Analisar a série temporal de dados climáticos e de mortalidade:
- Identificar padrões e tendências.
- Quantificar o aumento da mortalidade durante ondas de calor.
- Avaliar a influência de outros fatores, como idade, sexo e comorbidades.

2. Desenvolver modelos de Machine Learning para prever o aumento da mortalidade:
- Prever o número de mortes em excesso durante ondas de calor.
- Identificar áreas de maior risco.
- Auxiliar na tomada de decisões para proteger a saúde pública.

3. Evolução dos Objetivos:

Os objetivos específicos podem ser revisados e aprimorados ao longo da pesquisa, de acordo com:

- Resultados da análise exploratória dos dados.
- Disponibilidade de novos dados e recursos.
- Descobertas e insights obtidos durante a investigação.

4. Considerações Éticas e Sociais:

- A pesquisa será conduzida em conformidade com os princípios éticos da pesquisa científica.
- Os resultados da pesquisa serão divulgados de forma transparente e acessível à comunidade científica e à sociedade em geral.
- Os impactos sociais e éticos da pesquisa serão considerados e mitigados.

## Justificativa

Descreva a importância ou a motivação para trabalhar com o conjunto de dados escolhido. Indique as razões pelas quais você escolheu seus objetivos específicos, as razões para aprofundar o estudo do problema identificado e qual o impacto que tal problema provoca na sociedade. Lembre-se de quantificar (com dados reais e suas respectivas fontes) este impacto.



### Justificativa para o Trabalho com Dados Climáticos e Machine Learning

A compreensão precisa do clima é fundamental para a vida cotidiana, para a agricultura, para a prevenção de desastres naturais e para muitos outros aspectos da sociedade. No entanto, os padrões climáticos estão se tornando cada vez mais voláteis devido às mudanças climáticas, tornando essencial o desenvolvimento de métodos avançados para previsão e compreensão do clima. Portanto, a proposta de utilizar machine learning sobre dados climáticos dos anos anteriores é altamente relevante e motivada por diversas razões.

Importância/Motivação:

A precisão das previsões climáticas é essencial para permitir que as pessoas se preparem adequadamente para condições meteorológicas extremas, como ondas de calor, tempestades ou secas. Além disso, a capacidade de antecipar mudanças climáticas a longo prazo é crucial para o planejamento urbano, agrícola e de infraestrutura.

Razões para Escolher Objetivos Específicos:

Precisão das Previsões: Utilizando técnicas de machine learning sobre dados climáticos históricos, é possível identificar padrões complexos e sutis que podem escapar das abordagens tradicionais de modelagem climática. Isso leva a previsões mais precisas e confiáveis.

Adaptação e Mitigação: Ao compreender os padrões climáticos com maior precisão, as comunidades podem se adaptar melhor às mudanças climáticas e implementar medidas de mitigação mais eficazes.

Alerta de Desastres Naturais: Modelos de machine learning podem ajudar na detecção precoce de eventos climáticos extremos, como furacões e inundações, permitindo a evacuação e o planejamento de resposta a desastres de forma mais eficaz.

Razões para Aprofundar o Estudo do Problema Identificado:

Mudanças Climáticas: As mudanças climáticas estão aumentando a frequência e a intensidade de eventos climáticos extremos em muitas regiões do mundo. Compreender essas mudanças e seus impactos é essencial para a adaptação e mitigação.

Impacto Socioeconômico: Eventos climáticos extremos podem ter um impacto devastador nas economias locais e nacionais, causando danos a propriedades, infraestrutura e recursos naturais. Prever esses eventos com maior precisão pode reduzir o impacto econômico e social.

Saúde Pública: O clima extremo pode afetar a saúde das pessoas, aumentando o risco de doenças relacionadas ao calor, poluição do ar e disseminação de doenças infecciosas. Melhores previsões climáticas podem ajudar na implementação de medidas de saúde pública adequadas.

Impacto na Sociedade:

Redução de Riscos: Previsões climáticas mais precisas permitem que as comunidades se preparem melhor para eventos climáticos extremos, reduzindo assim os riscos para a vida e a propriedade.

Resiliência e Sustentabilidade: Ao compreender melhor os padrões climáticos, as comunidades podem desenvolver estratégias mais resilientes e sustentáveis ​​para lidar com as mudanças climáticas e proteger o meio ambiente.

Melhoria da Qualidade de Vida: A capacidade de se preparar adequadamente para condições climáticas extremas pode melhorar significativamente a qualidade de vida das pessoas, garantindo acesso a recursos essenciais, como água potável e alimentos, mesmo em situações adversas.

Referências:

IPCC - Painel Intergovernamental sobre Mudanças Climáticas
NOAA - National Oceanic and Atmospheric Administration
WMO - World Meteorological Organization
Estudos científicos e relatórios governamentais sobre mudanças climáticas e previsões climáticas.



> **Links Úteis**:
> - [Como montar a justificativa](https://guiadamonografia.com.br/como-montar-justificativa-do-tcc/)

## Público-Alvo

Descreva quem serão as pessoas que poderão se beneficiar com a sua investigação indicando os diferentes perfis. O objetivo aqui não é definir quem serão os clientes ou quais serão os papéis dos usuários na aplicação. A ideia é, dentro do possível, conhecer um pouco mais sobre o perfil dos usuários: conhecimentos prévios, relação com a tecnologia, relações hierárquicas, etc.

Adicione informações sobre o público-alvo por meio de uma descrição textual, diagramas de personas e mapa de stakeholders.

> **Links Úteis**:
> - [Público-alvo](https://blog.hotmart.com/pt-br/publico-alvo/)
> - [Como definir o público alvo](https://exame.com/pme/5-dicas-essenciais-para-definir-o-publico-alvo-do-seu-negocio/)
> - [Público-alvo: o que é, tipos, como definir seu público e exemplos](https://klickpages.com.br/blog/publico-alvo-o-que-e/)
> - [Qual a diferença entre público-alvo e persona?](https://rockcontent.com/blog/diferenca-publico-alvo-e-persona/)

## Estado da arte

Nesta seção, deverão ser descritas outras abordagens identificadas na literatura que foram utilizadas para resolver problemas similares ao problema em questão. Para isso, faça uma pesquisa detalhada e identifique, no mínimo, 3 trabalhos que tenham utilizado dados em contexto similares e então, detalhe: detalhe e contextualize o problema, descreva o _dataset_ utilizado, detalhe quais abordagens/algoritmos foram utilizados (e seus parâmetros), identifique as métricas de avaliação empregadas e fale sobre os resultados obtidos. 

> **Links Úteis**:
> - [Google Scholar](https://scholar.google.com/)
> - [IEEE Xplore](https://ieeexplore.ieee.org/Xplore/home.jsp)
> - [Science Direct](https://www.sciencedirect.com/)
> - [ACM Digital Library](https://dl.acm.org/)

# Descrição do _dataset_ selecionado

Nesta seção, você deverá descrever detalhadamente o _dataset_ selecionado. Lembre-se de informar o link de acesso a ele, bem como, de descrever cada um dos seus atributos (a que se refere, tipo etc.), se existem atributos faltantes etc.

# Canvas analítico

Nesta seção, você deverá estruturar o seu Canvas Analítico. O Canvas Analítico tem o papel de registrar a organização das ideias e apresentar o modelo de negócio.

> **Links Úteis**:
> - [Modelo do Canvas Analítico](https://github.com/ICEI-PUC-Minas-PMV-SI/PesquisaExperimentacao-Template/blob/main/help/Software-Analtics-Canvas-v1.0.pdf)

# Referências

Inclua todas as referências (livros, artigos, sites, etc) utilizados no desenvolvimento do trabalho utilizando o padrão ABNT.

> **Links Úteis**:
> - [Padrão ABNT PUC Minas](https://portal.pucminas.br/biblioteca/index_padrao.php?pagina=5886)
