# Detecção de Anomalias em Transações com Python

## Descrição

Este projeto demonstra como identificar transações financeiras suspeitas utilizando Python.

O objetivo é detectar valores que fogem do comportamento esperado, simulando um processo simples de monitoramento de fraudes.

## Tecnologias

- Python 3
- Pandas

## Como funciona

O algoritmo calcula:

- Média das transações
- Desvio padrão
- Limite superior e inferior

Toda transação que estiver acima ou abaixo desses limites é considerada uma anomalia.

## Exemplo

| ID | Valor |
|----|-------|
|1|120|
|2|135|
|3|118|
|4|125|
|5|950|
|6|130|

Resultado:

A transação de **R$950** será identificada como uma possível anomalia.

## Executando

```bash
pip install pandas

python detectar_anomalias.py
```

## Aprendizados

Este projeto demonstra conceitos de:

- Manipulação de dados
- Estatística básica
- Detecção de outliers
- Automação com Python

## Melhorias futuras

- Utilizar Machine Learning
- Detectar fraudes em tempo real
- Criar dashboard com Streamlit

- import pandas as pd

# Ler arquivo CSV
df = pd.read_csv("transacoes.csv")

media = df["Valor"].mean()
desvio = df["Valor"].std()

limite_superior = media + (2 * desvio)
limite_inferior = media - (2 * desvio)

anomalias = df[
    (df["Valor"] > limite_superior) |
    (df["Valor"] < limite_inferior)
]

print("Média:", round(media,2))
print("Desvio padrão:", round(desvio,2))
print("\nAnomalias encontradas:\n")

print(anomalias)

ID,Valor
1,120
2,125
3,130
4,128
5,122
6,126
7,124
8,950
9,123
10,127
11,121
12,129
13,118
14,132
15,1100
