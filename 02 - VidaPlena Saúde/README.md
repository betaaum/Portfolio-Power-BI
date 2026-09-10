<p align="center">
  <img src="Imagens/Logotipo-VidaPlena-Saude.jpg" width="300">
</p>

# 🏥 VidaPlena Saúde — Dashboard de Operações Hospitalares

> Projeto de Business Intelligence desenvolvido em Power BI para análise da eficiência operacional de uma rede hospitalar privada fictícia.

---

## 🎯 Objetivo

Desenvolver um dashboard para apoiar a diretoria de operações na análise de:

- Volume de atendimentos;
- Tempo médio de espera;
- Taxa de cancelamentos;
- Satisfação dos pacientes;
- Desempenho de hospitais, médicos e especialidades;
- Gargalos operacionais;
- Evolução dos indicadores ao longo do tempo.

---

## 🏢 Contexto

A **VidaPlena Saúde** é uma rede hospitalar privada fictícia, composta por hospitais, médicos, especialidades, convênios e pacientes, atuando nas regiões Sul, Sudeste, Centro-Oeste e Nordeste.

O projeto foi desenvolvido com foco em **eficiência operacional**, buscando apoiar decisões relacionadas à identificação de gargalos, comparação entre unidades e acompanhamento da evolução da rede.

Os dados utilizados são **simulados** e foram desenvolvidos exclusivamente para fins de estudo e demonstração de conhecimentos em Business Intelligence.

---

## ❓ Perguntas de negócio

- Qual hospital apresenta melhor desempenho operacional?
- Quais hospitais necessitam de maior atenção?
- Quais especialidades possuem maior demanda?
- Como a demanda evolui ao longo dos meses?
- O tempo médio de espera está aumentando ou diminuindo?
- Quais hospitais possuem maiores tempos de espera?
- Existe relação entre demanda e tempo de espera?
- Como cada hospital performa em relação ao ano anterior?
- Como ocorre a variação em relação ao mês anterior?
- Quais são os principais gargalos operacionais?

---

## 📊 Dashboard

### Visão Executiva

Visão consolidada da operação da rede, com foco em volume de atendimentos, tempo médio de espera, cancelamentos, satisfação e comparação entre hospitais.

![Visão Executiva](Imagens/01%20-%20Visao%20Executiva.jpg)

### Análise Operacional

Análise dos principais gargalos operacionais, com rankings de médicos e especialidades, cancelamentos por hospital e tempos de espera por especialidade.

![Análise Operacional](Imagens/02%20-%20Analise%20Operacional.jpg)

### Evolução Temporal

Análise da evolução dos atendimentos, satisfação e tempo médio de espera, incluindo comparações YoY, MoM, YTD e variação absoluta.

![Evolução Temporal](Imagens/03%20-%20Evolucao%20Temporal.jpg)

---

## 📈 Principais KPIs

| KPI | Objetivo |
|---|---|
| Atendimentos | Acompanhar o volume de atendimentos |
| Tempo Médio de Espera | Monitorar o tempo médio até o atendimento |
| % Cancelamentos | Acompanhar a taxa de cancelamentos |
| Satisfação Média | Monitorar a avaliação dos pacientes |
| Tempo Médio de Atendimento | Avaliar a duração média dos atendimentos |
| Permanência Média | Avaliar a permanência média nas internações |
| Tempo Máximo de Espera | Identificar situações críticas de espera |
| Crescimento Anual (YoY) | Comparar o desempenho com o ano anterior |
| Crescimento Mensal (MoM) | Acompanhar a variação mensal |
| Atendimentos Acumulado no Ano (YTD) | Acompanhar o acumulado no ano |
| Variação Absoluta | Medir a diferença absoluta entre períodos |

---

## 🧠 Modelo de dados

O projeto utiliza **modelagem dimensional com modelo estrela**, tendo `F_Atendimentos` como tabela fato e dimensões para calendário, hospitais, médicos, especialidades, convênios e pacientes.

![Modelo de Dados](Imagens/Modelo%281%29.jpg)

---

## 🧮 Exemplos de DAX

### Atendimentos

```DAX
Atendimentos =
COUNTROWS(F_Atendimentos)
```

### Tempo Médio de Espera

```DAX
'Tempo Médio de Espera' =
AVERAGE(F_Atendimentos[TempoEsperaMin])
```

### Percentual de Cancelamentos

```DAX
'% Cancelamentos' =
DIVIDE(
    CALCULATE(
        [Atendimentos],
        F_Atendimentos[Status] = "Cancelado"
    ),
    [Atendimentos],
    0
)
```

### Crescimento Anual (YoY)

```DAX
'% Crescimento Anual (YoY)' =
DIVIDE(
    [Variação Absoluta],
    [Atendimentos Ano Anterior],
    0
)
```

---

## 🛠️ Tecnologias e técnicas

- Power BI
- Power Query
- DAX
- Modelagem dimensional
- Modelo estrela
- Excel
- KPIs e indicadores
- Inteligência de tempo
- Visualização de dados
- Storytelling
- UX de dashboards
- Análise orientada ao negócio

---

## 📌 Resultado

O projeto permitiu aplicar conceitos de **Business Intelligence orientados ao negócio**, desde a definição do problema e das perguntas de negócio até a modelagem dos dados, criação de medidas, indicadores, visualizações e análises temporais.

O principal objetivo foi evoluir da construção de dashboards para uma abordagem de **pensamento analítico e tomada de decisão baseada em dados**.

---

> **Projeto fictício:** a VidaPlena Saúde e todos os dados apresentados neste projeto são simulados e foram desenvolvidos exclusivamente para fins de estudo e demonstração de conhecimentos em Business Intelligence.
