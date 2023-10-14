# wc_server
Water Counter server )

ESP32 собирет показания со счетчиков воды и автоматически отправляет их в МОСОБЛЕИРЦ
Мониторинг и управление процессом осуществляется через телеграм бот.

Функции
- Считает импульсы от приборов учета оснащенных герконом
- Счетчики хранятся во внутреннем Flash (библиотека Preferences)
- Подключается к одной из доступных WiFi сетей (библиотека WiFiMulti)
- Оснащен telegram ботом (библитека FastBot)
- Подключается к сайту mosoblerc.ru и забирает оттуда текущие данные о ваших счетчиках
    - id приборов
    - ранее переданные показания
    - дата плановой поверки
    - даты когда можно подавать показания
- Время синхронизирует по NTP
- В нужный день месяца отправляет показания в мособлеирц
- Не передает показания если значения превысили месячный лимит
- За три месяца до срока поверки начинает слать напоминания
- начальные значения счетчиков выставляются через telegram

# Подготовка
Чтобы настроить программу, нужно отредактировать файл wc_server.ino
Все строки которые там нужно отредактировать помечены фразой //Edit me

