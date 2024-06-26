# Исследование сервиса аренды самокатов
 
В нашем распоряжении данные сервиса аренды самокатов GoFast. Имеются данные о некоторых пользователях из нескольких городов, а также об их поездках. Также имеются данные о типах тарифов при аренде самокатов. Чтобы совершать поездки по городу, пользователи сервиса GoFast пользуются мобильным приложением. Сервисом можно пользоваться:
без подписки или с подпиской Ultra, имеющих разные условия. Основная задача проекта заключается в анализе данных и проверке некоторых гипотез, которые могут помочь бизнесу вырасти.

# Цель исследования

Цель проекта заключается в анализе данных популярного сервиса аренды самокатов GoFast, а именно:

Проанализировать основную информацию о пользователях сервисом.
Определить основные характеристики поездок на тарифах с подпиской и без.
Определить помесячную выручку для каждого пользователя.
Проверить ряд гипотез для решения задачи увеличения количества пользователей с подпиской.

# Выводы

Мной было рассмотрено 3 датасета с информацией о пользователях сревисом проката самокатов, поездках и информацией о подписках. Проведена проверка на пропуски в данных для каждого датасета. Пропускив данных отсутствуют. Дата была приведена к необходимому формату. Добавлен отдельный столбец с указанием месяца аренды. Проведен поиск и удаление дубликатов. Неявные дубликаты в данных отсутствуют.

Мной проведена оценка частоты встречаемости городов. Определено примерно равное распределение пользователей по городам. Проведена оценка пользователей с подпиской и без. Пользователей без подписки больше всего приблизительно на 10%. Это говорит об активном использовании подписки. Проведена оценка возраста пользователей. Распределение возрастов соответствует нормальному. Средний возраст пользователя услугой составляет порядка 25 лет. Люди старше 35 лет и младше 15 арендой самокатов практически не пользуются. Это связано со спецификой данного транспорта, весом самоката и необходимостью иметь определенный уровень физической формы. Проведена оценка расстояния, преодолеваемого за одну поездку. Большинство поездок проходит в диапазоне от 2,5 до 3,5 км. Средняя поездка поездка на самокате составляет порядка 3 км. Длительность большинства поездок проходит в диапазоне от 14 до 22 минут. Средняя поездка поездка на самокате занимает порядка 18 минут. Для развития бизнеса можно предложить меры, анправленные на привлечение более старшей категории людей (от 35 до 50 лет).

Мной был создан новый датафрейм с агрегированными данными на основе датафрейма с объединенными данными. Были найдены суммарное расстояние, количество поездок и суммарное время для каждого пользователя за каждый месяц. Также добавлен столбец с помесячной выручкой, которую принес каждый пользователь.

Проведена проверка гипотез о том тратят ли пользователи с подпиской больше времени на поездки, которая показала, что пользователи с подпиской используют самокат немного дольше, но это время незначительно и составляет чуть более минуты. Возможно внедрение каких-то скидок за длительное пользование самокатом, для того чтобы повысить среднее время использования. Проведена проверка гипотезы, что пользователи с подпиской проезжают расстояние, не превышающее 3130 метров за одну поездку. По результатам проверки мы не можем утверждать, что расстояние, которое проехали пользователи на тарифе ultra не превышает 3130 метров. В среднем пройденное расстояние находится в районе этого показателя. Если мы хотим увеличить время пользования услугой, то мы должны понимать, что пройденное расстояние тоже может увеличиваться. Это приведет к снижению ресурса самокатов. Как одно из решений - снижение максимальной скорости езды самоката. Это приведет к снижению травматичности, но также увеличит ресурс оборудования. Проведена проверка гипотезы, что выручка с пользователей на подписке ultra превышает выручку с пользователей на подписке free, которая подтвердилась. В среднем выручка с пользователей с подпиской на 10% выше, что говорит о необходимости повышать их долю в общем числе клиентов. Для этого необходимо проведение акций на подписку, возможно включение пробного периода пользования при подписке на другие сервисы компании и т.д. Определен метод для оценки изменения обращений в службу поддержки после замены сервера Метод, который нужно использовать при сравнении: scipy.stats.ttest_rel().

В общем, анализ сервиса проката самокатов показал, что он пользуется спросом в во всех представленных локациях. Сервис приности прибыль. Для его дальнейшего развития необходимо уделить особое внимание привлечению людей к приобретению подписки на данный сервис, так как она приносит дополнительный доход.
