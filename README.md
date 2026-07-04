# MVP — Previsão de Custos de Plano de Saúde

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Eddy8080/MVP-individual-de-Machine-Learning-Analytics/blob/main/mvp_insurance_charges.ipynb)

---

## Sobre o projeto

MVP individual desenvolvido para a disciplina **Machine Learning & Analytics**.

O objetivo é demonstrar o fluxo completo de um projeto de aprendizado de máquina:
definição do problema, preparação dos dados, modelagem, otimização e avaliação crítica dos resultados.

---

## Problema

**Prever o custo anual de um plano de saúde privado** com base em características
demográficas e de saúde do segurado — problema de **regressão supervisionada**.

---

## Dataset

| Item | Detalhe |
|---|---|
| Nome | Medical Insurance Charges |
| Fonte | GitHub público — `stedy/Machine-Learning-with-R-datasets` |
| URL | `https://raw.githubusercontent.com/stedy/Machine-Learning-with-R-datasets/master/insurance.csv` |
| Registros | 1.338 |
| Atributos | 7 (6 features + 1 variável-alvo) |
| Variável-alvo | `charges` — custo anual do plano em USD |

O dataset é carregado diretamente via URL pública no notebook — sem upload manual, login ou token.

---

## Estrutura do notebook

| Seção | Descrição |
|---|---|
| 0. Ambiente | Imports e seed fixo (`random_state=42`) |
| 1. Apresentação do problema | Contexto, objetivo, hipóteses e restrições |
| 2. Apresentação dos dados | Fonte, atributos e limitações |
| 3. Análise exploratória (EDA) | Distribuições, correlações e visualizações |
| 4. Preparação dos dados | Encoding, normalização e pipelines |
| 5. Divisão dos dados | 80% treino / 20% teste sem data leakage |
| 6. Modelagem | Baseline → Regressão Linear → Árvore → Random Forest |
| 7. Otimização | GridSearchCV com 5-fold cross-validation |
| 8. Avaliação | MAE, RMSE, R², resíduos, importância das features |
| 9. Conclusão | Narrativa completa e próximos passos |
| Checklist | Todas as perguntas do checklist respondidas |

---

## Modelos avaliados

| Modelo | R² (aprox.) |
|---|---|
| Baseline (Média) | ~0.00 |
| Regressão Linear | ~0.79 |
| Árvore de Decisão | ~0.76 |
| Random Forest | ~0.87 |
| **Random Forest Otimizado** | **~0.88** |

O **Random Forest Otimizado** (GridSearchCV) foi escolhido como melhor solução:
explica ~88% da variação nos custos e captura interações não-lineares entre as features.

---

## Como executar

### Via Google Colab (recomendado)
Clique no badge **"Abrir no Colab"** no topo deste README — o notebook abre diretamente com sua conta logada.

### Via Jupyter local
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook mvp_insurance_charges.ipynb
```

O notebook roda do início ao fim sem nenhuma configuração adicional.

---

## Arquivos do repositório

```
.
├── mvp_insurance_charges.ipynb   # Notebook principal (entrega)
├── README.md                     # Este arquivo
└── mvp.md                        # Requisitos originais do MVP
```

---

## Tecnologias utilizadas

- Python 3.10+
- pandas · numpy · matplotlib · seaborn
- scikit-learn — Pipeline, ColumnTransformer, GridSearchCV
