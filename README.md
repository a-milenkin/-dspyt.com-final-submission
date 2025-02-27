# RaifHack solution [dspyt.com]

### Описание

1. Обучение на данных price_type=1
2. Чистка данных (floor, categorical columns)
3. 10 фолдов
4. Предикт домножаем на 0.94
5. Ансамбль LGBMRegressor (0.75) + XGBRegressor (0.05) + CatBoostRegressor (0.2)
6. Публичный лидерборд - 1.4062123483345823

Файл работы - <code>raifhack-dspyt-com-final-solution.ipynb</code>
Файл для отправки - <code>submission_final_raif</code>

### Запуск
<ol>
    <li> убедиться, что у вас стоит python3.6 или выше </li>
    <li> установить зависимости:
    
    pip install -r requirements.txt 
</li>
    <li> запустить обучение, предикт
        Обучение и предсказание моделей происходит в ноутбуке <code>raifhack-dspyt-com-final-solution.ipynb</code>
</li>
    <li> загрузить полученные результаты в систему</li>
</ol>

### Анализ

1. Пробовалось агрегировать фичи, но это не дало результат.
2. В колонке city хранятся данные не только о городах, но и о улицах, районах, станциях метро.
3. Очищение колонки floor дало наиболее ощутимый результат.
4. Кросс валидация улучшает результат в среднем на 0.02
5. Пробовались разные варианты ансамблирования, оптимальный представлен в описании (п.5).
6. Пост процессинг, для удаления выбросов умножаем предикты соло моделей на 0.9, финального на 0.94.

Распределение недвижимости по России:

![dist_of_estate](https://github.com/RadmirZ/-dspyt.com-final-submission/blob/main/dist_of_estate.PNG?raw=true)

Распределение цен:

![dist](https://github.com/RadmirZ/-dspyt.com-final-submission/blob/main/distribution.PNG?raw=true)

Распределение расстояние недвижимости до центра города:

![dist_city](https://github.com/RadmirZ/-dspyt.com-final-submission/blob/main/%D1%80%D0%B0%D1%81%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5_%D1%80%D0%B0%D1%81%D1%81%D1%82%D0%BE%D1%8F%D0%BD%D0%B8%D1%8F.PNG?raw=true)

Распределение площади недвижимости:

![dist_sq](https://github.com/RadmirZ/-dspyt.com-final-submission/blob/main/%D1%80%D0%B0%D1%81%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%BF%D0%BB%D0%BE%D1%89%D0%B0%D0%B4%D0%B8.PNG?raw=true)

Важность дефолтных фич:

![feature_importances](https://github.com/RadmirZ/-dspyt.com-final-submission/blob/main/feature_importances.PNG?raw=true)


## Идеи по улучшению:

1. Ипользовать TabNet или AutoML
2. Генерация гео-факторов
3. Добавление временных дополнительных данных таких каких инфляция/прогноз инфляции
4. Кластеризация по местоположению
5. Попробовать другие кросс-валидационные функции: GroupKFold, TimeSeriesSplit
6. Псевдолейбелинг



[dspyt.com](https://dspyt.com/ru/)

