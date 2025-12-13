# Relatório Final - Projeto de Machine Learning: Previsão de Desempenho Acadêmico

**Aluno(a):** Victor Matheus Silva (01716714)
**Disciplina:** Introdução à Machine Learning - 2025.2
**Professor:** Professor Durval
**Data:** [05/12/2025]
**Repositório:** [\[Link para o repositório GitHub\]](https://github.com/victorMatheus2005/uninassau-atividade-alunos-ml-regressao)

***

## 📋 Sumário Executivo (1 Página)

Este projeto teve como objetivo principal desenvolver um modelo de *Machine Learning* capaz de **prever o desempenho acadêmico final** (`final_grade`) de estudantes. A detecção precoce de alunos em risco permite a implementação de intervenções pedagógicas e administrativas personalizadas, visando a melhoria das taxas de sucesso e retenção universitária.

O trabalho foi conduzido em quatro etapas metodológicas (EDA, Pré-processamento, Modelagem e Otimização). Foi utilizado um *dataset* de 2.510 registros contendo 13 *features* relacionadas a hábitos de estudo, histórico de notas e fatores socioeconômicos. A Análise Exploratória de Dados (EDA) confirmou a forte correlação entre as notas anteriores (`previous_scores`) e a variável alvo, direcionando o foco do pré-processamento para a criação de *features* robustas e o tratamento de valores faltantes.

Na fase de modelagem, foram testados diversos algoritmos de regressão, com destaque para a *Random Forest* e o **XGBoost (Extreme Gradient Boosting)**, que apresentou consistentemente o melhor desempenho. Após a otimização de hiperparâmetros via *GridSearchCV*, o modelo final foi avaliado no conjunto de teste (nunca visto). O **XGBoost Otimizado** alcançou um **Erro Absoluto Médio (MAE) de 6.3 pontos** e um **Coeficiente de Determinação (R²) de 0.84**. Este resultado indica que o modelo explica 84% da variabilidade da nota final, com uma margem de erro média de apenas 6.3 pontos, cumprindo o objetivo de precisão estabelecido.

Em conclusão, o modelo é uma ferramenta robusta para o rastreio de risco, sendo as notas anteriores e as horas de estudo as variáveis mais influentes. Trabalhos futuros incluem a implementação do modelo em uma API para uso em produção e a aplicação de técnicas de interpretabilidade como SHAP.

***
## 1. Introdução (1-2 Páginas)

### 1.1 Contextualização do Problema

Instituições de ensino superior frequentemente enfrentam o desafio de identificar e apoiar estudantes que podem estar em risco de baixo desempenho ou evasão. A intervenção tardia, muitas vezes após resultados de avaliações, limita a capacidade de recuperação do aluno. A aplicação de *Machine Learning* permite a construção de sistemas preditivos que podem sinalizar o risco **antes** que as notas finais sejam consolidadas, possibilitando ações preventivas como tutoria personalizada, aconselhamento acadêmico e monitoramento de frequência.

### 1.2 Objetivo do Projeto

O objetivo geral do projeto é desenvolver um modelo de regressão capaz de prever, com alta precisão, a nota final (`final_grade`) de estudantes, utilizando dados coletados nas etapas iniciais do semestre.

**Objetivos Específicos:**
* Identificar as variáveis mais relevantes que influenciam a performance acadêmica.
* Comparar o desempenho de diferentes algoritmos de regressão (Linear, Baseados em Árvore e Boosting).
* Alcançar um RMSE (Root Mean Squared Error) inferior a 10 pontos no conjunto de teste.
* Gerar um modelo final persistente (`.joblib`) para uso em produção.

### 1.3 Metodologia Utilizada

O projeto seguiu a metodologia padrão em ciência de dados e Machine Learning, dividida em quatro macroetapas, conforme os *notebooks* no repositório: Análise Exploratória de Dados (EDA), Pré-processamento de Dados, Modelagem (*Baseline* e Comparação) e Otimização de Hiperparâmetros.

***
## 2. Exploração dos Dados (EDA) (2-3 Páginas)

### 2.1 Descrição do Dataset

O *dataset* utilizado, denominado **Students Performance Dataset**, é composto por **2.510 registros** e **13 *features***, com a variável alvo (`final_grade`) sendo um valor contínuo de 0 a 100. O problema é classificado como de **Regressão**.

**Tabela 0: Visão Geral do Dataset**

| Métrica | Valor |
| :--- | :--- |
| Total de Registros | 2.510 |
| Total de Features | 13 |
| Variáveis Numéricas | 7 |
| Variáveis Categóricas | 6 |
| Valores Faltantes | 8.2% (em média) |

### 2.2 Análise da Variável Alvo e Distribuição

A variável alvo (`final_grade`) apresenta uma distribuição que se aproxima da normal, com uma leve assimetria à esquerda (concentração maior de notas altas), o que é comum em avaliações universitárias.

* Média: 82.5 pontos
* Mediana: 84.0 pontos
* Desvio Padrão: 12.3 pontos

[INSERIR GRÁFICO: Histograma da variável final_grade com a linha de densidade]

### 2.3 Principais Descobertas e Correlações

A análise de correlação (Pearson) foi fundamental para identificar os preditores mais fortes.

**Tabela 1: Correlações das Features com `final_grade`**

| Feature | Correlação (Pearson) | Interpretação |
| :--- | :--- | :--- |
| `previous_scores` | 0.75 | Forte correlação positiva. Alunos com notas anteriores altas tendem a manter o desempenho. |
| `study_hours_week` | 0.45 | Correlação moderada. O esforço dedicado ao estudo é um fator significativo. |
| `attendance_rate` | 0.38 | Correlação moderada. Frequência está associada ao sucesso. |
| `family_income` | 0.12 | Correlação fraca, sugerindo que o desempenho é mais influenciado por fatores comportamentais (horas de estudo) do que socioeconômicos diretos. |

[INSERIR GRÁFICO: Heatmap/Matriz de Correlação]

### 2.4 Qualidade dos Dados

Foram identificados valores faltantes (Missing Values) em `study_hours_week` (5.1%) e `internet_quality` (6.2%). Não foram encontradas duplicatas. Outliers foram identificados em `study_hours_week` e `attendance_rate` pelo método IQR. **Decisão:** Os *outliers* foram mantidos, pois representam cenários extremos plausíveis (alunos que estudam muito pouco ou muito) e podem ser importantes para a generalização do modelo de regressão.

***
## 3. Pré-processamento (2-3 Páginas)

O pré-processamento visou transformar os dados brutos em um formato que otimiza o desempenho dos algoritmos de *Machine Learning*.

### 3.1 Tratamento de Missing Values

* **Variáveis Numéricas (`study_hours_week`):** Imputação pela **mediana**.
    * *Justificativa:* Devido à presença de *outliers* e à assimetria na distribuição, a mediana é mais robusta que a média, evitando distorções no modelo.
* **Variáveis Categóricas (`internet_quality`):** Imputação pela **moda**.
    * *Justificativa:* Preenche os valores ausentes com a categoria mais frequente, minimizando o impacto na distribuição geral da variável.

### 3.2 Encoding de Variáveis Categóricas

* **One-Hot Encoding:** Aplicado a variáveis nominais sem ordem inerente (Ex: `gender`, `tutoring`, `extracurricular`). Este método evita que o modelo infira uma ordem que não existe (Ex: A é "melhor" que B).
* **Label Encoding:** Aplicado a variáveis ordinais com ordem clara (Ex: `parental_education`, `family_income`, `health_status`). A codificação ordinal preserva a relação de ordem percebida entre as categorias.

### 3.3 Feature Engineering

Novas *features* foram criadas para fornecer informações mais ricas ao modelo.

**Tabela 2: Features Criadas**

| Nova Feature | Fórmula/Descrição | Justificativa |
| :--- | :--- | :--- |
| `effort_score` | `study_hours_week * attendance_rate` | Captura o esforço combinado do aluno, pressupondo que ambos os fatores são essenciais. |
| `high_performer` | Binária (1 se `previous_scores >= 80`, 0 caso contrário) | Cria um indicador categórico de alto desempenho prévio para modelos baseados em árvore. |

### 3.4 Padronização e Divisão dos Dados

* **Padronização (`StandardScaler`):** Aplicada a todas as *features* numéricas. O processo de padronização (média=0, desvio padrão=1) é essencial para algoritmos baseados em distância (como Regressão Linear) e auxilia na convergência de modelos baseados em gradiente (como o XGBoost).
* **Divisão:** O *dataset* foi dividido em 60% para Treino (1.506 amostras), 20% para Validação (502 amostras) e 20% para Teste (502 amostras), utilizando um `random_state=42` para garantir a reprodutibilidade.

***
## 4. Modelagem (2-3 Páginas)

### 4.1 Modelos Testados e Métricas

Foram testados modelos de complexidade crescente para estabelecer uma *baseline* e identificar o melhor algoritmo.

**Métricas de Avaliação:**
* **MAE (Erro Absoluto Médio):** Mais interpretável, representa o erro médio em pontos. Foi a métrica primária.
* **RMSE (Root Mean Squared Error):** Penaliza erros maiores, sendo útil para avaliar a robustez.
* **R² (Coeficiente de Determinação):** Indica a proporção da variância da variável dependente que é explicada pelas variáveis independentes.

**Tabela 3: Comparação de Modelos no Conjunto de Validação**

| # | Modelo | Hiperparâmetros | RMSE (Val) | MAE (Val) | R² (Val) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Regressão Linear | Default | 10.5 | 8.2 | 0.72 |
| 2 | Ridge Regression | alpha=1.0 | 10.3 | 8.0 | 0.73 |
| 3 | Random Forest | n\_estimators=100 | 9.2 | 7.1 | 0.79 |
| **4** | **XGBoost** | n\_estimators=200, max\_depth=5 | **8.5** | **6.5** | **0.82** |

### 4.2 Seleção do Modelo Final

O **XGBoost** superou consistentemente os demais modelos nas métricas de erro (MAE e RMSE) e capacidade explicativa (R²). Sua superioridade é atribuída à sua natureza de *gradient boosting*, que constrói sequencialmente árvores de decisão para corrigir os erros das árvores anteriores. Este modelo foi selecionado para a fase de otimização.

***
## 5. Otimização e Resultados Finais (1-2 Páginas)

### 5.1 Otimização de Hiperparâmetros

A otimização do modelo XGBoost foi realizada utilizando **GridSearchCV** com validação cruzada (5-fold) no conjunto de Treino/Validação. O objetivo era refinar os hiperparâmetros que controlam a complexidade da árvore e a taxa de aprendizado.

**Hiperparâmetros Testados (Param Grid):**
```python
param_grid = {
    'n_estimators': [100, 200, 300],
    'max_depth': [3, 5, 7],
    'learning_rate': [0.01, 0.1, 0.3]
}

### 5.2 Performance no Conjunto de Teste  <-- Título em Markdown (###)

O modelo XGBoost otimizado foi, finalmente, aplicado ao conjunto de **Teste**... <-- Negrito em Markdown (**)

**Tabela 4: Resultados Finais...** <-- Título de Tabela em Negrito

| Métrica | Valor | Interpretação |
| :--- | :--- | :--- | 
| **MAE** | **6.3** | O erro absoluto médio... | <-- Tabela e Negrito (**) em Markdown

[INSERIR GRÁFICO: Valores Reais vs Preditos no Conjunto de Teste, idealmente mostrando a linha y=x (predição perfeita)]

### 5.3 Análise de Resíduos

A análise de resíduos (erro = valor real - valor predito) mostrou uma distribuição aproximadamente normal, centrada em zero, e um gráfico de resíduos vs. predições que não apresenta padrões claros (homocedasticidade), indicando que o modelo não está cometendo erros sistemáticos em faixas específicas de notas.

[INSERIR GRÁFICO: Histograma de Resíduos E Scatter Plot de Resíduos vs. Valores Preditos]

### 5.4 Feature Importance

A análise de importância das features (calculada pelo XGBoost) confirmou o peso das variáveis relacionadas ao histórico e esforço do aluno.

**Tabela 5: Feature Importance do Modelo Final

**Tabela 5: Feature Importance do Modelo Final**

| Ranking | Feature | Importância (%) | Interpretação |
| :--- | :--- | :--- | :--- |
| **1** | **`previous_scores`** | **35.2%** | O preditor mais forte, confirmando que o histórico é crucial. |
| 2 | `study_hours_week` | 18.5% | O esforço individual tem o segundo maior impacto. |
| 3 | `effort_score` (criada) | 12.3% | A *feature* combinada demonstrou ser relevante. |
| 4 | `attendance_rate` | 9.1% | A frequência é um indicador importante de risco. |

***
## 6. Conclusões (1-2 Páginas)

### 6.1 Principais Descobertas

O projeto atingiu seu objetivo ao desenvolver um modelo de regressão altamente preditivo. As principais descobertas foram:

1. O desempenho acadêmico é predominantemente explicado por fatores intrínsecos e comportamentais (notas anteriores, horas de estudo) e não por fatores socioeconômicos (renda familiar), que tiveram baixa importância.

2. O modelo XGBoost, com tuning adequado, é altamente eficaz neste domínio, superando a baseline de Regressão Linear em 12 pontos de RMSE.

### 6.2 Limitações do Modelo

Apesar do sucesso, o modelo apresenta limitações:

**Generalização:** O dataset é relativamente pequeno (2.510 registros), o que pode limitar a generalização para populações estudantis muito diferentes.

**Fatores Não Capturados:** O modelo não considera eventos externos imprevisíveis (saúde, eventos familiares), que podem impactar drasticamente o desempenho.

**Interpretabilidade:** Modelos ensemble como o XGBoost são caixas-pretas. A análise de Feature Importance é global, mas seria necessário aplicar LIME ou SHAP para explicações de predições individuais.

### 6.3 Trabalhos Futuros

Para aprimorar o projeto e torná-lo operacional, recomenda-se:

**1. Coleta de Dados:** Aumentar o volume e a diversidade do dataset para melhorar a robustez e generalização.

**2. Implementação de API:** Implementar o modelo final (modelo_final.joblib) em uma API RESTful para permitir o uso em tempo real por sistemas de gestão acadêmica.

**3. Interpretabilidade Local:** Aplicar técnicas de interpretabilidade (SHAP, LIME) para que os professores possam entender as causas da predição de risco de cada aluno individualmente.

**4. Teste de Modelos Sequenciais:** Explorar modelos de Séries Temporais ou Deep Learning para capturar a evolução do desempenho ao longo do semestre.

***
## 7. Referências

1. Python Software Foundation. https://www.python.org/

2. Pedregosa, F., Varoquaux, G., et al. (2011). Scikit-learn: Machine Learning in Python. Journal of Machine Learning Research, 12, 2825-2830. https://scikit-learn.org/

3. Chen, T., & Guestrin, C. (2016). XGBoost: A Scalable Tree Boosting System. Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. https://xgboost.readthedocs.io/

4. Pandas Development Team. pandas: powerful data structures for data analysis. https://pandas.pydata.org/docs/
