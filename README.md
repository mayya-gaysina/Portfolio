Проект " Телекоммуникации"
Описание проекта

Оператор связи «ТелеДом» хочет бороться с оттоком клиентов. Для этого его сотрудники начнут предлагать промокоды и специальные условия всем, кто планирует отказаться от услуг связи. Чтобы заранее находить таких пользователей, «ТелеДому» нужна модель, которая будет предсказывать, разорвёт ли абонент договор. Команда оператора собрала персональные данные о некоторых клиентах, информацию об их тарифах и услугах.

Оператор предоставляет два основных типа услуг:
 - Стационарную телефонную связь. Телефон можно подключить к нескольким линиям одновременно.
 - Интернет. Подключение может быть двух типов: через телефонную линию (DSL, от англ. digital subscriber line — «цифровая абонентская линия») или оптоволоконный кабель (Fiber optic).

Также доступны такие услуги:
 - Интернет-безопасность: антивирус (DeviceProtection) и блокировка небезопасных сайтов (OnlineSecurity);
 - Выделенная линия технической поддержки (TechSupport);
 - Облачное хранилище файлов для резервного копирования данных (OnlineBackup);
 - Стриминговое телевидение (StreamingTV) и каталог фильмов (StreamingMovies).

Клиенты могут платить за услуги каждый месяц или заключить договор на 1–2 года. Возможно оплатить счёт разными способами, а также получить электронный чек.

Описание данных

Данные состоят из нескольких файлов, полученных из разных источников:

 - contract_new.csv — информация о договоре;
 - personal_new.csv — персональные данные клиента;
 - internet_new.csv — информация об интернет-услугах;
 - phone_new.csv — информация об услугах телефонии.sv.

Задача:
- обучить на предоставленных выше данных модель для прогноза оттока клиентов. Основная метрика: AUC-ROC. Дополнительная метрика: Accuracy.Критерии оценки: AUC-ROC >= 0.85

Обучено несколько моделей (линейной регрессии, 2 модели деревьев и модель градиентного бустинга), лучшую метрику ROC AUC при кросс-валидации показала модель градиентного бустинга  CatBoostClassifier с гиперпараметрами (‘learning_rate': 1, 'max_depth': 3, 'n_estimators': 1000). На тестировании данная модель имеет значение метрики ROC AUC равное 0.91, что выше требуемого в 0.85. Также данная модель имеет достаточно высокое значение Accuracy  0.91(по умолчанию порог для отнесения к классам определен в 0.5). 

Также даны рекомендации заказчику.  
