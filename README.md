# Análise Exploratória de Dados (EDA) – Alura Challenge | Parte 1

Este repositório contém a primeira etapa do **Alura Challenge** focada na **Análise Exploratória de Dados (EDA)**. Nele, exploramos um conjunto de dados para compreender padrões, relacionamentos e possíveis insights que servirão de base para as próximas fases do projeto.

---

## Contexto do Desafio

O **Alura Challenge** é um projeto proposto pela plataforma [Alura](https://www.alura.com.br/challenges) que busca estimular o aprendizado prático de diversas áreas de tecnologia. Nesta etapa, o desafio é realizar a Análise Exploratória de um conjunto de dados disponibilizado para:

- Entender a estrutura do dataset  
- Limpar, tratar e transformar os dados conforme necessário  
- Explorar visualizações e estatísticas descritivas para identificar padrões interessantes  

Por meio dessa análise inicial, é possível formular hipóteses e levantar insights que orientarão as próximas etapas do projeto, como modelagem e criação de soluções.

---

## Objetivos

1. **Familiarizar-se com o conjunto de dados**: Verificar as colunas, tipos de variáveis e possíveis inconsistências.  
2. **Identificar outliers e valores ausentes**: Entender como tratar dados faltantes, inconsistentes ou fora do padrão.  
3. **Explorar relações entre variáveis**: Fazer correlações, cruzamentos e verificar variáveis mais significativas para análises futuras.  
4. **Obter insights**: Levantar hipóteses que possam ser testadas na etapa de modelagem.

---

## Visão Geral do Projeto

Nesta primeira parte, foi realizada a **Análise Exploratória (EDA)** para:

- Verificar a qualidade dos dados (limpeza e tratamento de dados faltantes ou inválidos).  
- Entender as distribuições estatísticas de variáveis numéricas e categóricas.  
- Criar visualizações (histogramas, scatter plots, gráficos de barras, box plots etc.) que ajudam a descrever o comportamento dos dados.  
- Destacar pontos de atenção que podem impactar as análises posteriores (como outliers e colunas sem relevância).

---

## Principais Análises Realizadas

- **Análise Descritiva Inicial**  
  Estatísticas básicas (média, mediana, moda, quartis, desvio padrão) que ajudam a entender a distribuição das variáveis.

- **Visualização Inicial de Distribuições**  
  Criação de histogramas e gráficos de densidade para avaliar comportamentos e possível presença de distribuições assimétricas.
  
- **Tratamento de Dados Faltantes**  
  Verificação da proporção de valores nulos em cada coluna e aplicação de métodos de imputação ou exclusão de linhas/colunas.

- **Visualização de Distribuições Detalhada**  
  Criação de histogramas e gráficos de densidade com a distribuição em torno da variável target para avaliar comportamentos e possível presença de distribuições assimétricas.

- **Correlação entre Variáveis**  
  Geração de uma matriz de correlação e visualização usando heatmaps para verificar relações lineares.
  
---

# Resumo Desta Etapa

1. Extraímos os Dados com API utilizando requests
2. Criamos o DataFrame
3. Exploramos os dados e identificamos tamanho, variáveis, tipos de dados, valores faltantes.
4. Corrigimos os valores faltantes e removemos, ajustamos os nomes das colunas, fizemos uma investigação inicial da distribuição dos dados.
5. Investigamos melhor a distribuição dos dados e procuramos padrões entre as distribuições da variável target com as variáveis independentes.
6. Levantamos hipóteses das análises.
7. Traduzimos os nomes das colunas automaticamente utilizando API da OpenAI (para aprendizado).
8. Criamos a coluna de Cobranças Diária (desafio extra).
9. Separamos o DF em variáveis numéricas e categóricas.
10. Fizemos Encoding das variáveis categóricas utilizando Label Encoder.
11. Unimos as variáveis numéricas com as categóricas após a codificação.
12. Puxamos as informações estatísticas e gerais do data frame para relembrar.
13. Fizemos um Heatmap de correlação entre as variáveis.

---

# Conclusões das Análises dos Gráficos de Distribuição

## Distribuições Desiguais:

- Temos um número muito mais alto de contagens para Não Churn que Sim Churn
- Senioridade está desigual, poucos clientes idosos.
- Dependentes está desigual
- Acúmulo de Tempo de contrato nos valores mais baixos
- PhoneService
- Online Security
- Online Backup
- Device Protection
- TechSupport
- StreamingTV
- StreamingMovies
- Acúmulo de ChargesMonthly e Total nas faixas menores, o que faz sentido pro ChargesTotal já que temos um número de clientes com poucos meses de contrato. Mas ChargesMonthly indica que temos um grande número de clientes com ticket baixo.

## Distribuições Iguais:
- A distribuiçõa de Gênero está equivalente.
- Parceiros está igual.
- Linhas Múltiplas
- InternetService
- Contract
- Paperless Billing
- Payment Method

## Hipóteses Levantadas

- Entre homens e mulheres não vemos um padrão maior de churn por gênero.
- Entre os idosos, vemos uma taxa de cancelamento muito alta.
- Clientes que não possuem parceiros tendem a cancelar em torno de 2x mais.
- Existem mais clientes sem dependentes, porém os clientes com dependentes possuem uma taxa de cancelamento significativamente menor.
- A contagem alta de Churns em clientes com poucos meses de contrato demonstra uma taxa de cancelamento alta para os primeiros meses de contratação.
- Existe um número muito superior de clientes com contratação de serviços telefônicos, porém a taxa de churn aparenta estar proporcionalmente igual.
- Temos mais clientes SEM múltiplas linhas, mas a taxa de churn para os que tem é significativamente maior.
- A taxa de cancelamento para clientes com serviço de internet por fibra ótica extremamente alta, beirando os 50%. O que indica possível problema com o tipo de serviço.
- Temos mais clientes sem segurança online e com maior taxa de cancelamento do que aqueles que TEM segurança online.
- Mais clientes sem backup online, com uma taxa de cancelamento ligeiramente menor para aqueles que possuem backup online.
- O mesmo acontece para os clientes que possuem proteção de dispositivos.
- Clientes com suporte técnico tem uma taxa de churn 2x menor.
- Clientes sem StreamingTV possuem taxa de cancelamento menor, indicando possível problema com o tipo de serviço.
- O mesmo acontece para clientes sem StreamingMovies.
- Clientes com contrato mês a mês tem um Churn muito alto, em torno de 40%.
- Clientes com faturamento sem papel cancelam muito mais.
- Clientes que pagam com cheque eletrônico cancelam em torno de 40%.
- Não parece haver um padrão de churn em relação ao preço mensal.
- Distribuições desiguais podem fazer ser necessário utilizar uma reamostragem dos dados para evitar enviesamento do modelo. Utilizar outras métricas além de Acurácia, como F1-score, Recall e ROC-AUC.
