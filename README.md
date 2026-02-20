# 🚲 London Bike Sharing — Análise Exploratória e Previsão de Demanda

## 📌 Visão Geral

Este projeto aplica técnicas de Análise Exploratória de Dados (EDA) e modelagem de séries temporais para compreender e prever a demanda por bicicletas compartilhadas na cidade de Londres. O conjunto de dados é disponibilizado pela plataforma Kaggle e contém registros horários de utilização integrados a variáveis temporais e climáticas. 

O projeto simula um problema real de previsão de demanda, comum em cenários de mobilidade urbana e planejamento operacional.

<br>

## 🎯 Objetivo

- Analisar o comportamento temporal da demanda por bicicletas

- Identificar padrões de tendência e sazonalidade

- Desenvolver e avaliar um modelo de séries temporais com Prophet para previsão da demanda futura

<br>

## 📊 Análise Exploratória de Dados

\*
A EDA evidenciou que a demanda apresenta forte sazonalidade diária, semanal e anual, além de clara dependência do calendário. A variável de contagem mostrou assimetria positiva, com rejeição da hipótese de normalidade por meio do teste de Shapiro–Wilk, orientando a escolha de abordagens estatísticas e modelos compatíveis com esse comportamento.
*/

A Análise Exploratória de Dados foi conduzida com foco na compreensão do comportamento temporal da demanda e na identificação de padrões estruturais relevantes para a modelagem preditiva. A análise revelou a presença de múltiplas sazonalidades, com ciclos bem definidos em níveis diário, semanal e anual, além de diferenças significativas no volume de aluguéis entre dias úteis, fins de semana e estações do ano.     
  
A avaliação da distribuição da variável alvo (contagem de aluguéis) indicou assimetria positiva, caracterizada por picos de demanda em determinados períodos. Testes formais de normalidade, como o Shapiro–Wilk, foi utilizado em dados referentes a contagem em estações específicas do ano e, rejeitaram a hipótese de normalidade. Adicionalmente, análises comparativas entre estações do ano foram realizadas com métodos não paramétricos, permitindo avaliar diferenças no comportamento da demanda sem assumir normalidade das amostras.     

As visualizações temporais e estatísticas descritivas forneceram suporte às decisões metodológicas adotadas na etapa de modelagem, garantindo coerência entre as características observadas nos dados e as técnicas empregadas.



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

- Matplotlib, Seaborn e Plotly

- SciPy e sklearn

- Prophet

<br>

## ✅ Por que este projeto é relevante?

Este projeto demonstra a aplicação prática de EDA, estatística e modelagem de séries temporais, com decisões metodológicas justificadas e foco em um problema real de previsão de demanda.

<br>

> Veja o notebook para detalhes da análise.

