# Project Panach: первый проект [Tayviscon IO](https://github.com/tayviscon-io)

## Начало работы
Мы стараемся держать [wiki](https://github.com/tayviscon-io/project-panach/wiki) нашего проекта в актуальном состоянии,
чтобы вы могли найти все необходимое для начала работы. Вы также можете начать с простого просмотра репозитория и поиска
интересующих вас вещей. В основных каталогах репозитория вы также найдете README.me файлы, а также в коде Javadoc,
которые помогут вам сориентироваться в данном проекте.
Проект и вся его документация разработаны с учётом идеи «самостоятельного исследования».

## Запуск проекта локально без Docker
Каждый микросервис является приложением Spring Boot и может быть запущен локально с помощью IDE или команды
`../mvnw spring-boot:run`. Обратите внимание, что есть вспомогательные сервисы
([Config Server](https://github.com/tayviscon-io/project-panach/tree/main/config-server)
и [Discovery Server](https://github.com/tayviscon-io/project-panach/tree/main/discovery-server)),
которые должны быть запущены до любого другого приложения.

[//]: # (После добавления серверов трассировки, сервера администратора, Grafana Prometheus добавить информацию о том,)

[//]: # (что их запуск необязателен.)

Если все прошло успешно, вы сможете получить доступ к следующим сервисам в указанных местах: 
* Config Server - http://localhost:8888 
* Discovery Server - http://localhost:8761

## Обзор проекта
Данный проект состоит их нескольких микросервисов:
* **[Config Server](https://github.com/tayviscon-io/project-panach/tree/main/config-server)**:
Централизованное управление конфигурациями для всех сервисов;
* **[Discovery Server](https://github.com/tayviscon-io/project-panach/tree/main/discovery-server)**:
Сервис обнаружения микросервисов, основанный на Eureka Server;