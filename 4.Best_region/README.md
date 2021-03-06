# Проект по:

- Подготовке данных
- Обучению и проверке модели
- Расчету прибыли и рисков (Bootstrap)

# Библиотеки:

- pandas, numpy, matplotlib, Bootstrap, train_test_split, StandardScaler, shuffle, GridSearchCV, cross_val_score, sklearn, MSE, RMSE

# Описание:

- Нужно решить, где бурить новую скважину. Есть данные пробы нефти в 3-ех регионах.

# Задача проекта:

- Постройте модель машинного обучения, которая поможет определить регион, где добыча принесёт наибольшую прибыль.

# Условия задачи:

- При разведке региона исследуют 500 точек, из которых с помощью машинного обучения выбирают 200 лучших для разработки.
- Бюджет на разработку скважин в регионе — 10 млрд рублей.
- При нынешних ценах один баррель сырья приносит 450 рублей дохода. Доход с каждой единицы продукта составляет 450 тыс. рублей, поскольку объём указан в тысячах баррелей.
- После оценки рисков нужно оставить лишь те регионы, в которых вероятность убытков меньше 2.5%. Среди них выбирают регион с наибольшей средней прибылью.

# Вывод по проекту:

- Мой выбор региона для разработки скважин это регион geo_1. Самым главный порогом для принятия решения является риск убытков. У geo_1 риск убытков соотвествует Т3, а значит получить шанс убытков в этом регионе самый маленький, что делает его победителем в выборах для разработки скважен. К тому же средненный доход и доверительный интервал выше чем у других, что говорит о том, что окупаемость и рентабельность этого региона нам подходит для лучше, чем остальные регионы и с большей долей вероятности она нам принесет прибыль, т.к. это единственный регион у которого судя по доверительному интервалу нет отрицательной прибыли.