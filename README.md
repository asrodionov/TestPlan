# План автоматизированного тестирования оформления накопительного счета «Накопилка»

## Перечень автоматизируемых сценариев

### Переход на страницу формы заявки

Сценарий:

1. На главной странице наводим мышь на пункт главного меню "Вклады", кликаем Накопилка
2. На странице Накопилка кликаем "Заполнить заявку"

Ожидаем: открывается форма оформления вклада

### Отправка формы с валидными данными

Сценарий

1. Заполняем поле имя : Андрей (или Анна-Мария или Родионов Андрей Cергеевич или Andrei)
2. Заполняем поле телефон : +79098768967 (или 89098768967 или 9098768967)
3. Устанавливаем чекбокс "Я согласен(а) на обработку персональных данных"
4. Кликаем на кнопку "Мы перезвоним"

Ожидаем: форма исчезает, появляется сообщение "Спасибо, скоро мы вам перезвоним!"

### Отправка формы с не валидными данными

Сценарий

1. Заполняем поле имя : 123 (или ?*%;№" или пустое поле или пробел)
2. Заполняем поле телефон : 123 (или пустое поле или пробел или абв или abc)
3. Устанавливаем чекбокс "Я согласен(а) на обработку персональных данных"
4. Кликаем на кнопку "Мы перезвоним"

Ожидаем: форма не исчезает, появляется уведомление о неправильном заполнении полей

Сценарий

1. Заполняем поле имя : Андрей 
2. Заполняем поле телефон : +79098768967
3. НЕ Устанавливаем чекбокс "Я согласен(а) на обработку персональных данных"
4. Кликаем на кнопку "Мы перезвоним"

Ожидаем: форма не исчезает, появляется уведомление о неправильном заполнении полей

### Открытие попапа "Персональные данные"

Сценарий

1. Кликаем ссылку "персональных данных"

Ожидаем: открывается попап с текстом о персональных данных.

## Перечень используемых инструментов

- Intellij IDEA

среда разработки, необходима для написание JAVA кода и unit тестов.

- Gradle 

Быстрое и удобное подключение зависимостей необходимых для тестирования

- Selenide

Необходим для автоматизированного взаимодействия с веб-страницами в ходе проведения тестирования 

- JUNIT

Модуль позволяющий запускать unit тесты и получать вердикты по ним.

## Перечень необходимых разрешений/данных/доступов от банка

- Получить разрешение от банка отправлять в базу тестовые заявки с определенной пометкой, например имя Тест (для игнорирования менеджерами).

Если этот вариант не возможен, то:

- Попросить развернуть сервис на тестовом сервере с ограниченным доступом (копия веб-приложения + копия СУБД).

## Перечень и описание возможных рисков при автоматизации

1. Изменение содержимого html страниц

Тк Selenide ищет элементы по css классам то при изменении элементов авто-тесты могут перестать выполняться.

2. Не получены разрешения на отправку в базу тестовых заявок либо нет возможности развернуть копию веб-сервиса

В данном случае выполнение тестирования будет не возможно

## Перечень необходимых специалистов для автоматизации

Backend-разработчик

Для переноса сервиса на тестовый сервер.


Тестировщик ПО

Для непосредственного проведения работ по автоматизированному тестированию



## Интервальная оценка с учётом рисков (в часах)


3 часа
