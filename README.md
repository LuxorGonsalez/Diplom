# Дипломный проект по профессии «Тестировщик ПО»

Дипломный проект представляет собой автоматизацию тестирования комплексного сервиса, взаимодействующего с СУБД и API Банка.

---
## Документация
[План по автоматизации дипломного проекта](https://github.com/LuxorGonsalez/Diplom/blob/master/documentation/Plan.md)

[Отчёт о проведённом тестировании](https://github.com/LuxorGonsalez/Diplom/blob/master/documentation/Report.md)

[Отчёт о проведённой автоматизации](https://github.com/LuxorGonsalez/Diplom/blob/master/documentation/Summary.md)

---

## Описание приложения

### Бизнес часть

Приложение представляет из себя веб-сервис по покупку тура.

![](https://github.com/netology-code/qa-diploma/blob/master/pic/service.png)

Приложение предлагает купить тур по определённой цене с помощью двух способов:

1. Обычная оплата по дебетовой карте
2. Уникальная технология: выдача кредита по данным банковской карты

Само приложение не обрабатывает данные по картам, а пересылает их банковским сервисам:

* сервису платежей (далее - Payment Gate)
* кредитному сервису (далее - Credit Gate)

---
## Предварительные условия для запуска автотестов

1. Для запуска проекта и тестов на локальном компьютере потребуются установленные
   Git, JDK 11, IntelliJ IDEA, Docker
2. Запустить Docker Desktop.
3. Склонировать репозиторий на локальный компьютер командой в Git:

   ```
   git clone https://github.com/LuxorGonsalez/Diplom.git
   ```
4. Запустить IntelliJ IDEA и открыть проект.

---

### Запуск контейнеров

1. Запустить необходимые базы данных (MySQL и PostgreSQL), а также NodeJS. Параметры для запуска хранятся в файле `docker-compose.yml`. Для запуска необходимо ввести в терминале команду:
```
docker-compose up
```
2. В новой вкладке терминала ввести следующую команду в зависимости от базы данных:

`java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" -jar .\aqa-shop.jar
`   - для MySQL

`java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" -jar .\aqa-shop.jar
` - для PostgreSQL

## Примечание
Запуск приложения осуществляется на порту 8080. Для изменения, необходимо в файле `application.properties` изменить значение `server.port`

## Запуск тестов
В новой вкладке терминала ввести команду: `.\gradlew clean test`

## Перезапуск приложения и тестов
Если необходимо перезапустить приложение и/или тесты (например, для другой БД), необходимо выполнить остановку работы в запущенных ранее вкладках терминала, нажав в них Ctrl+С

## Формирование отчета AllureReport по результатам тестирования
В новой вкладке терминала или нажав двойной Ctrl ввести команду:
```
./gradlew allureServe
```
Сгенерированный отчет откроется в браузере автоматически. После просмотра и закрытия отчета можно остановить работу команды, нажав Ctrl+С, затем ввести букву Y и нажать Enter, либо закрыть вкладку терминала.