# Brazilian Energy Matrix — Data Science & Machine Learning

> Academic analysis · Public ONS data, Python, Pandas and scikit-learn.

## Visão Geral do Projeto

Este projeto oferece uma análise aprofundada da capacidade de geração de energia no Brasil, utilizando um conjunto de dados públicos do Operador Nacional do Sistema Elétrico (ONS). Através de técnicas de análise de dados e Machine Learning com Python, o projeto explora a evolução da matriz energética, identifica padrões geográficos e aplica modelos preditivos para classificar usinas e prever o crescimento de fontes renováveis.

O objetivo principal é transformar dados brutos em insights estratégicos sobre o setor elétrico brasileiro, demonstrando como a ciência de dados pode ser aplicada para entender e prever tendências em um setor de grande relevância econômica e ambiental.

---

## Como o Projeto Funciona

O projeto é desenvolvido em um Jupyter Notebook e está dividido em cinco análises sequenciais. Cada etapa utiliza bibliotecas de Python como **Pandas** para manipulação de dados, **Matplotlib** e **Seaborn** para visualização, e **Scikit-learn** para a aplicação de modelos de Machine Learning.

### 1. **Exploração da Matriz Energética (Exercício 1)**
- **O que faz:** Analisa a evolução temporal da capacidade instalada (em MW) para cada tipo de fonte de energia (Hidrelétrica, Eólica, Solar, etc.).
- **Como funciona:**
    1.  Os dados são carregados e a coluna de data de operação é convertida para o formato de data.
    2.  O código agrupa os dados por ano e tipo de usina, somando a potência instalada anualmente.
    3.  Calcula-se a soma acumulada para mostrar o crescimento contínuo de cada fonte.
    4.  Um gráfico de linhas é gerado para visualizar essa evolução ao longo do tempo.
- **Resultado:** Identifica qual fonte de energia apresentou o maior crescimento em capacidade nos últimos 10 anos.

### 2. **Análise Geográfica da Geração (Exercício 2)**
- **O que faz:** Mapeia a distribuição da capacidade de geração de energia pelos estados brasileiros, correlacionando a localização com o tipo de fonte predominante.
- **Como funciona:**
    1.  Os dados são agrupados por estado e tipo de usina.
    2.  A potência total de cada fonte é calculada para cada estado.
    3.  Um gráfico de barras empilhadas é criado para comparar visualmente a matriz energética de cada estado.
- **Resultado:** Identifica os estados que são líderes na geração de energias solar e eólica.

### 3. **Previsão de Crescimento da Energia Solar (Exercício 3)**
- **O que faz:** Aplica um modelo de regressão linear para prever a capacidade instalada de energia solar para os próximos cinco anos.
- **Como funciona:**
    1.  O conjunto de dados é filtrado para conter apenas usinas fotovoltaicas.
    2.  Uma série temporal da capacidade acumulada ao longo dos anos é criada.
    3.  O modelo `LinearRegression` da Scikit-learn é treinado usando o ano como variável independente (`X`) e a capacidade como variável dependente (`y`).
    4.  O modelo treinado é usado para prever a capacidade para os anos futuros.
- **Resultado:** Uma projeção quantitativa do crescimento da energia solar, acompanhada de uma análise sobre se o crescimento tende a ser linear ou exponencial.

### 4. **Classificação de Usinas com Machine Learning (Exercício 4)**
- **O que faz:** Treina um modelo de classificação para prever o tipo de uma usina com base em suas características (potência, ano de operação e estado).
- **Como funciona:**
    1.  As variáveis categóricas (como o estado) são transformadas em formato numérico usando a técnica de *One-Hot Encoding*.
    2.  Os dados são divididos em conjuntos de treino e teste.
    3.  Um modelo `RandomForestClassifier` é treinado com os dados de treino.
    4.  A acurácia do modelo é avaliada no conjunto de teste.
- **Resultado:** Um modelo preditivo com alta acurácia (96,42%) e a identificação das características mais importantes para determinar o tipo de uma usina.

### 5. **Agrupamento de Usinas por Perfil (Exercício 5)**
- **O que faz:** Utiliza o algoritmo de clusterização K-Means para agrupar usinas com perfis semelhantes, sem conhecimento prévio dos tipos.
- **Como funciona:**
    1.  As variáveis numéricas (potência e ano de operação) são selecionadas e padronizadas para terem a mesma escala.
    2.  O K-Means é aplicado para dividir as usinas em 4 grupos (clusters).
    3.  Os resultados são visualizados em um gráfico de dispersão, onde cada ponto representa uma usina e a cor indica o cluster ao qual pertence.
- **Resultado:** A identificação de perfis de usinas, como "grandes hidrelétricas antigas" e "usinas renováveis recentes e de menor porte".

---

## Para que Serve: Objetivos e Aplicações

Esta análise serve como uma ferramenta poderosa para diversos públicos, desde estudantes e pesquisadores até profissionais do setor de energia. Suas principais aplicações são:

- **Análise de Mercado e Investimento:** Investidores e empresas podem usar os insights para identificar tendências de crescimento em fontes renováveis e as regiões mais promissoras para novos projetos.
- **Planejamento Energético:** Órgãos governamentais e o próprio ONS podem utilizar as previsões de crescimento para planejar a expansão da rede elétrica e garantir a estabilidade do sistema.
- **Pesquisa Acadêmica:** O notebook serve como um exemplo prático de aplicação de ciência de dados em problemas reais do setor de energia, podendo ser utilizado como material de estudo ou ponto de partida para análises mais complexas.
- **Tomada de Decisão Estratégica:** A classificação e a clusterização de usinas ajudam a segmentar o mercado e a entender as características operacionais de diferentes tipos de ativos de geração.

Em resumo, o projeto demonstra como analisar a transição para fontes de energia mais limpas, prever o futuro da matriz energética e criar modelos inteligentes para otimizar a gestão de recursos no setor elétrico brasileiro.
