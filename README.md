# IT Service Ticket Classification

[![GitHub](https://img.shields.io/badge/GitHub-Mikhail9030-blue?logo=github)](https://github.com/Mikhail9030/Final_Project_ML_1)
[![Python](https://img.shields.io/badge/Python-3.10%2B-brightgreen)](https://www.python.org/)
[![MLflow](https://img.shields.io/badge/MLflow-Tracking-blueviolet)](https://mlflow.org/)

**Автор:** Михаил Гуляев (`Mikhail9030`)  
**Преподаватель:** Даниил Корбут  
**Репозиторий:** [GitHub / Mikhail9030 / Final_Project_ML_1](https://github.com/Mikhail9030/Final_Project_ML_1)

---

## Описание проекта
Проект посвящен решению задачи многоклассовой классификации обращений пользователей в службу технической поддержки (IT Service Desk). Система автоматически распределяет входящие текстовые тикеты по 8 тематическим категориям (`Hardware`, `HR Support`, `Access`, `Miscellaneous`, `Storage`, `Purchase`, `Internal Project`, `Administrative rights`)[cite: 8].

### Датасет
* **Источник:** Kaggle — *IT Service Ticket Classification Dataset* (`all_tickets_processed_improved_v3.csv`)
* **Объём:** 47 837 обращений (пропуски отсутствуют)
* **Длина текстов:** медиана — 26 слов, среднее — 43.6 слова (от 2 до 981 слова)
* **Разбиение:** стратифицированный сплит 80/20 — **38 269** записей в `Train` и **9 568** записей в `Test`

---

## Результаты экспериментов (MLflow)

Все модели обучены на едином разбиении данных и залогированы в эксперименте MLflow (`IT_Ticket_Classification_Daniil_Korbut`):

| Модель | Признаки / Параметры | Accuracy | F1-Macro | F1-Weighted |
| :--- | :--- | :---: | :---: | :---: |
| **Logistic Regression** | **TF-IDF (10k features, n-grams 1–2)** | **0.8584** | **0.8547** | **0.8584** |
| PyTorch MLP | TF-IDF (5k features, 3 layers, 5 epochs) | 0.8493 | 0.8526 | 0.8491 |
| Random Forest Classifier | TF-IDF (10k features, max_depth=20) | 0.6313 | 0.6043 | 0.6274 |

* **Победитель:** `Logistic Regression` в связке с `TfidfVectorizer(ngram_range=(1, 2))` показала наилучшее качество по всем метрикам при минимальном времени обучения и инференса.
* **Узкое место:** миноритарный класс `Administrative rights` (3.68% выборки, 352 примера в тесте) имеет наименьший `F1-Score = 0.74` из-за дисбаланса классов и пересечения лексики с категорией `Hardware`[cite: 8].

---

## Структура репозитория
```text
├── Final_project_1.ipynb    # Основной Jupyter Notebook с полным циклом (Шаги 1–9)
├── README.md                # Документация проекта и сводка метрик
├── requirements.txt         # Зависимости проекта
└── .gitignore               # Исключения для Git (.venv, кэш, крупные датасеты)

Клонирование репозитория
bash
git clone [https://gitverse.ru/gulaevmihail112/it-service-ticket-classification.git](https://gitverse.ru/gulaevmihail112/it-service-ticket-classification.git)
cd it-service-ticket-classification