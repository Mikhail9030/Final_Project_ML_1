# IT Service Ticket Classification

[![GitVerse](https://img.shields.io/badge/GitVerse-gulaevmihail112-blue)](https://gitverse.ru/gulaevmihail112)
[![Python](https://img.shields.io/badge/Python-3.10%2B-brightgreen)](https://www.python.org/)
[![MLflow](https://img.shields.io/badge/MLflow-Tracking-blueviolet)](https://mlflow.org/)

**Автор:** Михаил Гуляев  
**Преподаватель:** Даниил Корбут  
**Репозиторий:** [GitVerse / gulaevmihail112](https://gitverse.ru/gulaevmihail112)

---

## 📌 Описание задачи
Проект посвящен автоматической классификации текстовых обращений пользователей в службу IT-поддержки по 8 ключевым категориям (`Access`, `Administrative rights`, `HR Support`, `Hardware`, `Internal Project`, `Miscellaneous`, `Purchase`, `Storage`). 

Цель работы — построить полный пайплайн машинного обучения и глубокого обучения (PyTorch MLP), провести трекинг экспериментов через **MLflow** и определить оптимальную модель для внедрения в production.

---

## 📊 Описание датасета
* **Источник:** [Kaggle IT Service Ticket Classification Dataset](https://www.kaggle.com/datasets/adisongoh/it-service-ticket-classification-dataset)
* **Размер выборки:** 47,837 записей (Train: 38,269; Test: 9,568)
* **Структура:**
  * `Document`: Исходный текст тикета на английском языке.
  * `Topic_group`: Целевой класс обращения.

---

## 📈 Таблица результатов

| Модель | Векторизация / Архитектура | Accuracy | F1-Macro | F1-Weighted |
| :--- | :--- | :---: | :---: | :---: |
| **Logistic Regression** | **TF-IDF (10k features, n-grams 1-2)** | **0.8584** | **0.8547** | **0.8584** |
| **PyTorch MLP** | **TF-IDF (5k features, 3 layers)** | **0.8491** | **0.8522** | **0.8488** |
| Random Forest Classifier | TF-IDF (10k features, max_depth=20) | 0.6313 | 0.6043 | 0.6274 |
```[cite: 6]

### Проверочный чек-лист перед отправкой в GitVerse:
1. В ноутбуке сделан **Kernel -> Restart and Run All** — все ячейки отрабатывают сверху вниз без ошибок.
2. Локальная папка `mlruns` сформировалась.
3. Файл `README.md` в корне репозитория сохранен.
4. Выполнен коммит и `git push` в репозиторий GitVerse.

Работа полностью готова к сдаче Даниилу Корбуту!