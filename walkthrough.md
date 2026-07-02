# Conclusão do Projeto Avaliativo de Machine Learning [T1]

O desenvolvimento técnico do seu pipeline corporativo para a base de **Risco de Crédito** foi concluído com sucesso e está devidamente versionado no Git!

## O que foi realizado

1. **Repositório Git e Branches:** O projeto está configurado no seu repositório local com as boas práticas exigidas. Trabalhamos nas branches `fase/eda`, `fase/data-prep`, `fase/feature-engineering` e `fase/modelagem`.
2. **README.md e Requirements:** Documentação inicializada contendo dicionário de dados, resumo executivo e lista de dependências no `requirements.txt`.
3. **Pipeline Completo no Jupyter Notebook (`projeto_pipeline.ipynb`):**
   - **EDA (Fase 1):** Geramos gráficos estatísticos e análises textuais justificando as decisões tomadas.
   - **Limpeza (Fase 2):** Tratamos as duplicadas, imputamos nulos usando a **mediana** (devido aos outliers detectados) e removemos erros de input flagrantes (idade > 100, emprego > 60).
   - **Engenharia de Atributos (Fase 3):** Criamos a coluna calculada `comprometimento_renda` da forma correta e tratada.
   - **Preparação Segura (Fase 4):** Balanceamento aplicado rigorosamente apenas no Treino (combatendo Data Leakage), além do Escalonamento exclusivo para o modelo de distâncias euclidianas (KNN).
   - **Modelagem (Fase 5 e 6):** Testamos Árvores e KNN variando profundidade e vizinhos. Escolhemos a melhor Árvore de Decisão por apresentar maior recall para evitar o "Falso Negativo" (o erro que dá prejuízo real no Risco de Crédito).

## Próximo Passo: Gravação de Vídeo!

> [!IMPORTANT]
> A última etapa exigida pelo seu professor é a **gravação de um vídeo de até 7 minutos** respondendo às 5 perguntas do item 5.3 do roteiro (página 5 do PDF).

**Dicas para o seu vídeo:**
*   Você já possui todas as respostas e justificativas dentro das células de texto (Markdown) do próprio notebook! Basta ler e explicar os resultados das matrizes de confusão.
*   Você pode abrir o notebook rodado na tela, mostrar os *Classification Reports* e justificar sua escolha pela Árvore de Decisão com base no prejuízo do **Falso Negativo** (explicado lá no último parágrafo do projeto).

Não esqueça de publicar as suas branches locais no GitHub (fazendo `git push --all`) e enviar os links (GitHub e Vídeo) na plataforma AVA.

**Sucesso no projeto! Me avise se precisar de qualquer outra coisa.**
