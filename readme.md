# Stationmapper

Библиотека для базовых операций с картами автобусных остановок.

### Основные функции

* Загрузка и сохранение фрагментов карт в виде изображений в формате BMP.
* Загрузка списков автобусных остановок.
* Нанесение географических точек (автобусных остановок и не только) на изображение карты.
* Поиск ближайших остановок.

### Сборка и запуск

Сборка библиотеки:

```
make libstationmapper.so
```

Сборка примера:

```
make example
```

### Входные и выходные данные

Библиотека работает с изображениями карт в формате BMP.

Изображение карты привязывается к географическим координатам по двум противоположным углам. Библиотека предназначена для обработки небольших фрагментов карты. Поэтому на масштабах карты координатную сетку можно считать прямоугольной. Координаты (широта и долгота) для привзяки изображения к координатам передаются через конфигурационный CSV-файл. Первая строка - заголовки, вторая - координаты углов. Разделитель - запятая. Пример:

```
top left latitude, top left longitude, bottom right latitude, bottom right longitude
55.665193184436, 37.2216796875, 55.627995954267, 37.3095703125
```

Библиотека обрабатывает списки остановок, в формате CSV.

Формат:

```
id остановки,Название,Широта,Долгота
```

Первая строка - заголовки. Разделитель - запятая.

Пример:

```
Station Id,Station name,latitude,longitude
102,27y km Minskogo shosse,55.65117899,37.267036
```

Примеры входных данных находятся в директории `data`.

Дополнительные карты можно генерировать с помощью сайта BigMap: http://bigmap.osmz.ru

Данные об остановках можно получить с портала открытых данных: https://data.gov.ru/opendata/5047042291-stops-registry

### Зависимости

Для работы с BMP используется библиотека LoadBMP: https://github.com/vallentin/LoadBMP

