# Определение стоимости автомобилей
Сервис по продаже автомобилей с пробегом «Не бит, не крашен» разрабатывает приложение для привлечения новых клиентов. В нём можно быстро узнать рыночную стоимость своего автомобиля. В вашем распоряжении исторические данные: технические характеристики, комплектации и цены автомобилей. Вам нужно построить модель для определения стоимости. 

Заказчику важны:

- качество предсказания;
- скорость предсказания;
- время обучения.

В нашем распоряжении данные о технических характреристиках автомобилей и их стоимости. Имеются данные о модели автомобиля, годе выпуска, типе кузова и т.д.. Чтобы привлечь клиентов, компания разрабатывает приложение, позволяющее на основе основных данных об автомобиле, предсказать его рыночную стоимость.

# Цель исследования
 
Цель проекта заключается в разаработке наилучшей модели предсказания стоимости автомобилей, а именно:
1. Проанализировать основную информацию об автомобилях из базы данных.
2. Подготовить данные для обучения моделей.
3. Обучить разные модели и сравнить их быстродействие и качество моделей.
4. Выбрать лучшую модель и проверить ее на тестовой выборке.

# Выводы

Мной был проведен исследовательский анализ данных, который включал в себя:

- изучение данных;

- удаление явные дубликатов;

- исключение неинформативных признаков;

- исследование данных после первоначальной предобработки;

- обработку аномалий (например удаление строк с минимальной стоимостью автомобиля или годом регистрации раньше 1930 года);

- обработку пропущенных значений;

- удаление дубликатов.

Я установил, что цена зависит от основных признаков, причем высокие показатели года регистрации и мощности увеличивают цену, а пробег и наличие ремонта ее снижают.

Провел обучение 5 видов моделей (Линейная регрессия, дерево решений, случайный лес, CatBoost, LGBMRegressor). На данном этапе было выяснено какую метрику RMSE выдают модели предсказаний и их лучшие параметры. 

Далее модели с полученными ранее гиперпараметрами я проверил на тестовой выборке.

Лучшая с точки зрения качества предсказания - модель LGBMRegressor.

Наименьшее время обучения - модель DecisionTreeRegressor.

Наменьшее время предсказания - модель DecisionTreeRegressor.

В целом я рекомендую принять за основную модель LGBMRegressor, так как она обладает наилучшей точностью, но нужно учитывать, что эта модель требует времени на обучение и предсказание результатов.
