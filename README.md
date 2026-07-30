# Projeto de Análise de Dados - Banco Horizonte

<p align="center">
<img width="1774" height="887" alt="Image" src="https://github.com/user-attachments/assets/cd785c1f-934f-4e3a-8e2e-1186e76842a6" />
</p>

Este projeto realiza uma análise de risco de crédito para o Banco Horizonte (instituição fictícia), que enfrenta aumento na inadimplência em produtos como cartão de crédito e empréstimos pessoais.

Para isso, foram utilizadas ferramentas de análise de dados e visualização: Python para limpeza, tratamento e análise exploratória dos dados, e Power BI para a construção de um dashboard estratégico com os principais indicadores de risco.

## Conjunto de Dados


Foi utilizado o dataset público **["Give Me Some Credit"](https://www.kaggle.com/c/GiveMeSomeCredit)** (Kaggle), contém aproximadamente 150.000 registros de clientes, com variáveis relacionadas ao perfil demográfico e comportamento financeiro, como:
Idade 
Renda mensal
Número de dependentes
Utilização do limite de crédito
Histórico de atrasos (30–59, 60–89 e 90+ dias)

> **Nota metodológica:** a base não possui variáveis como credit score ou número de parcelas. Por isso, a análise foi conduzida com foco em variáveis comportamentais, como histórico de atrasos e utilização de crédito, que se mostraram mais relevantes para identificação de risco.

## Apresentação

A análise é apresentada em duas frentes:

### Dashboard Interativo

No dashboard encontram-se as principais métricas e indicadores que permitem uma compreensão rápida do perfil de risco da carteira de clientes.

<p align="center">
  <img src="COLE_AQUI_O_LINK_DO_PRINT_DO_SEU_DASHBOARD" alt="Dashboard Banco Horizonte">
</p>

### [Confira aqui o dashboard do projeto.](COLE_AQUI_O_LINK_DO_POWER_BI_PUBLICADO)

### Notebook em Python

O notebook (`Banco.ipynb`) contém todo o processo de limpeza dos dados, tratamento de valores nulos e a análise exploratória que fundamenta os achados do dashboard.

## Ferramentas

Para a execução dessa análise, foram utilizadas as seguintes ferramentas:
- **Python**: limpeza, tratamento de valores nulos e análise exploratória, utilizando as bibliotecas *Pandas*, *Matplotlib* e *Seaborn*. O passo a passo está demonstrado no arquivo `Banco.ipynb`.
- **Microsoft Power BI**: construção do dashboard, com criação de colunas e medidas em **DAX** para as visualizações (faixa etária, taxa de inadimplência, status de pagamento, entre outras).

## Perguntas de Negócio

#### 1. Qual o perfil demográfico (idade, dependentes) do cliente inadimplente?
Clientes inadimplentes são, em média, mais jovens (45,9 anos vs. 52,8 anos dos adimplentes). A inadimplência cai progressivamente com a idade, de 11,7% na faixa 18-30 anos até 2,3% em 70+.

#### 2. O histórico de atrasos passados prevê inadimplência futura?
Sim. Inadimplentes apresentam de 8,5x a 15x mais ocorrências de atraso, em todos os prazos analisados (30-59, 60-89 e 90+ dias), em relação aos adimplentes.

#### 3. O uso do limite de crédito disponível está associado a maior risco?
Sim, e é o indicador mais forte da base: inadimplentes utilizam, em mediana, **84%** do limite disponível, contra apenas **13%** dos adimplentes.

#### 4. A renda mensal, isoladamente, é um bom preditor de inadimplência?
Não. A diferença de renda mediana entre os grupos é pequena (R$ 5.400 vs. R$ 5.240), indicando que o risco está mais ligado ao comportamento de uso do crédito do que ao nível de renda em si.

#### 5. Clientes sem informação de renda têm comportamento de risco diferente?
Sim, mas de forma contraintuitiva: quem não informou a renda apresentou taxa de inadimplência **menor** (5,6%) do que quem informou (6,9%) — resultado que contraria a hipótese inicial de que omitir a renda seria um sinal de risco.

## Recomendações de Negócio

#### 🔴 1. Segmentação por faixa etária no crédito
**Insight:** clientes entre 18–30 anos apresentam inadimplência significativamente maior (11,7% vs 2,3% em 70+).
**Recomendação:** aplicar políticas de crédito mais conservadoras para clientes até 30 anos — limites iniciais mais baixos, maior rigor na aprovação e monitoramento mais próximo nos primeiros meses.

#### 🔴 2. Monitoramento do uso do limite de crédito
**Insight:** clientes inadimplentes utilizam, em média, 84% do limite, contra 13% dos adimplentes.
**Recomendação:** implementar monitoramento proativo, com alertas automáticos acima de 60–70% de uso, acionamento preventivo do time de relacionamento e revisão dinâmica de limites.

#### 🔴 3. Gestão de clientes com histórico de atraso
**Insight:** mesmo atrasos leves (30–59 dias) já indicam maior probabilidade de reincidência.
**Recomendação:** criar réguas de acompanhamento diferenciadas, com segmentação automática por histórico, contato antecipado antes de novos atrasos e estratégias de renegociação preventiva.

#### 🟡 4. Renda como variável secundária de risco
**Insight:** a renda média entre adimplentes e inadimplentes é similar (R$ 5.400 vs R$ 5.240).
**Recomendação:** reduzir o peso da renda no modelo de crédito e priorizar variáveis comportamentais, histórico de pagamento e uso de crédito.

#### 🟡 5. Revisão da exigência de comprovação de renda
**Insight:** clientes que não informaram renda apresentaram inadimplência menor (5,6% vs 6,9%).
**Recomendação:** reavaliar políticas atuais que penalizam quem não declara renda, testar flexibilização em ambientes controlados (A/B test) e validar se há viés no processo atual.

## Autora

Suzy Ane Brito de Oliveira — [LinkedIn](COLE_AQUI_O_LINK_DO_SEU_LINKEDIN) | [GitHub](https://github.com/suzyanebr)
