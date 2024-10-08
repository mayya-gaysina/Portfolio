# Проект "Прогнозирование заказов такси"

Компания «Чётенькое такси» собрала исторические данные о заказах такси в аэропортах. Чтобы привлекать больше водителей в период пиковой нагрузки, нужно спрогнозировать количество заказов такси на следующий час. 

Задача:
 - Построить модель для предсказания количества заказов такси на следующий час. Значение метрики RMSE на тестовой выборке должно быть не больше 48.
Вам нужно:

Структура выполнения:
 - загрузка данных и их ресемплирование по одному часу.
 - анализ данных,
 - обучение разных модели с различными гиперпараметрами (размер тестовой выборки определен размером 10% от исходных данных).
 - проверка данных на тестовой выборке и формирование выводов.

Данные лежат в файле taxi.csv. Количество заказов находится в столбце num_orders (от англ. number of orders, «число заказов»).

Для решения задачи выбрана модель бустинга LGBMRegressor (на тестовых данных показала значение метрики RMSE=40):
 - рассмотрено несколько линейных моделей (с регуляризацией и без), дерево решений и модель бустинга. Для каждой модели подобраны такие гиперпараметры, при которых метрика MSE, а соответственно RMSE будет меньше,
 - с небольшим отрывом лучшую метрику RMSE при кросс-валидации показала модель бустинга LGBMRegressor.
 - значение метрики модели бустинга LGBMRegressor на тестовой выборке составило 40, что соответствует необходимому,
 - при сопоставлении фактических и предсказанных выбранной моделью значений, выявлено, что модель достаточно точно определяет ежедневно повторяющиеся тестовые данные, но редкие пики в данных предсказать не может.
