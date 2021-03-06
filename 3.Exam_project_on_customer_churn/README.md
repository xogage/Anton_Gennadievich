# Проект по:

- Первичному анализу и предобработке данных.
- Разметке целевого признака.
- Поиску модели для обучения.
- Обучению модели.
- A/B-тесту.

# Библиотеки:

- pandas, numpy, matplotlib, plotly, scipy(A\B-тесты), time, StandardScaler, shuffle, GridSearchCV, cross_val_score, sklearn models, accuracy_score, roc_auc_score, classification_report, confusion_matrix, eli5 

# Описание:

- Оператор связи хочет научиться прогнозировать отток клиентов. Если выяснится, что пользователь планирует уйти, ему будут предложены промокоды и специальные условия. 

# Задача проекта:

- Построить модель для прогнозирования оттока клиентов (Это поможет компании сохранить клиентов путем предложения скидок или подарков).

# Что мы имеем:

- Есть персональные данные о некоторых клиентах, информация об их тарифах и договорах.

**Примечание:** Информация о договорах актуальна на 1 февраля 2020.

## Услуги и доп. услуги для клиентов

Основные: 

1. Стационарную телефонную связь (Возможно подключение телефонного аппарата к нескольким линиям одновременно).
2. Интернет (Подключение может быть двух типов: через телефонную линию (DSL) или оптоволоконный кабель (*Fiber optic*)).

Доп. услуги:

- Интернет-безопасность: антивирус (*DeviceProtection*) и блокировка небезопасных сайтов (*OnlineSecurity*);
- Выделенная линия технической поддержки (*TechSupport*);
- Облачное хранилище файлов для резервного копирования данных (*OnlineBackup*);
- Стриминговое телевидение (*StreamingTV*) и каталог фильмов (*StreamingMovies*).

## Описание столбцов:
- 4 таблицы с данными: У всех общий столбец "customerID" - уникальный номер пользователя.  


    * Столбец "cont" - информация о договоре; (ниже описание столбцов)
        - BeginDate - дата начала пользования
        - EndDate - дата окончания пользования
        - Type - тип оплаты
        - PaperlessBilling - электронный тип выписки
        - PaymentMethod - способ оплаты  
        - MonthlyCharges - ежемесячные затраты на услуги
        - TotalCharges - общие затраты на услуги
        
    * Столбец "pers" - персональные данные клиента; (ниже описание столбцов)  
        - gender - пол клиента
        - SeniorCitizen - пожилой клиент
        - Partner - наличие партнера
        - Dependents - клиент другого гражданства
    
    * Столбец "inet" - информация об интернет-услугах; (ниже описание столбцов)  
        - InternetService - тип подключения
        - OnlineSecurity - безопасность в интернете
        - OnlineBackup - резервное копирование онлайн
        - DeviceProtection - защита устройства
        - TechSupport - техническая поддержка
        - StreamingTV - cтриминговое телевидение
        - StreamingMovies - каталог фильмов
    
    * Столбец "phone" - информация об услугах телефонии. (ниже описание столбцов)  
        - MultipleLines - многолинейность 

# Вывод по проекту:

- В начале познакомились с данными и сделал небольшую предобработку. Проведены проверки по поиску пропусков и дубликатов. Исправлены типы данных в таблицах. Провел анализ на наличие аномалий.
- Т.к. небыло разметки по которой можно было бы проводить обучение с учителем, сделал его в ручную по столбцу "EndDate", который показывал дату окончания пользованием услугой.
- Создал признаки, разделил на train и test выборки. Проверил баланса классов и провел тестировочные прогоны для моделей. 
- После тестов выбрал подходящую модель по accuracy и ROC-AUC. Отредактировал признаки и обучил заново модель подбирая гиперпараметры. Проверил мою модель на тестовых данных и получил значения удовлетворяющие ТЗ. Вывел классы на "матрице ошибок" и выяснил, что ошибка 2 рода самая дорогая для компании.
- Стоило бы протестировать модели еще раз не на accuracy, а на precision, чтобы найти модель которая минимизирует ошибку 2 рода лучше всех, но проведя А/В-тест выяснил, что моя модель предсказывает неплохо для того, чтобы компания не несла убытки по ошибке 2 рода.

**Итог:** Получил рабочую модель, которая не несет убытки в случае ухода клиента. 