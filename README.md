# Карта упоминаний топонимов в двух жанрах российских песен второй половины 20-го века
На следующей карте отмечены топонимы, которые упоминаются в текстах двух случайно взятых представителей двух русских музыкальных жанров второй половины 20-го века – рок-песни и бардовской песни, Бориса Гребенщикова (синие точки) и Сергея Никитина (красные). Поскольку и в рок, и в бардовской песне были часты упоминания конкретных географических названий, было бы интересно посмотреть, различаются ли географическая территория охвата для этих двух довольно разных жанров и выявить корреляцию между набором свойственных жанру мотивов и тем и частотными топонимами.
Поскольку для данной задачи необходимо проанализировать большое количество текстов, была предпринята попытка автоматизировать этот процесс. На языке Python был написан скрипт, несовершенство которого легко заметить хотя бы по тому, что Вавилон на получившейся карте оказался отмечен где-то под Новороссийском, рядом с Маяковкой, которая не могла быть распознана машиной как станция метро и расположилась в одноименном селе Маяковка. Тем не менее, этот код (здесь он был опробован на двух авторах) позволил получить черновую карту, которую при условии долгой ручной обработки, которую пока произвести не удалось, можно было бы подвергнуть интерпретации.

В коде были представлены следующие этапы обработки данных:
1. Разметка всех имевшихся в библиотеке lib.ru текстов выбранных авторов при помощи парcера mystem 
2. Составление словаря топонимов – всех лексем, которым парсер присвоил тег “geo”
3. Сопоставление словаря с русскоязычной базой географических координат (именно здесь возникла проблема дезамбигуации, которая привела к выбору не самых очевидных из одноименных точек)
4. Генерация кода geojson

![Карта](https://polyatomson.github.io/kili_map1/map_bard_rock.geojson)
