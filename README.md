# uninassau-atividade-alunos-ml-regressao

## 📚 Visão Geral do Projeto

Este repositório contém o projeto de Machine Learning desenvolvido para a disciplina de Introdução à Machine Learning, com foco na **previsão do desempenho acadêmico final** (`final_grade`) de estudantes.

O objetivo foi construir um modelo de **Regressão** robusto, utilizando o *dataset* `students_performance.csv`. O algoritmo selecionado, após otimização de hiperparâmetros, foi o **XGBoost (Extreme Gradient Boosting)**.

### Resultados Chave
* **Modelo Final:** XGBoost Otimizado.
* **Métrica de Teste (MAE):** 6.3 pontos.
* **Métrica de Teste (R²):** 0.84.

## 📁 Estrutura do Repositório

A estrutura segue o padrão recomendado para projetos de Ciência de Dados:

* **`data/`**: Contém o dataset original (`students_performance.csv`).
* **`notebooks/`**: Contém os *Jupyter Notebooks* que documentam cada etapa do projeto (EDA, Pré-processamento, Modelagem e Otimização).
* **`docs/`**: Contém o **RELATORIO_FINAL.md** completo.
* **`models/`**: Contém o modelo final treinado e persistido (`modelo_final.joblib`).
* **`requirements.txt`**: Lista todas as dependências Python necessárias para reproduzir o ambiente.
* **`README.md`**: Este arquivo.

## ⚙️ Como Reproduzir o Projeto

Para reproduzir o ambiente e os resultados deste projeto, siga os seguintes passos:

### 1. Clonar o Repositório

Abra o terminal e clone o seu repositório (substitua a URL se necessário):

```bash
git clone [https://github.com/victorMatheus2005/uninassau-atividade-alunos-ml-regressao.git](https://github.com/victorMatheus2005/uninassau-atividade-alunos-ml-regressao.git)
cd uninassau-atividade-alunos-ml-regressaopip install -r requirements.txt

### 2. Membros do Grupo

**Victor Matheus Silva (01716714)**

** José Humberto Silva de Araújo – (01589405)** 

** Naeliton Chavez - (01594737) **