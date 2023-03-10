В этом репозитории предложены задания курса по Фотограмметрии для студентов МКН/ИТМО/ВШЭ.

[Остальные задания](https://github.com/PhotogrammetryCourse/PhotogrammetryTasks2023/).

# Задание 1. Локальные ключевые точки SIFT (детектор и дескриптор)

[![Build Status](https://github.com/PhotogrammetryCourse/PhotogrammetryTasks2023/actions/workflows/cmake.yml/badge.svg?branch=task01&event=push)](https://github.com/PhotogrammetryCourse/PhotogrammetryTasks2023/actions/workflows/cmake.yml)

0. Сделать fork проекта (обратите внимание что задание не в ветке **master**, а в ветке **task01**)
1. [Установите OpenCV 4.5.1](https://github.com/PhotogrammetryCourse/PhotogrammetryTasks2023/blob/task01/CMakeLists.txt#L19-L31)
2. Выполнить задания ниже (не используйте пожалуйста C++ из будущего о котором не знает GCC 5.5 - именно он будет использоваться при тестировании в Github Actions CI, ориентируйтесь на C++11)
3. Отправить **Pull-request** с названием```Task01 <Имя> <Фамилия> <Аффиляция>```:

 - Скопируйте в описание [шаблон](https://raw.githubusercontent.com/PhotogrammetryCourse/PhotogrammetryTasks2023/task01/.github/pull_request_template.md)
 - Обязательно отправляйте PR из вашей ветки **task01** (вашего форка) в ветку **task01** (основного репозитория)
 - Перечислите свои мысли по вопросам поднятым в коде и просто появившиеся в процессе выполнения задания (выписывайте их с самого начала в отдельный текстовый файл, в шаблоне предложены некоторые вопросы)
 - Создайте PR
 - Затем дождавшись отработку Github Actions CI (около 15 минут) - скопируйте в описание PR вывод исполнения вашей программы **на CI** (через редактирование описания PR)

**Мягкий дедлайн**: начало лекции 22 февраля. Мягкий дедлайн - ориентировочная рекомендация "здорово если успеете".

**Жесткий дедлайн**: начало лекции 1 марта. Жесткий дедлайн - предполагается что все в него укладываются. Не доделали - зашлите хотя бы что-то. После дедлайна досылать тоже можно (но будет небольшой штраф в баллах).

Задание 1.0.
=========

Ознакомьтесь со структурой проекта:

1. ```src/phg/sift/``` - основная часть где вы будете реализовывать алгоритм

2. ```tests/test_sift.cpp``` - тесты которые будут прогонять ваш алгоритм на каких-то относительно простых манипуляциях с маленькой картинкой, если вам хочется добавить другие сценарии тестирования (возможно с другими метриками) - здорово!

3. ```data/src``` - исходные данные используемые при тестировании (к ним используются относительные пути, поэтому нужно выставить Working directory = путь к проекту)

4. ```data/debug/test_sift/SIFT``` - сюда тесты сохранят картинки с визуализацией результата

5. ```data/debug/test_sift/debug``` - сюда вам предлагается сохранять любые промежуточные картинки-визуализации, это очень полезно для отладки, оценки качества, уверенности и в целом один из немногих способов качественно "заглянуть в черную коробку"

Задание 1.1.
=========

1. Убедитесь что у вас все компилируется и тесты проходят.

2. Ознакомьтесь с тем как проводится тестирование - ```tests/test_sift.cpp```:

3. Обратите внимание что там сравнивается ORB и SIFT реализованные в OpenCV

4. Посмотрите и сравните результаты этих двух дескрипторов:

 - по логам в т.ч. пишущим угол поворота, перепад масштаба и расстояние между дескрипторами)
 - по картинкам с результатами в папке ```data/debug/test_sift/SIFT```

Задание 1.2.
=========

Включите тестирование вашего SIFT - см. **TODO** в ```test/test_sift.cpp```

Реализуйте SIFT в ```src/phg/sift/sift.cpp```:

 - Либо с чистого листа самостоятельно - просто удалите оттуда весь код (тогда если все хорошо - **10 баллов**)
 - Либо выполняя **TODO** один за другим (через Ctrl+F сверху вниз) (тогда если все хорошо - **8 баллов**)
 - Либо выполняя **TODO** один за другим, а если на каких-то отдельных этапах вы хотите сделать больше самостоятельно - смело удаляйте окружающий код заготовки :) (тоже если все хорошо - **8 баллов**)
