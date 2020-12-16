# Análise de Dados
##  com Pandas e Numpy.

### 1º passo: instalar as bibliotecas:

import numpy as np.

import pandas as pd.

### 2º passo: carregar seu dataset para análise utilizando o pandas.
df = pd.read_csv("https://pycourse.s3.amazonaws.com/bike-sharing.csv").

## Tudo pronto parar iniciar sua análise.
### A lista de códigos a seguir foi utilizada no módulo Analista de Machine Learning no Bootcamp Programador Python da IGTI.

### a) Como calcular o tamanho do dataset?

df.info()

### b) Qual a média da coluna windspeed?

df.windspeed.mean()

### c) Qual a média da coluna temp?

df.temp.mean()

### d) Quantos registros existem para o ano de 2011?

df[df.year==0].shape

### e) Quantos registros existem para o ano de 2012?

df[df.year==1].shape

### f) Quantas locações de bicicletas foram efetuadas em 2011?

df[df.year==0].total_count.sum()

### g) Quantas locações de bicicletas foram efetuadas em 2012?

df[df.year==1].total_count.sum()

### h) Qual estação do ano contém a maior média de locações de bicicletas?

df.groupby(['season']).total_count.mean()

### i) Qual estação do ano contém a menor média de locações de bicicletas?

---> Aqui utilizamos o mesmo código, o que deve mudar é a análise:

df.groupby(['season']).total_count.mean()

### j) Qual horário do dia contém a maior média de locações de bicicletas?

df.groupby(['hour']).total_count.mean().sort_values(ascending=False)

### k) Qual horário do dia contém a menor média de locações de bicicletas?

---> Aqui utilizamos o mesmo código, o que deve mudar é a análise:

df.groupby(['hour']).total_count.mean().sort_values(ascending=False)

### l) Que dia da semana contém a maior média de locações de bicicletas?

df.groupby(['weekday']).total_count.mean().sort_values(ascending=False)

### m) Que dia da semana contém a menor média de locações de bicicletas?

---> Aqui utilizamos o mesmo código, o que deve mudar é a análise:

df.groupby(['weekday']).total_count.mean().sort_values(ascending=False)


### n) Às quartas-feiras (weekday = 3), qual o horário do dia contém a maior médiade locações de bicicletas?

df[df.weekday==3].groupby(['hour']).total_count.mean().sort_values(ascending=False)

### o) Aos sábados (weekday = 6), qual o horário do dia contém a maior média de locações de bicicletas?

df[df.weekday==6].groupby(['hour']).total_count.mean().sort_values(ascending=False)


## Agora é só codar!
