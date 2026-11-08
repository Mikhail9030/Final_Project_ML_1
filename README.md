# IT Service Ticket Classification

[![GitHub](https://img.shields.io/badge/GitHub-Mikhail9030-blue?logo=github)](https://github.com/Mikhail9030/Final_Project_ML_1)
[![Python](https://img.shields.io/badge/Python-3.10%2B-brightgreen)](https://www.python.org/)
[![MLflow](https://img.shields.io/badge/MLflow-Tracking-blueviolet)](https://mlflow.org/)

**Автор:** Михаил Гуляев (`Mikhail9030`)  
**Преподаватель:** Даниил Корбут  
**Репозиторий:** [GitHub / Mikhail9030 / Final_Project_ML_1](https://github.com/Mikhail9030/Final_Project_ML_1)

---

## 📌 Описание задачи
Проект посвящен автоматической классификации входящих обращений пользователей в службу IT-поддержки по 8 тематическим группам (`Access`, `Administrative rights`, `HR Support`, `Hardware`, `Internal Project`, `Miscellaneous`, `Purchase`, `Storage`). 

Цель — реализовать полный цикл NLP (EDA, предобработка, построение пайплайнов Sklearn и нейросетей PyTorch) с трекингом параметров и метрик в **MLflow**.

---

## 📊 Описание датасета
* **Источник:** Kaggle IT Service Ticket Classification Dataset
* **Объем данных:** 47 837 записей (Train: 38 269; Test: 9 568)
* **Признаки:**
  * `Document`: Исходный текст обращения на английском языке.
  * `Topic_group`: Целевая категория IT-обращения.
* **Пропуски:** 0 во всех колонках.

---

## 📈 Таблица результатов

| Модель | Векторизация / Архитектура | Accuracy | F1-Macro | F1-Weighted |
| :--- | :--- | :---: | :---: | :---: |
| **Logistic Regression** | **TF-IDF (10k features, n-grams 1-2)** | **0.8584** | **0.8547** | **0.8584** |
| PyTorch MLP | TF-IDF (5k features, 3 layers, 5 epochs) | 0.8485 | 0.8526 | 0.8485 |
| Random Forest Classifier | TF-IDF (10k features, max_depth=20) | 0.6313 | 0.6043 | 0.6274 |

### Подробный отчет по классам (Logistic Regression):
| Класс | Precision | Recall | F1-Score | Support |
| :--- | :---: | :---: | :---: | :---: |
| **Access** | 0.92 | 0.88 | 0.90 | 1425 |
| **Administrative rights** | 0.88 | 0.63 | 0.74 | 352 |
| **HR Support** | 0.86 | 0.87 | 0.87 | 2183 |
| **Hardware** | 0.80 | 0.90 | 0.84 | 2724 |
| **Internal Project** | 0.92 | 0.80 | 0.86 | 424 |
| **Miscellaneous** | 0.84 | 0.82 | 0.83 | 1412 |
| **Purchase** | 0.98 | 0.86 | 0.92 | 493 |
| **Storage** | 0.95 | 0.83 | 0.89 | 555 |

---

## 🛠 Инструкция по запуску

### 1. Клонирование репозитория
```bash
git clone [https://gitverse.ru/gulaevmihail112/it-service-ticket-classification.git](https://gitverse.ru/gulaevmihail112/it-service-ticket-classification.git)
cd it-service-ticket-classification