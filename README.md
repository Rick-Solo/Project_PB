# Задача

Создать телефонный справочник с возможностью импорта и экспорта данных в нескольких форматах. Под форматами понимаем структуру файлов, например, в файле на одной строке хранится одна часть записи, пустая строка - разделитель

Фамилия_1

Имя_1

Телефон_1

Описание_1

Фамилия_2

Имя_2

Телефон_2

Описание_2

и т.д.

В файле на одной строке хранится все записи, символ разделитель - *;*

Фамилия_1;Имя_1;Телефон_1;Описание_1

Фамилия_2;Имя_2;Телефон_2;Описание_2

и т.д.

# Решение
Структура проекта состоит из 4 модулей:
+ `User_interface`. Предоставляет пользователю возможность ввести данные для дальнейшого сохранения в телефонном справочнике. В данном модюле присутствует проверка на количество символов в номере телефона, и проверка на число.
Все четыре категории данных, а именно фамилия, имя, номер телефона и описание, сохраняются в списке `info`.
+ `CSV_creating`. Модуль создает файл `.csv` и записывает в него шапку таблицы.
+ `File_writing`. Содержит два метода для записи файла `csv` и `.txt`. В первом данные сохраняются через '*;*', во втором - через пустую строку части записи, и через две пустые строки целые записи.
+`Main`. Проверяет существует ли файл с расширением `.csv`. Если нет, то запускает модуль создания файла с шапкой таблицы. После этого вызываюся модуль записи, который в свою очередь забирает информацию из UI.