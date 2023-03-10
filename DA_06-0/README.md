# Проект 06

Работа с условными операторами и подзапросами

## Cодержание

1. [Chapter I](#chapter-i) \
    1.1. [Введение](#введение) 
2. [Chapter II](#chapter-ii) \
    2.1. [Общая инструкция](#общая-инструкция) 
3. [Chapter III](#chapter-iii) \
    3.1. [Знакомство с инструментом](#знакомство-с-инструментом) \
    3.2. [Задание](#задание)\
    3.3. [*Дополнительное задание](#дополнительное-задание)
4. [Chapter IV](#chapter-iv)\
    4.1 [Сдача работы и проверка](#сдача-работы-и-проверка) 


<h2 id="chapter-i">Chapter I</h2> 
<h3 id="введение">Введение</h3>

При написании SQL запросов часто возникает необходимость отфильтровать данные по какому-то условию. Это делается не только для конкретизации самого запроса (когда нас интересует конкретный год или категория товаров), но и для ограничений, что бывает крайне важно при работе с ограниченными вычислительными ресурсами (чтобы, например, протестировать корректность запроса на данных за последнюю неделю и не ждать выполнения тяжелых вычислений на всем объеме данных).

В этом проекте мы на примерах познакомимся с использованием команд WHERE и HAVING. Часто они используются в связке с логическими операторами AND/OR, когда необходимо скомбинировать несколько условий (например, даты и какую-то конкретную категорию). 

Еще мы познакомимся с концепцией вложенных запросов. Она позволяет производить поэтапную обработку массива данных: когда нет возможности провести все преобразования сразу в одном запросе, можно встраивать запросы друг на друга, как на изображении ниже. Их же можно использовать и для условий, когда нет уверенности, что мы покроем все возможные варианты фильтров явным перечислением или их слишком много).

<img src="https://lh5.googleusercontent.com/-U9739tqb-Lul4z8h2zXQCnKggWPeCDXxQX0_YXYPwG4uR4om5H9EUn23WWQdk1JR4N_QvzQNkH74dnsTzkqPN2xddUHyk8PodyJWj9BQDxUz9V5hrokwrcicqxNKn8pghIunejgSzr0hOFdVcZvGCQ" width=60% height=60% >


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

<h2 id="chapter-iii">Chapter III</h2> 
<h3 id="знакомство-с-инструментом">Знакомство с инструментом</h3>

Для работы с SQL и тренировки будем пользоваться [sqliteonline.com](https://sqliteonline.com/)

По ссылке ты откроешь инструмент SQL Lite Online - онлайн-песочница, к которой, как мы делали ранее с Yandex DataLens, можно подключить свои файлы в качестве источника данных и потренироваться в написании запросов на языке SQL. Для загрузки своего файла нажми кнопку Import и загрузи файл. Слева отображается структура нашей базы данных: какие есть таблицы, какие столбцы в ней содержатся, данные каких типов хранятся в столбцах. Также в тренажере есть подсказки по использованию команд, и в самом скрипте будут удобно подсвечиваться ключевые слова.

<h3 id="задание">Задание</h3>

В этом проекте будем использовать в качестве источника данных тот же .csv файл, что и на прошлой неделе, чтобы подробнее разобраться в отдельных категориях товаров. 
Ранее мы выяснили, что самой популярной категорией товаров в нашем интернет-магазине являются видеокарты. Давай проверим, так ли это было всегда, сколько денег они приносят от общей выручки магазина, в какие часы их покупают чаще всего и можем ли мы предложить этим покупателям еще какие-то дополнительные товары.
1. Укажи файл da_project05_purch.csv из папки datasets в качестве источника при импорте в sqliteonline.com
2. Вычисли выручку по категории computers.components.videocards по месяцам. Чтобы не указывать название явно, можно использовать конструкцию like '%videocard%', где % указывают на то, что вокруг этой строки могут находиться другие символы.
3. Вычисли общую выручку по месяцам, можно переиспользовать предыдущий без фильтра по категории. Для того, чтобы закомментировать строку и не удалять ее из запроса, укажи двойное тире "--" перед строкой.
4. Получив значение общей суммы и суммы в конкретной категории, вычисли %, сколько составляют продажи видеокарт от общей выручки. Для вычисления % можно использовать Excel/калькулятор и любые другие подручные средства. 
5. Так как в последние месяцы видеокарты начали составлять значительную долю выручки нашего онлайн-магазина, необходимо выяснить, какой бренд пользуется наибольшей популярностью. Для этого вычисли количество покупок в категории computers.components.videocards, используя группировку по brand.
6. Давай посмотрим, какие еще категории товаров покупают пользователи, которые купили видеокарты этого бренда. В подзапросе с условием используй поиск по user_id с покупками в нужной категории и бренде.
7. Мы выяснили, какие товары пользуются популярностью в нашем интернет-магазине и хотим запустить акцию для покупателей "Счастливый час!", когда при покупке любой видеокарты пользователь получает скидку на товар из п. 6. Необходимо выяснить, сколько покупок совершалось в какой час в категории computers.components.videocards. Для создания колонки с часами используй команду strftime()
9. Пронумеруй от 1 до 5 и запиши в файл da_project06.txt ответы на следующие вопросы:
    1. какой тренд имеет доля выручки видеокарт от общих продаж: падает или растет?
    2. сколько % от общей выручки составили продажи видеокарт в феврале 2021 года, напиши с округлением до 1 знака после запятой
    3. какой бренд самый популярный
    4. перечисли через запятую все подкатегории товаров computers, которые покупяют вместе с видеокартами самого популярного бренда. 
    5. предложи топ 2 часа, в которые чаще всего покупали видеокарты, укажи через запятую.

<h3 id="дополнительное-задание">*Дополнительное задание</h3>

Как правило, обычно недостаточно знать самые популярные позиции, т.к. они могут быть дешевыми и иметь много продаж, но в сумме приносить не так много денег. Еще одной значимой метрикой для пользователя явлеяется средний чек. В этом задании необходимо вычислить средний чек пользователя, который покупал в нашем интернет-магазине видеокарту vs средний чек пользователя, который видеокарту не покупал. Сделать это необходимо в одном запросе, используя вложенную структуру. Предлагаемый вариант решения: 
1. промаркировать пользователей по признаку "купил/не купил", для этого можно использовать конструкцию CASE WHEN THEN. В таком случае промаркируется одна или N строчек, когда пользователь совершал покупку, подходящую под наши условия. Для того, чтобы промаркировать пользователя, можно при дальнейшней группировке использовать maх() по этому признаку, и тогда если у нас хотя бы в одной строке была 1, то у пользователя будет 1.
2. посчитать на каждого пользователя средний чек, используя сумму его трат за все время и количество покупок. На этом же этапе при группировке по пользователям используй maх() из п.1
3. используя группировку по признаку "купил/не купил", вычисли средний чек по всем пользователям этой группы.

В файле da_project06_extra.txt впиши через запятую с округлением до двух знаков, какой средний чек у купивших видеокарту и не купивших, укажи категории. Дополнительно добавь в файл текст свой запроса.

<h2 id="chapter-iv">Chapter IV</h2> 
<h3 id="cдача-работы-и-проверка">Сдача работы и проверка</h3>

1. Впиши ответы на вопросы в файл блокнота с названием da_project06.txt 
3. При необходимости, заполни файл с дополнительным заданием da_project06_extra.txt
4. Загрузи перечисленные выше файлы в GIT-репозиторий этого проекта для проверки (ветка develop, папка src).

💡 [Нажми здесь](https://forms.gle/AQp2XpdRoKuhR9b67) **чтобы отправить обратную связь по проекту**.

