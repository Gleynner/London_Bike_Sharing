# 🚲 Análise Exploratória e Previsão de Demanda — London Bike Sharing  

<p align="center">
  <code>Python</code> <code>Prophet</code> <code>Séries Temporais</code> <code>Testes de Hipótese</code> <code>EDA</code>
</p>

<p align="center">
  <img src="assets/London_Bike_Sharing_Image.png" width="670"/>
</p>

 
## 📌 Visão Geral
 
Projeto de Ciência de Dados para compreender e prever a demanda por bicicletas compartilhadas em Londres, combinando testes estatísticos não paramétricos, tratamento de outliers orientado por evidência e validação cruzada temporal para calibrar um modelo de séries temporais com o Prophet. O trabalho simula um problema real de previsão de demanda, comum em cenários de mobilidade urbana e planejamento operacional.
 
## 🎯 Objetivo
 
Analisar o comportamento temporal da demanda por bicicletas, identificar padrões de tendência e sazonalidade, e desenvolver um modelo preditivo capaz de estimar a demanda futura com boa capacidade de generalização.
 
## 📊 Sobre os Dados
 
Dataset do Kaggle com registros horários de aluguel de bicicletas em Londres (jan/2015 a jan/2017), incluindo contagem de aluguéis, variáveis climáticas (temperatura, sensação térmica, umidade, velocidade do vento, tipo de clima) e indicadores de sazonalidade (estação do ano, fim de semana, feriado).
 
## 📈 Resultados Principais
 
| Etapa do Modelo | RMSE Relativo | Classificação |
|---|:---:|---|
| Modelo inicial (com outliers) | 18,12% | Boa capacidade preditiva |
| **Modelo final** (outliers tratados + tuning via cross-validation) | **17,53%** | **Boa capacidade preditiva** |
 
A remoção de observações discrepantes e o ajuste de hiperparâmetros via validação cruzada temporal (grid search) reduziram o erro absoluto em 476,06 unidades. Os melhores hiperparâmetros encontrados foram `changepoint_prior_scale = 0.01`, `seasonality_prior_scale = 10.0` e `yearly_seasonality = True`.
 
## 🔎 Principais Insights
 
- **Sazonalidade forte e multi-nível**: a demanda segue ciclos diários (picos no início da manhã e fim da tarde/início da noite — horários de deslocamento casa-trabalho), semanais (queda nos fins de semana) e anuais (verão no pico, inverno na baixa).
- **Fatores climáticos têm poder explicativo moderado**: `umidade` é a variável com maior associação à demanda (r² = 21,16%), seguida por `temperatura` (15,21%) e `sensação térmica` (13,69%); `velocidade do vento` tem impacto quase nulo (r² = 1,44%).
- **Diferença estatisticamente significativa entre estações**: como os dados de contagem por estação não seguem distribuição normal (confirmado pelo teste de Shapiro–Wilk), foi aplicado o teste não paramétrico de Mann–Whitney U, que confirmou diferença estatisticamente significativa entre primavera e outono (p = 0,00048 < 0,05), apesar de ambas apresentarem medianas visualmente próximas.
- **Anomalia identificada e validada externamente**: um pico de demanda fora do padrão entre julho e outubro de 2015 foi investigado e associado a uma greve do metrô de Londres — achado confirmado com fontes jornalísticas da época (BBC e The Independent), que registraram a recomendação da Transport for London para uso de bicicletas como alternativa.
## 🤖 Modelagem com Prophet
 
O Prophet foi escolhido por sua adequação a séries com múltiplas sazonalidades e por oferecer boa interpretabilidade dos componentes de tendência e sazonalidade. O processo de modelagem seguiu as seguintes etapas:
 
1. **Modelo inicial**, com sazonalidade anual ativada, treinado nos dados completos (RMSE relativo de 18,12%).
2. **Tratamento de outliers**, com base nos intervalos de confiança gerados pelo próprio Prophet, reduzindo o conjunto a 682 observações.
3. **Validação cruzada temporal** (janelas deslizantes) com busca em grade sobre `changepoint_prior_scale` e `seasonality_prior_scale`, para encontrar a configuração com melhor generalização fora da amostra.
4. **Modelo final**, treinado com os melhores hiperparâmetros, resultando em RMSE relativo de 17,53% e maior aderência aos dados observados.
## 🛠️ Etapas do Projeto
 
1. **Análise Exploratória de Dados** — tratamento de nulos e duplicados, estatísticas descritivas, análise de distribuições e correlações.
2. **Testes de Hipótese** — Shapiro–Wilk (normalidade) e Mann–Whitney U (comparação entre estações do ano).
3. **Engenharia de Atributos Temporais** — extração de ano, mês, hora e dia da semana para análise de padrões.
4. **Preparação para o Prophet** — agregação diária e formatação no padrão exigido pela biblioteca (`ds`, `y`).
5. **Modelagem e Avaliação** — treino/teste, cálculo de RMSE e RMSE relativo.
6. **Tratamento de Outliers** — remoção de valores atípicos com base nos intervalos de confiança do modelo.
7. **Tuning de Hiperparâmetros** — validação cruzada temporal com grid search.
> 📓 [Veja o notebook completo para todos os detalhes técnicos](https://github.com/Gleynner/Analise_demanda_bike_sharing/blob/main/bike_demand_forecasting_prophet.ipynb)
 
## 📊 Tecnologias
 
`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `SciPy` · `Scikit-learn` · `Prophet`
 
## 🚀 Próximos Passos
 
- Comparar o desempenho do Prophet com outras abordagens de séries temporais (ex.: SARIMA, LSTM) como benchmark adicional.
- Incorporar variáveis exógenas de forma mais explícita ao modelo (ex.: clima como regressor, não apenas na EDA).
- Testar a granularidade horária diretamente no modelo, em vez da agregação diária, para cenários operacionais de curtíssimo prazo.
## 💡 Principal Aprendizado
 
Mais do que ajustar um modelo, o projeto reforçou a importância de uma EDA estatisticamente rigorosa como base para decisões de modelagem — da escolha de testes não paramétricos diante da violação de normalidade até a investigação e validação externa de uma anomalia nos dados, em vez de simplesmente descartá-la como ruído.
