Основная функциональность Postman - возможность создания и отправки запросов к API для проверки его функциональности и получения данных. Для этого не потребуется писать код или команды в терминале. В интерфейсе Postman вы создаете запрос, нажимаете кнопку отправить и получаете ответ от API. API расшифровывается как Application Programming Interface или программный интерфейс приложения. С его помощью мы можем  получить доступ к возможностям другого приложения и обмениваться с ним данными. Такое приложение называется API сервером. Отправка запросов и получение ответов происходит через интернет с помощью протокола HTTP. Приложение, которое отправляет запрос, называется клиентом. Это может быть мобильное приложение, web сайт или другой сервис.

Запрос всегда содержит URL вызываемого эндпоинта API и HTTP метод запроса. Наиболее часто используются следующие методы:

- **POST** - для добавления новых данных
- **GET** - для чтения данных
- **PUT** - для обновления данных
- **PATCH** - для частичного обновления данных
- **DELETE** - для удаления данных

Давайте попробуем отправить первый запрос. Это будет GET запрос из демонстрационного API Postman. Выглядит он следующим образом:

`GET`	https://postman-echo.com/get
Для отправки в Postman выбираем метод GET. Копируем адрес нашего эндпоинта и нажимаем кнопку Send. В результате получаем ответ содержащий данные в виде json объекта.

Здесь мы можем увидеть тело ответа (**Body**), который мы получили от сервера. Postman автоматически распознает формат JSON и форматирует его, для лучшего восприятия. Помимо Body, мы можем посмотреть куки (**Cookies**) и заголовки (**Headers**) ответа, нажав на соответствующие ссылки. Также мы видим, что наш запрос выполнился успешно и в ответе мы получили код ответа **200 OK**. На выполнение запроса ушло **148мс**.
