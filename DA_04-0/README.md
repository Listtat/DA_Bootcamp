# Проект 04

Основные понятия математической статистики. 

## Cодержание

1. [Chapter I](#chapter-i) \
    1.1. [Основные понятия в математической статистики](#основные-понятия-в-математической-статистики) 
2. [Chapter II](#chapter-ii) \
    2.1. [Общая инструкция](#общая-инструкция) 
3. [Chapter III](#chapter-iii) \
    3.1. [Задание](#задание) \
    3.2. [*Дополнительное задание](#дополнительное-задание)  
4. [Chapter IV](#chapter-iv)\
    4.1 [Сдача работы и проверка](#сдача-работы-и-проверка) 


<h2 id="chapter-i">Chapter I</h2> 
<h3 id="основные-понятия-в-математической-статистики">Основные понятия в математической статистики</h3>

В этом проекте мы познакомимся с основными понятиями математической статистики, научимся их вычислять и еще не раз будем этим пользоваться в будущих проектах.

Для многих статистика кажется чем-то странным, сложным и далеким. Но мы пользуемся статистикой на ежедневной основе. Даже когда используем в речи “обычно” или “как правило”, мы подразумеваем какую-то среднюю величину, которую привыкли наблюдать чаще всего. И понимаем, что существуют отклонения от этой средней величины в ту или иную сторону. Например, каждое утро ты пьешь кофе с молоком и без сахара, но раз в месяц можешь добавить карамельный сироп, или вообще выбрать зеленый чай. У отклонений так же есть норма (карамельный сироп каждый третий четверг месяца), но если ты вдруг вообще решил выпить просто молока - это можно считать за аномалию.

Так и для больших чисел, с которыми работает статистика - мы анализируем явления, пытаемся понять их нормальность или аномальность, сравнивая с историческими данными.

Представим, что ты занимаешься ботаникой. И исследуешь разновидности Ириса: Ирис щетинистый (Iris setosa), Ирис виргинский (Iris virginica) и Ирис разноцветный (Iris versicolor). Действительно ли эти растения настолько разные, что их стоит разделять?

<img src="https://lh6.googleusercontent.com/8_Dl3d92Ec8tVp5Sg7jdDfiq1Tn7cQIl178Y8WTRqm3udWqNEM4mS0Eis468-EJzHwsDhGLFIiWzsbAuMjBC-u4Mg1cFlZLUC5u_hq4dSknaQi2SMb-1tbG_bEIY2hLNPpuSTsFmetApNrxQDAaOXv9aWbDbwwfnyoksEVCJNplGps-QHsTIwDF06nNoew" width=50% height=50% >


Повторим некоторые измерения за американским ботаником Эдгаром Андерсеном. Он взял по 50 экземпляров каждого вида, всего 150 растений. Для каждого экземпляра измерялись четыре характеристики (в сантиметрах):

1. Длина наружной доли [околоцветника](https://ru.wikipedia.org/wiki/%D0%9E%D0%BA%D0%BE%D0%BB%D0%BE%D1%86%D0%B2%D0%B5%D1%82%D0%BD%D0%B8%D0%BA) (англ. sepal length);
2. Ширина наружной доли околоцветника (англ. sepal width);
3. Длина внутренней доли околоцветника (англ. petal length);
4. Ширина внутренней доли околоцветника (англ. petal width).

Итоговый набор данных выглядит следующим образом:

<img src="https://lh5.googleusercontent.com/AzwER2VypUiUDERV5qz9ZwFCWEcDSa0fAwO0JQYMQt3dDYc_jbmEkWK7LKpqcBD8AUKa2gnHxrznlTgpY3yu-2U-jPENQw1TVNEh2hOCfxuT8KhuQ-LrOYib0gXKbZKFlwr9YHJOuj1tow7_EJAZyp_-xD32H7Myc-EUOYqFwvLM_4Kahf1-8VtYvOicqg" width=30% height=30% >


С подобными табличными данными мы и работали ранее. 

Ранее упоминалось, что в наборе данных 150 растений. Можем ли мы делать выводы, основываясь только на этих растениях? На планете их в тысячи раз больше, может надо измерить все? Так мы подходим к некоторым основным понятиям математической статистики.

**Генеральной совокупностью** называется всякая большая (конечная или бесконечная) коллекция или совокупность предметов, которые мы хотим исследовать. 

**Выборка** — это часть или подмножество совокупности. Выборка называется **репрезентативной** если она адекватно отражает свойства генеральной совокупности.

Соответственно в нашем примере все ирисы на планете - генеральная совокупность, а для исследования использовалась выборка из 150 растений. 

Существует много методов формирования выборки, чтобы достичь репрезентативности. В этот момент мы можем столкнуться с когнитивными искажениями: например, не учесть влияние факторов, про которые не знаем. 

При работе с измерениями надо всегда иметь в виду, что мы никогда не сможем получить абсолютно идентичные величины. У каждой линейки есть своя погрешность, две разные линейки изготовили на разных предприятиях, мы проводили измерение в разное время дня, когда было разное освещение в помещении и т.д. Учитывая все эти факторы, мы не постоянно будем попадать куда-то около реальной величины нашего объекта. Мы попадем в истинное значение только с какой-то вероятностью, само измерение можно считать случайным. 

Важнейшее значение в теории вероятностей и в её приложениях имеет группа теорем, объединяемых обычно под названием «закон больших чисел» или предельных теорем. Не прибегая к строгим формулировкам, можно сказать, например, что при некоторых слабых условиях среднее значение независимых одинаково распределенных случайных величин стремится к их математическому ожиданию при достаточно большом количестве этих случайных величин. Если в качестве совокупности случайных величин рассматривать независимые наблюдения одной и той же случайной величины, то это означает, что среднее по выборочным наблюдениям должно стремиться к истинному (неизвестному) математическому ожиданию этой случайной величины. Это закон больших чисел в форме Чебышёва. Это даёт основу для получения соответствующих оценок.

Если мы попробуем все наши измерения нарисовать (построить гистограмму), то увидим распределение. Распределения могут быть разными: 

<img src="https://lh5.googleusercontent.com/WPOC3UHewD_W4TZvuaUmB0NwJZL7C9mcJTLLQST5yTBD8Q24NNOYA7S3xNRIC-7hYBt06dXYRLtbcycdgptBf-acbOoOnerCzaJMN5DppldnBtSwQGxjwPj81UtBqjAknREhlIlHZ4m0xj7swzxTvJm1jcuC9jynLeIAvTJpyw9OHeFhlAzAFFp_TTLSTw" width=30% height=30% >


Например, рост человека описывается нормальным распределением (не так много очень низких людей и очень высоких), а сумма на банковском счете может быть описана логномальным распределением (достаточно много счетов с минимальной суммой и не так много с очень крупными суммами). 

Когда мы говорим о распределении, и, самое главное, пытаемся два распределения сравнивать друг с другом и искать отличия или аномалии, то очень важно уметь вычислять его показатели: 

<img src="https://lh6.googleusercontent.com/HOiUtfKInWB4TcqezMctoXQ-9u4eM7NrhbhrfxWt0ECPPPl-I2HsB1_12LItOZD_nAWzpbzF8ZkRLt59tfyo9QmRJCa1HgzfV9GJUu03LFxoMvki4Mqk2XhKfDWhZGHyBWu2ypd7FYaR3wQl-LL7OTS-HBb9S7aqJBxxThYCTHA5pECLjJrBIWOTYMmmXQ" width=30% height=30% >


Помимо этого, к данной категории принято относить так называемые экстремумы: максимум и минимум (минимальное и максимальное значение) выборки.

Для решения практических задач широко распространена стандартизация распределения. Цель — преобразовать исходный набор в новый со средним значением равным 0 и стандартным отклонением равным 1. 

Например, мы хотим выяснить, какую информацию человеческий мозг лучше запоминает: текст или картинки? Для начала давай посмотрим отличаются ли показатели запоминаемости вообще. 

Для этого мы провели измерения, где одной группе людей показывали текст, другой инфографику и потом просили пройти тест, за который человек получал оценку от 0 до 1000. Такие результаты у нас получились:

<img src="https://lh3.googleusercontent.com/f_3Z0g65QrUjiPPtHtbu1j0o8wlraj3A8444mw8w4LbWxKDBSbGR34CSSlo0BuKXWptiqrvfPcRFW8V18qhWgbABottzwdIZxXZmUOCUWYwRMd2Yk73ItfZq4c6Hlzt6DrrLODXTp6HnJaOlhRQ03dg5PxX3e_T0b-9ub8BVwMC_cCUSLr6eARQ5W9U8" width=30% height=30% >

Как мы видим, у нас действительно данные сосредоточены вокруг средних, и большинство значений лежит в пределах 500 баллов.

Да и без графиков понятно, что среднее 600 больше, чем 480. Можем ли мы сделать вывод о том, что картинки запоминаются лучше текста? К сожалению, нет. Никто не отменял случайность. Для того, чтобы смело сделать выводы о преимуществах картинок перед текстами, необходимо уметь вычислять p-value и z-score.

Чтобы избежать самых распространенных заблуждений, связанных с вероятностью, не забывай о следующем:

- вероятность неэффективна для предсказания краткосрочного поведения. Она эффективна в случае с долгосрочными моделями;
- если возможны всего два исхода, то совсем не обязательно, что у каждого из них 50% шансов произойти;
- если где-то наблюдается целый ряд редких событий, то это могло произойти просто случайно. Редкие события обязательно произойдут с кем-то, где-то, когда-то;
- нельзя считать себя удачливым только потому, что процесс повторяется снова и снова при заданных условиях (как в случае с азартными играми). У вероятности нет памяти.


<h2 id="chapter-ii">Chapter II</h2> 
<h3 id="общая-инструкция">Общая инструкция</h3>

Методология Школы 21 может быть не похожа на тот образовательный опыт, который случался с тобой ранее. Её отличает высокий уровень автономии: у тебя есть задача, ты должен её выполнить. По большей части тебе нужно будет самому добывать знания для её решения. Второй важный момент — это peer-to-peer обучение. В образовательном процессе нет менторов и экспертов, перед которыми ты защищаешь свой результат. Ты это делаешь перед таким же учащимися, как и ты сам. У них есть чек-лист, который поможет им качественно выполнить приемку вашей работы.

Роль Школы 21 заключается в том, чтобы обеспечить через последовательность заданий и оптимальный уровень поддержки такую траекторию обучения, при которой ты не только освоишь hard skills, но и научишься самообучаться.

- Не доверяй слухам и предположениям о том, как должно быть оформлено ваше решение. Этот документ является единственным источником, к которому стоит обращаться по большинству вопросов;
- твое решение будет оцениваться другими учащимися;
- подлежат оцениванию только те файлы, которые ты выложил в GIT (ветка develop, папка src);
- в твоей папке не должно быть лишних файлов — только те, что были указаны в задании;
- не забывай, что у вас есть доступ к интернету и поисковым системам;
- обсуждение заданий можно вести и в Slack;
- будь внимателен к примерам, указанным в этом документе — они могут иметь важные детали, которые не были оговорены другим способом;
- и да пребудет с тобой Сила!


<h2 id="chapter-ii">Chapter III. Практика</h2> 

Периодически для решения некоторых задач возникает необходимость подготовить данные и провести необходимые вычисления до визуализации в конкретной BI-системе. В первой части проекта мы научимся использовать математические формулы и строить графики в Excel. Во второй части проекта проекта - проведем мини-исследование и составим портрет пользователя.

В папке src ты найдешь excel-файл, в котором содержится статистика о количестве установок мобильного приложения банка N за каждый месяц с 2017 года до лета 2022 года.

Мы знаем что установок год к году становится меньше, тренд на снижение, но в мае 2022 года было резкое падение. Некоторые связывают его с обычным спадом интереса в период отпусков. Необходимо проверить, так ли это.

<h3 id="задание">Задание</h3>

В первой части проекта мы будем выполнять упражнение в excel-файле da_project04_empty.xlsx из папки src. Вычислительная часть упражения выполняется каждым участником команды индивидуально, сбор и валидация ответов - в команде.

1. Заполни столбец “Месяц - Год”, используя формулу из ячейки C2. 
2. Построй линейную диаграмму, на которой будет отображаться количество установок по месяцам за весь период с начала 2017 года. Обязательно укажи название графика. Для подписи горизонтальной оси используй столбец “Месяц - Год”
3. Вычисли колонку **M2Mchange** по формуле ниже, которая будет отображать изменение количества установок месяц к месяцу. В этом случае 1 элемент столбца будет пустым, т.к. нам не с чем сравнивать январь 2017 года, более ранние данные отсутствуют.

<img src="https://lh4.googleusercontent.com/y1SKm0kvS2zFKwrlaOI3d9xWcOK8TERrdylOZTEXb2U63vaQqsH5ntA_YZw1I2brBoEDAdsjf4i7j_lWTeq5q4fss8Ugzvwq0VICC5Z7_NMFsVpMAQmnTx3WUMJQVSx4naIp_Cuedb6U-A2WIxqr9ZDu-dFIVoW5oZ-2vJwoPI2SG-gM86Hy7A-2a71Wzw" width=30% height=30% >

4. Построй линейную диаграмму, которая будет отображать изменение параметра **M2Mchange** (количества установок месяц к месяцу). Для горизонтальной оси используй столбец  “Месяц - Год”, который создали ранее.

5. Далее необходимо проверить, похоже ли поведение **M2Mchange** в 2022 году на поведение в предыдущие годы. Для того, чтобы можно было выявлять аномалии с использованием доверительных интервалов, необходимо, чтобы данные были распределены нормальным образом. Для этого проведем тест на нормальность. 

   1. Наша нулевая гипотеза состоит в том, что данные распределены нормальным образом. Если гипотеза будет отвергнута, верна альтернативная гипотеза -  данные распределены отлично от нормального.
   2. Скопируй на страницу “Тест на нормальность” данные **M2Mchange** с 2017 по 2021 год включительно. 2022 мы в выборку не включаем, т.к. наша гипотеза состоит в том, что там есть аномалии.
   3. Вычисли параметры СЧЁТ(), СКОС(), ЭКСЦЕСС()
   4. Вычисли критерий Харке-Бера - это критерий согласия, который определяет, имеют ли выборочные данные асимметрию и эксцесс, соответствующие нормальному распределению .
   5. Используя ХИ2.РАСП.ПХ() вычисли p-value. Если p-value превышает 0,05, мы не можем отвергнуть нулевую гипотезу. 

6. После теста гипотезы о нормальности распределения перейди на вкладку “Доверительный интервал”. Если данные распределены нормально, то мы можем построить некоторый доверительный интервал, в котором могут находиться любые ожидаемые значения из нашего распределения. Если новые данные не входят в доверительный интервал, значит мы наблюдаем аномалию.

   1. Перенеси данные из **M2Mchange** в соответствующие ячейки по годам. Т.к. могут наблюдаться некоторые сезонные отклонения, мы будем рассматривать изменения количества установок в течение года. Таким образом, мы получим по **5** измерений на каждый месяц. Чтобы перенести значения из ячейки без привязки к формуле, выбери в параметрах вставки “Вставить значения”.
   2. Вычисли для каждого месяца среднее значение, стандартное отклонение и величину **95%** доверительного интервала, используя СРЗНАЧ(), СТАНДОТКЛОН() и ДОВЕРИТ.НОРМ() соответственно. Затем вычисли верхнюю и нижнюю границы доверительного интервала.
   3. Построй график, на котором будет отображаться среднее, верхняя и нижняя границы доверительного интервала и данные за 2022 год.
   4. Подтверждается ли наша изначальная гипотеза, что падение количества установок в мае 2022 года можно считать сезонным явлением и это нормально?

7. Соберитесь с командой и подготовьте общий excel-файл с вычислениями da_project04_empty.xlsx , переименуйте его в da_project04_ready.xlsx и загрузите в репозиторий этого проекта (ветка develop, папка src).

8. Пронумеруйте от 1 до 6 и подготовьте текстовый файл da_project04.txt с ответами на следующие вопросы:

   1. Какой тренд наблюдается по ежемесячной статистике установок с 2017 года?
   2. Что показывает параметр M2Mchange?
   3. Какая звучит нулевая гипотеза в тесте Харке-Бера?
   4. Какое значение параметра “альфа” в формуле ДОВЕРИТ.НОРМ соответствует 95% интервалу значимости?
   5. Напиши значение p-value с точностью до 2 знаков после запятой.
   6. Укажи, является ли падение количества установок в мае 2022 года нормальным.

Следующее упраднение включает в себя сбор и обработку данных. Распланируйте внутри команды заранее, кто будет заниматься сбором данных, вычислениями и визуализацией. Проведите следующее мини-исследование.
1. Соберите статистику с других участников курса по использованию продуктов банков и мобильных приложений. Можно использовать шаблон из папки materials или собрать опрос на любой онлайн-платформе. Рекомендуем для анонимизации респондентов пользоваться категориями для группировки соц.дем показателей, таких как, например, возраст или место жительства. Сохраните таблицу со статистикой в файл da_project04_stats.xlsx
2. Вне зависимости от количества банков и приложений все респонденты могут быть нашими потенциальными пользователями. На основании таблицы со статистикой сформируйте портрет типичного пользователя нашего приложения. Для этого необходимо рассчитать средние показатели количества банков, приложений, карт и др. численных показателей, которые удалось собрать.
3. Проверьте, наблюдаются ли перекосы в категориальных вопросах, например, по возрасту или полу. Проведите расчет статистической значимости отличий по частоте использования мобильного приложения для мужчин и женщин. Для этого сначала необходимо самостоятельно проверить данные на нормальность. В случае, если распределение нормальное, для расчета статистической значимости используйте функцию СТЬЮДЕНТ.ТЕСТ в Excel с двусторонним распределением, для выбора типа теста расчитайте дисперсию для каждой из выборок. Если распределение не нормальное, предварительно используйте функцию НОРМАЛИЗАЦИЯ(). Сохраните расчеты в файл da_project04_stats_test.xlsx с обязательным выводом о нормальности распределения и наличии стат.значимых различий.
4. Оформите портрет типичного пользователя с важными, на ваш взгляд, параметрами на слайде в PowerPoint da_project04_user.pptx Например: пол, возраст, размер населенного пункта, сколько банков в среднем использует, как часто пользуется приложениями и для чего. Если есть стат.значимые различия между мужчинами и женщинами - составьте 2 разных портрета для этих групп (можно поделить слайд пополам). Не забудьте указать данные о размере выборки. 
Категории на картинке ниже приведены для примера:
<img src="https://assets.website-files.com/602ff064968e34c1f8134de1/617ae5f82a8415e4aa33ffcc_portret-tsa.png" width=30% height=30% >

<h3 id="дополнительное-задание">*Дополнительное задание</h3>

1. По профилю пользователя, полученному в основном задании, попробуйте с командой оценить объем рынка подобных мобильных приложений в РФ. Для оценки можно использовать открытые источники по соц.демографическому составу населения. Зная количество установок нашего приложения из исходного датасета (установки считаем уникальными), дайте оценку доли рынка, которую мы занимаем. Сформулируйте 1-2 гипотезы, по какой причине мы могли просесть по установкам в мае 2020 года. Оформите свои расчеты в свободной форме в файле da_project04_extra.txt под номером 1.

2. Данные, полученные в первой части, можно использовать как исходный датасет для построения дашборда в Yandex DataLens. Распределите задания ниже между участниками группы и создайте дашборд с описанием основных результатов этого проекта.
    1. Скопируй лист “Исходные данные” в новый excel-файл da_project04_data1.xlsx.
    2. Создай подключение в Yandex DataLens, используй файл da_project04_data1.xlsx в качестве источника и создай датасет.
    3. Воссоздай графики с ежемесячным количеством установок и M2Mchange, добавь их на дашборд.
    4. Скопируй столбцы “Месяц”, “среднее”, “upper”, “lower”, ‘2022 год” в новый excel-файл da_project04_data2.xlsx.
    5. Создай подключение в Yandex DataLens, используй файл da_project04_data2.xlsx в качестве источника и создай датасет.
    6. Воссоздай график с границами доверительного интервала, средним и данными за 2022 год.
    7. Добавь в качестве индикатора % падения установок в мае 2022 года.
    8. В левый верхний угол добавь текстовый блок с описанием кейса, проведенными исследованиями и итоговыми выводами.
    9. Настрой к дашборду публичный доступ по ссылке и скопируй ссылку в текстовый файл da_project04_extra.txt под номером 2.
    10. Выгрузи дашборд в .pdf в файл da_project04_extra_dashboard.pdf

<h2 id="chapter-iv">Chapter IV</h2> 
<h3 id="сдача-работы-и-проверка">Сдача работы и проверка</h3>

1. Впиши ответы на вопросы в файл блокнота с названием da_project04.txt 
2. Сохрани вычисления в excel-файле и переименуй его в da_project04_ready.xlsx
3. Сохрани статистику опроса в файл da_project04_stats.xlsx
4. Сохрания вычисления стат.значимости в файл da_project04_stats_test.xlsx 
5. Оформи портрет пользователя приложения в файл da_project04_user.pptx 
6. При необходимости, выгрузи дашборд с дополнительным заданием в файл da_project04_extra_dashboard.pdf, файл со ссылкой на дашборд da_project04_extra.txt и файлы с датасетами da_project04_data1.xlsx и da_project04_data2.xlsx
7. Загрузи перечисленные выше файлы в GIT-репозиторий этого проекта для проверки (ветка develop, папка src).

💡 [Нажми здесь](https://forms.gle/8gzQemHztiJGDsCd7) **чтобы отправить обратную связь по проекту**.
