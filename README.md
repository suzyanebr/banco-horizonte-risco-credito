# Projeto de Análise de Dados - Banco Horizonte

<p align="center">
<img width="1774" height="887" alt="Image" src="https://github.com/user-attachments/assets/cd785c1f-934f-4e3a-8e2e-1186e76842a6" />
</p>

<p align="justify">
Este projeto realiza uma análise de risco de crédito para o Banco Horizonte (instituição fictícia), que enfrenta aumento na inadimplência em produtos como cartão de crédito e empréstimos pessoais.
</p>

<p align="justify">
Para isso, foi utilizado Python para limpeza, tratamento e análise exploratória dos dados, e Power BI para a visualização dos principais indicadores e compreensão geral do comportamento dos clientes.
</p>

## Conjunto de Dados
<p align="justify">
Foi utilizado o dataset público <strong><a href="https://www.kaggle.com/c/GiveMeSomeCredit">Give Me Some Credit</a></strong> (Kaggle), contendo exatamente 150.000 registros de clientes, com variáveis relacionadas ao perfil demográfico e comportamento financeiro, como:
</p>

<ul>
<li>Idade</li>
<li>Renda mensal</li>
<li>Número de dependentes</li>
<li>Utilização do limite de crédito</li>
<li>Histórico de atrasos (30–59, 60–89 e 90+ dias)</li>
</ul>

> **Nota metodológica:** a base não possui variáveis como credit score ou número de parcelas. Por isso, a análise foi conduzida com foco em variáveis comportamentais, como histórico de atrasos e utilização de crédito, que se mostraram mais relevantes para identificação de risco.

## Apresentação

### Dashboard Interativo

O dashboard foi desenvolvido no **Power BI** com o objetivo de apresentar, de forma clara e interativa, os principais indicadores de risco do perfil de clientes.

<div align="center"> <img width="1171" height="642" alt="Image" src=05-Imagem/01-imag-dashboard.png />

🔗 [Acesse o dashboard completo:](https://app.powerbi.com/view?r=eyJrIjoiYjBlYzk1NzAtZDI5OS00ZTBmLTg5NTYtZjZiYzAzMDU2NGI2IiwidCI6ImE2MDk0MDk0LWY1YjEtNDU3Yi1hODE3LTM2ZmNlOTFhYTQ3NSJ9)
</div>

<br>

## Ferramentas Utilizadas

Para a execução desta análise, foram utilizadas as seguintes ferramentas:

- **Python**: utilizado para limpeza, tratamento de valores nulos e análise exploratória dos dados, utilizando as bibliotecas *Pandas*, *Matplotlib* e *Seaborn*. O processo completo está documentado no arquivo `analise_risco_credito.ipynb`.

- **Microsoft Power BI**: utilizado para construção do dashboard estratégico, incluindo criação de colunas, medidas em **DAX** e visualizações para análise de faixa etária, taxa de inadimplência, status de pagamento e outros indicadores de risco.

## Perguntas de Negócio

#### 1. Qual o perfil demográfico do cliente inadimplente?
Clientes inadimplentes são, em média, 7 anos mais jovens (46 anos vs. 53 anos dos adimplentes). A inadimplência cai progressivamente com a idade, de 12% na faixa 18–30 anos até 2% em 70+.

#### 2. O histórico de atrasos passados prevê inadimplência futura?
Sim. Atrasos mais longos concentram a inadimplência. Para atrasos de 90+ dias, há 20.968 ocorrências entre inadimplentes contra 18.928 entre adimplentes.

#### 3. O uso do limite de crédito disponível está associado a maior risco?
Sim, sendo o indicador mais relevante da análise. Clientes inadimplentes utilizam, em mediana, 84% do limite disponível, enquanto clientes adimplentes utilizam apenas 13%.

#### 4. A renda mensal, isoladamente, é um bom preditor de inadimplência?
Não. A diferença de renda mediana entre os grupos é mínima (R$ 5.400 adimplentes vs. R$ 5.240 inadimplentes), indicando que o risco está mais relacionado ao comportamento de uso do crédito do que ao nível de renda.

#### 5. Clientes sem informação de renda têm comportamento de risco diferente?
Sim. Clientes que informaram a renda apresentaram maior taxa de inadimplência (7%) em comparação aos que não informaram (6%).

## Recomendações de Negócio

<p align="justify">
<strong>1. Segmentação por faixa etária no crédito</strong><br>
Insight: clientes entre 18–30 anos apresentam inadimplência significativamente maior (12% vs. 2% em 70+).<br>
Recomendação: aplicar políticas de crédito mais conservadoras para clientes até 30 anos, com limites iniciais mais baixos, maior rigor na aprovação e monitoramento mais próximo nos primeiros meses.
</p>

<p align="justify">
<strong>2. Monitoramento do uso do limite de crédito</strong><br>
Insight: clientes inadimplentes utilizam, em média, 84% do limite disponível, contra 13% dos adimplentes.<br>
Recomendação: implementar monitoramento proativo com alertas automáticos para utilização acima de 60–70%, permitindo ações preventivas como revisão de limite e contato antecipado.
</p>

<p align="justify">
<strong>3. Gestão de clientes com histórico de atraso</strong><br>
Insight: atrasos longos (especialmente acima de 90 dias) concentram o maior volume de inadimplentes.<br>
Recomendação: criar réguas de acompanhamento diferenciadas, com segmentação por histórico de atraso, contato antecipado e estratégias de renegociação preventiva.
</p>

<p align="justify">
<strong>4. Renda como variável secundária de risco</strong><br>
Insight: a renda média entre adimplentes e inadimplentes é semelhante (R$ 5.400 vs. R$ 5.240).<br>
Recomendação: reduzir o peso da renda nos modelos de crédito e priorizar variáveis comportamentais, como histórico de pagamento e uso do limite.
</p>

<p align="justify">
<strong>5. Revisão da exigência de comprovação de renda</strong><br>
Insight: clientes que informaram renda apresentaram maior taxa de inadimplência (7% vs. 6%).<br>
Recomendação: reavaliar políticas que penalizam a ausência de informação de renda e testar flexibilizações em ambiente controlado. Como o dado histórico é observacional, a validação deve ser feita por meio de um teste controlado, comparando a política atual com uma abordagem alternativa que não penalize esse grupo.
</p>
