# MVP — Previsão da Qualidade do Vinho Tinto

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Eddy8080/MVP-individual-de-Machine-Learning-Analytics/blob/main/mvp_wine_quality.ipynb)

---

## Sobre o projeto

MVP individual desenvolvido para a disciplina **Machine Learning & Analytics**.

O objetivo é demonstrar o fluxo completo de um projeto de aprendizado de máquina:
definição do problema, preparação dos dados, modelagem, otimização e avaliação crítica dos resultados.

---

## Problema

**Prever a nota de qualidade de vinhos tintos** (escala 0–10) com base em suas propriedades físico-químicas — problema de **regressão supervisionada**.

---

## Dataset

| Item | Detalhe |
|---|---|
| Nome | Wine Quality – Red Wine |
| Fonte | UCI Machine Learning Repository |
| Repositório | `Eddy8080/MVP-individual-de-Machine-Learning-Analytics` |
| URL | `https://raw.githubusercontent.com/Eddy8080/MVP-individual-de-Machine-Learning-Analytics/main/winequality-red.csv` |
| Registros | 1.599 |
| Atributos | 12 (11 features físico-químicas + 1 variável-alvo) |
| Variável-alvo | `quality` — nota de qualidade (0 a 10) |

O dataset é carregado diretamente via URL pública do repositório GitHub do autor — sem upload manual, login ou token.

---

## Estrutura do notebook

| Seção | Descrição |
|---|---|
| 0. Ambiente | Imports e seed fixo (`random_state=42`) |
| 1. Apresentação do problema | Contexto, objetivo, hipóteses e restrições |
| 2. Apresentação dos dados | Fonte, atributos e limitações |
| 3. Análise exploratória (EDA) | Distribuições, correlações e visualizações |
| 4. Preparação dos dados | Normalização via StandardScaler em Pipeline |
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
| Regressão Linear | ~0.36 |
| Árvore de Decisão | ~0.30 |
| Random Forest | ~0.50 |
| **Random Forest Otimizado** | **~0.52** |

O **Random Forest Otimizado** (GridSearchCV) foi escolhido como melhor solução.

---

## Como executar

### Via Google Colab (recomendado)
Clique no badge **"Abrir no Colab"** no topo deste README — o notebook abre diretamente com sua conta logada.

### Via Jupyter local
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook mvp_wine_quality.ipynb
```

O notebook roda do início ao fim sem nenhuma configuração adicional.

---

## Arquivos do repositório

```
.
├── mvp_wine_quality.ipynb    # Notebook principal (entrega)
├── winequality-red.csv       # Dataset (Wine Quality – UCI)
└── README.md                 # Este arquivo
```

---

## Tecnologias utilizadas

- Python 3.10+
- pandas · numpy · matplotlib · seaborn
- scikit-learn — Pipeline, StandardScaler, GridSearchCV
