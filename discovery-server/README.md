# Projcet Panach: Сервер обнаружения микросервисов, основанный на Eureka Server

Discovery сервер на основе
[Spring Cloud Netflix Eureka](https://cloud.spring.io/spring-cloud-netflix/reference/html/) - это сервер,
который управляет регистрацией и обнаружением микросервисов проекта Panach.

Данный сервис запускает на порту _8761_ и обеспечивает централизованное хранилище информации о доступных микросервисах,
регистрируемых в системе.

## Проблема

* В микросервисной архитектуре каждый сервис взаимодействует с другими сервисами.
Без централизованного механизма обнаружения сервисов необходимо было бы
вручную указывать их местоположение (IP-адреса и порты), что становится сложной задачей,
особенно в динамически масштабируемых средах;
* Если адреса сервисов изменяются (например, при автоматическом развертывании в облаке),
то все зависимые микросервисы должны обновлять свою конфигурацию,
что ведет к дополнительным трудозатратам и увеличивает вероятность ошибок.

## Решение

Централизованный сервер обнаружения (Discovery Server) помогает решить данную проблему,
предоставляя единое место для регистрации и поиска сервисов;
Вместо жесткого кодирования адресов микросервисы
могут динамически регистрироваться и находить друг друга через этот сервер.

## Принцип работы

* Сервер Discovery действует как реестр, в котором микросервисы регистрируются при запуске, указывая свое имя и адрес;
* Другие микросервисы могут запрашивать сервер Discovery, чтобы узнать, где находятся нужные им сервисы;
* Если микросервис становится недоступным, сервер автоматически исключает его из списка доступных сервисов;
* Это позволяет микросервисам динамически взаимодействовать друг с другом
без жесткой привязки к конкретным IP-адресам или портам.