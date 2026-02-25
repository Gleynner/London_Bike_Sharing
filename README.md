# 🚲 London Bike Sharing — Análise Exploratória e Previsão de Demanda

<p align="center">
  <img src="assets/London_Bike_Sharing_Image.png" width="670"/>
</p>

## 📌 Visão Geral

Este projeto aplica técnicas de Análise Exploratória de Dados (EDA) e modelagem de séries temporais para compreender e prever a demanda por bicicletas compartilhadas na cidade de Londres. O conjunto de dados é disponibilizado pela plataforma Kaggle e contém registros horários de utilização integrados a variáveis temporais e climáticas. 

O projeto simula um problema real de previsão de demanda, comum em cenários de mobilidade urbana e planejamento operacional.

<br>

## 📊 Sobre o Conjunto de Dados

Cada observação representa um intervalo de uma hora e inclui, entre outras variáveis:

- Quantidade de bicicletas alugadas no período

- Data e hora do registro

- Condições climáticas (temperatura, umidade, velocidade do vento e tipo de clima)

- Indicadores de sazonalidade (estação do ano)

- Flags de fim de semana e feriado

Essa combinação de atributos torna o dataset especialmente adequado para análises temporais, identificação de padrões sazonais e modelagem preditiva baseada em variáveis exógenas

<br>

## 🎯 Objetivo

- Analisar o comportamento temporal da demanda por bicicletas

- Identificar padrões de tendência e sazonalidade

- Desenvolver e avaliar um modelo de séries temporais com Prophet para previsão da demanda futura

<br>

## 📊 Análise Exploratória de Dados

A Análise Exploratória de Dados foi conduzida com o objetivo de compreender o comportamento temporal da demanda por bicicletas e identificar padrões estruturais relevantes para a modelagem preditiva. A análise evidenciou a presença de múltiplas sazonalidades, com ciclos bem definidos nos níveis diário, semanal e anual, além de diferenças consistentes no volume de aluguéis entre dias úteis, fins de semana e estações do ano.

A investigação da distribuição da variável alvo revelou a ocorrência de períodos de alta concentração de demanda, associados a picos sazonais e eventos específicos, resultando em uma distribuição assimétrica e na presença de observações extremas. Testes formais de normalidade, como o teste de Shapiro–Wilk, aplicados a subconjuntos dos dados por estação do ano, rejeitaram a hipótese de normalidade. Diante desse contexto, análises comparativas entre estações foram conduzidas por meio de métodos não paramétricos, permitindo avaliar diferenças no comportamento da demanda sem a imposição de pressupostos paramétricos.

As visualizações temporais e as estatísticas descritivas forneceram suporte direto às decisões metodológicas adotadas na etapa de modelagem, assegurando alinhamento entre as características observadas nos dados e as técnicas empregadas na previsão da série temporal.



<br>

## 🤖 Modelagem com Prophet

Foi utilizado o modelo Prophet, adequado para séries temporais com múltiplas sazonalidades e necessidade de interpretabilidade. O processo incluiu ajuste de hiperparâmetros e validação temporal. O modelo final capturou de forma consistente a tendência e os ciclos sazonais observados na série histórica, apresentando bom desempenho preditivo.


<br>

## 📈 Insights Executivos

- A demanda por bicicletas é altamente previsível devido a padrões sazonais recorrentes

- Componentes temporais exercem papel central na explicação do volume de uso

- O Prophet mostrou-se adequado para previsão de demanda em contextos de mobilidade urbana

<br>

## 🛠️ Tecnologias Utilizadas

- Python

- Pandas, NumPy

- Matplotlib, Seaborn

- SciPy, Scikit-learn

- Prophet

<br>

## ✅ Por que este projeto é relevante?

Este projeto demonstra a aplicação prática de EDA, estatística e modelagem de séries temporais, com decisões metodológicas justificadas e foco em um problema real de previsão de demanda.

<br>

> [Veja o notebook para detalhes da análise.](https://github.com/Gleynner/London_Bike_Sharing/blob/main/bike_demand_forecasting_prophet.ipynb)

