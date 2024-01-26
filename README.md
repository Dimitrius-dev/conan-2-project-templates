# Conan template
___
#### Проект-справка для наглядного использования пакетного менеджера Conan 2.0 в c/c++ проектах.
___
Оффициальная справка: https://docs.conan.io/2/
___
### Описание
В общих чертах данный пакетный менеджер сильно похож по функционалу на пакетный менеджер Maven для языка Java.

### Установка conan
```
pip install conan
```

Все строится на репозиториях с пакетами. Каждый пакет - библиотека.
Репозитории бывают двух типов:
+ Локальные (клиентский - local cache)
+ Удаленные (оффициальный - conancenter, свой - custom_server(https://docs.conan.io/2/reference/config_files/remotes.html) )

Локальный существует на любом устройстве, которое создает и использует пакеты.  
Удаленные лишь хранят множество пакетов, которые можно получить на локальные.

Иерархия данных
```
+--+-библиотека example 0.0.1 (версия библиотеки)
|  |
|  +--+-ревизия #1 (ревизия библиотеки)
|  |  |
|  |  +--пакет #1 (сборка библиотеки)
|  |  +--пакет #2 (сборка библиотеки)
|  |
|  +--+-ревизия #2 . . .
|     | . . .
|
+--+-библиотека example 0.0.2 (версия библиотеки)
   | . . .
```
Сначала требуется создать ```profile``` - файл профиль, который будет определять
характеристики нашей системы для сборки и использования пакетов.  
Профиль определяет пользователь, его содержимое никак не проверяется на соответствие реальной системы.

Автоматически создать профиль
```
conan profile detect --force
```
Получить путь к профилю ```default```
```
conan profile path default
```
Шаблоны создания и использования библиотеки:
+ [Создание библиотеки](./build-lib-project/README.md)
+ [Использование библиотеки](./build-executable-project/README.md)
+ [Сервер библиотек](./conan-server/README.md)