# Отчёт о проведённой автоматизации

## 1. Что было сделано

В результате работы над дипломным проектом были выполнены следующие задачи:

1. Автоматизированы позитивные и негативные тестовые сценарии покупки тура через UI
  ("Оплата по карте" и "Кредит по данным карты");
2. Протестирована работа сервиса на двух СУБД (MySQL и PostgreSQL), а так же
   параметризован запуск SUT и тестов для указанных БД;
3. Сгенерирован отчет о проведенном тестировании в Allure Report.

## 2. Не было выполнено по определённым причинам

Остутствует интеграция с системой CI по причине нехватки времени.

## 3. Выявленные проблемы

В процессе автоматизации тестирования были выявлены следующие проблемы:

- В следствие отсутствия уникальных идентификаторов для элементов страниц (id) были сложности с выбором правильных селекторов;
- Проверка правильности работы автоматизированных тестов вручную и исключение «ложных» падений по причине наличия значительного числа дефектов в сервисе потребовали дополнительного времени для анализа;
- Отсутствие подробной документации к сервису;

## 4. Общий итог по временным затратам


**Итого запланировано:** 100 часов

**Итого потрачено:** 120 часов