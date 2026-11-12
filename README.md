# Titanic: previsão de sobrevivência com Random Forest

Modelo de machine learning desenvolvido para a competição **Titanic - Machine Learning from Disaster** no Kaggle. O objetivo é prever quais passageiros sobreviveram ao naufrágio a partir de dados como idade, sexo, classe da passagem e porto de embarque.

[Ver notebook público no Kaggle](COLE_AQUI_O_LINK_DO_SEU_NOTEBOOK)

## Resultados

- **Validação (20% dos dados de treino):** ~82% de acurácia
- **Submissão oficial no Kaggle (dados de teste):** ~74,6% de acurácia

## Tecnologias utilizadas

- Python 3
- Pandas e NumPy
- Scikit-learn (`train_test_split`, `RandomForestClassifier`, `accuracy_score`)

## Como o projeto foi construído

1. **Exploração dos dados:** leitura do arquivo `train.csv` e verificação das dimensões do dataset e dos valores ausentes.
2. **Limpeza:**
   - Remoção de `Cabin` (cerca de 77% de valores vazios) e das colunas de identificação `PassengerId`, `Name` e `Ticket`.
   - Preenchimento das idades ausentes (`Age`) e da tarifa (`Fare`, no conjunto de teste) com a mediana.
   - Preenchimento dos valores vazios em `Embarked` com a moda.
3. **Transformação de variáveis:** conversão das colunas categóricas `Sex` e `Embarked` para formato numérico usando One-Hot Encoding (`pd.get_dummies`).
4. **Treinamento e validação:** divisão em 80% para treino e 20% para validação (`random_state=42`) e treino de um `RandomForestClassifier` com 100 árvores (`n_estimators=100`).
5. **Previsão e envio:** aplicação das mesmas etapas de limpeza no arquivo `test.csv` e geração do `submission.csv` para avaliação na competição.

## Próximos passos

- Criar novas features a partir das colunas existentes (como tamanho da família somando `SibSp` + `Parch`).
- Testar outros algoritmos de classificação e ajustar os hiperparâmetros do Random Forest.

## Arquivos do repositório

- `titanic-previs-o-com-random-forest.ipynb`: notebook completo com o código e as explicações de cada etapa.
- `README.md`: documentação do projeto.