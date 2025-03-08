


# Análise Exploratória de Dados - Vendas de Café
Informações do dataframe: https://www.kaggle.com/datasets/ahmedmohamed2003/cafe-sales-dirty-data-for-cleaning-training/data

Este projeto realiza uma análise exploratória de dados sobre transações de vendas em cafeterias, aplicando técnicas estatísticas e de visualização para extrair insights. O estudo foi desenvolvido em Python, utilizando as bibliotecas Pandas, Numpy, Matplotlib, Seaborn e Scipy.

## Objetivos
- Identificação e tratamento de dados inválidos ou ausentes
- Transformação de variáveis categóricas e numéricas
- Análises estatísticas univariadas e bivariadas
- Estudo de correlação entre variáveis

## Problema Enfrentado: Imputação Cíclica de Dados
Durante o processo de reparação dos dados, surgiu um problema de imputação cíclica. Algumas variáveis estavam relacionadas de forma que a correção de uma poderia habilitar a correção da outra em uma iteração posterior. Por exemplo:

1 - Relação entre "Item" e "Preço por Unidade": Se um item é conhecido, seu preço pode ser imputado.

2 - Relação matemática entre "Quantidade", "Preço por Unidade" e "Total Gasto": Se duas dessas variáveis são conhecidas, a terceira pode ser calculada.

No entanto, essas correções não ocorrem simultaneamente. A execução de uma regra pode gerar novos dados passíveis de correção pela outra, mas, como a análise era sequencial, esses novos dados não eram corrigidos no primeiro ciclo.

## Solução Adotada
Para lidar com essa dependência entre correções, foi implementado um loop iterativo que executa as funções de reparo até que não haja mais mudanças a serem feitas. Esse processo garantiu que todas as linhas possíveis fossem corrigidas antes de finalizar a análise.

## Resultados
Após o tratamento, a quantidade de dados inválidos foi significativamente reduzida, melhorando a qualidade das análises estatísticas e permitindo insights mais confiáveis sobre as vendas.
