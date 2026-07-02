# Projeto Avaliativo - Machine Learning [T1]
**Risco de Crédito (Setor Financeiro)**

## Descrição do Problema de Negócio
Um banco precisa prever se um cliente se tornará inadimplente (alvo: `loan_status = 1`) ou se pagará o empréstimo em dia (alvo: `loan_status = 0`). O objetivo é construir um pipeline preditivo para minimizar os riscos financeiros, evitando classificar um mau pagador como "Seguro" (Falso Negativo) e entender o impacto de classificar um bom pagador como "Risco de Calote" (Falso Positivo).

## Dicionário de Dados
*   `person_age`: Idade da pessoa
*   `person_income`: Renda anual da pessoa
*   `person_home_ownership`: Propriedade da casa (ex: RENT, OWN, MORTGAGE)
*   `person_emp_length`: Tempo de emprego em anos
*   `loan_intent`: Motivo do empréstimo (ex: EDUCATION, MEDICAL, VENTURE)
*   `loan_grade`: Nota/grau do empréstimo
*   `loan_amnt`: Valor do empréstimo
*   `loan_int_rate`: Taxa de juros do empréstimo
*   `loan_status`: Status do empréstimo (0 = pagará em dia, 1 = inadimplente) - **Variável Alvo**
*   `loan_percent_income`: Porcentagem da renda comprometida com o empréstimo
*   `cb_person_default_on_file`: Histórico de inadimplência prévia
*   `cb_person_cred_hist_length`: Tamanho do histórico de crédito em anos
*   `comprometimento_renda`: Porcentagem da renda comprometida calculada como `(loan_amnt / person_income) * 100` *(A ser criada)*

## Como rodar o projeto
1. Clone este repositório.
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```
3. Abra o Jupyter Notebook:
   ```bash
   jupyter notebook projeto_pipeline.ipynb
   ```

## Resumo Executivo
**Insights da EDA:** A base apresentou um forte desbalanceamento na variável alvo (`loan_status`), exigindo técnicas de Undersampling no Treino. Variáveis como idade e tempo de emprego possuíam outliers extremos (ex: > 120 anos), que foram removidos para garantir a estabilidade dos modelos (em especial do KNN). A imputação de nulos foi realizada de forma robusta utilizando a Mediana.
**Veredito do Modelo:** Após testes comparativos buscando combater o Overfitting, a **Árvore de Decisão com max_depth=7** apresentou a melhor capacidade de generalização e o melhor *Recall* para a classe minoritária. No contexto financeiro, o **Falso Negativo** (prever que o cliente é seguro, mas ele dar calote) traz o pior impacto (perda do principal do empréstimo). A Árvore de Decisão minimizou significativamente esse erro em relação ao KNN, sendo o modelo oficialmente recomendado para entrar em produção.