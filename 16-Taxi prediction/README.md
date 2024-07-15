#  Прогнозирование заказов такси

Компания «Чётенькое такси» собрала исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. Постройте модель для такого предсказания.

# Цель исследования
 
Цель проекта заключается в разработке модель, которая на основании исторических данных сможет спрогнозировать количество заказов такси в аэропорту на следующий час. 

# Основные выводы

Были загружены данные с начала марта 2018 по конец августа. Данные были проверены на пропуски и монотонность. Пропуски отсутствуют, данные расположены в хронологическом порядке. Исходный датасет был перегруппирован: новый временной интервал 1 час. Все объекты за этот период были объединены и заказы просуммированы. Дубликаты и пропуски данных - отсутствовали. Хронологичный порядок соблюден в течение всего периода: 1 марта 2018 - 31 августа 2018. И

Анализ данных. Тренды, помимо пульсаций, имеют прослеживаемый линейный рост. Сезонность имеет одинаковую повторяемость: суточную, недельную и месячную, но в слабо выраженная. Определили дневную сезонность - максимальная загрузка в понедельник, минимальная загрузка - суббота, очен хороший спрос в пятницу. Определили суточную сезонность - максимальная загрузка в районе 00:00, спад до ~06:00 (минимальная загрузка), с дальнейшем не плавным ростом до 00:00. Про месячную сезонность - нельзя ничего говорить, данные не за полный год. Определили тренд - рост с каждым месяцем. Но данные не полные, рост может быть связан с временем года.

Это позволило определить перечень признаков и их размеры:

сдвиг (количество заказов за 2 предыдущих часов);

скользящее среднее (среднее количество заказов за 3 ближайших часа);

месяц;

день месяца;

день недели;

час.

Получившаяся выборка относительно небольшая и для подбора гиперпараметров моделей использовалась кросс вылидация, с учётом хронологического порядка. Были обучены четыре модели:

Линейная регрессия (Linear Regression);

Случайный лес (Random Forest Regressor);

Модель градиентный бустинг (Light GBM), которая показала себя лучшей;

Модель CatBoost.

Результат на тестовой выборке: время обучения 3 мс. и предсказания 30 мс., RMSE: 43. Большую часть временного ряда получается предсказать, за исключение выбросов. Приведенный в работе график иллюстритрует, что прогнозируемые значения коррелируют с фактичесими, значит модель адекватна и может быть использована в работе.