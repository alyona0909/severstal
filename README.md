# Хакатон Северстали и McKinsey. Задача «Анализ Контрагентов»

## Описание файлов

* counterparty-analysis/ - исходные данные за 2016-2021 года
* counterparty-analysis/Описание файлов_контрагентов.docx - подробное описание исходных данных
* create_dataset.ipynb - формирование датасета для обучения и валидации
* data.csv - сформированный датасет для обучения и валидации
* modeling.ipynb - построение модели
* eda.ipynb - анализ полученных данных 

## Требования задачи
•	Провести исследование имеющихся данных и спрогнозировать просрочку по контрагенту на следующий год: 
   a) факт просрочки; 
   б) просрочку более 30 дней; 
   с) просрочку в диапазоне от 60 до 90 дней
• По представленным данные за разные годы с различным набором информации провести EDA, определить и визуализировать взаимосвязи и самые значимые факторы;


## Описание проекта

* create_dataset.ipynb - - сформирован итоговый файл для обучения модели (data.csv), полученный в результате совмещения данных за 2019-2021 года; проведена очистка и предобработка данных.
* eda.ipynb – проведен разведочный анализ данных, визуализирована взаимосвязь таргета и различных видов задолженности; выявлена возможная взаимосвязь с одной из предложенных фичей и размером контрагента (по фиче «Итого» можно определить является ли контрагент крупным или средним/мелким)
* modeling.ipynb – применено два подхода (LogisticRegression и CatBoostClassifier), подбор гиперпараметров осуществлялся с помощью optuna
  ** для каждого из таргетов построена отдельная модель
  ** для контроля качества использовалась стратифицированная кросс-валидация и метрика  roc_auc_score 

## Результаты
* Для факта просрочки: Средний ROC_AUC score: 0.7829
* Для просрочки 0-30 дней: Средний ROC_AUC score: 0.8923
* Для просрочки более 30 дней: Средний ROC_AUC score: 0.7964

