### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы? 

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это 
реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД 
логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

**Ответ 1.1**

Лучше всего подойдут реляционные СУБД, т.к. данный тип поддерживает SQL-запросы, что позволяет удобно анализировать и формировать отчеты. Примеры наиболее известных релционных СУБД: Microsoft SQL Server, PostgeSQL.

**Ответ 1.2**

Для лендингов - СУБД NoSQL, например MongoDB. Так как в лендинге данные представлены не только текстом, а изображениями, видеоматериалами, звуковыми файлами и т.д.  
Для CRM - реляционная СУБД, например PostgreSQL. Так данные представлены в виде текста.

**Ответ 1.3**

Судя по описанию БД, в ней будут храниться документы (описание корпоративных норм и правил), обучающие фото и видеоматериалы и т.д., поэтому выбор СУБД типа NoSQL.

**Ответ 1.4**

Полагаю, графовая СУБД, т.к. этот тип позволяет быстро работать со связями.

---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

**Ответ 2.1**  

* Начало транзакции.
* Указание суммы, на которую будет пополнен счёт.
* Проверка баланса пополняемого счёта.
* Пополнение баланса на определённую сумму.
* Сохранение баланса полполняемого счёта.
* Окончание транзакции.

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

**Ответ 3.1**
* Строгая схема. Гарантирует целостность данных и упрощает управление. Это особенно важно для приложений, где структура данных редко изменяется.
* Стандартный язык запросов. SQL является широко известным и используется многими разработчиками. Это облегчает обучение и интеграцию с другими системами.
* Поддержка транзакций. Обеспечивает надёжность операций с данными. Транзакции позволяют гарантировать, что все операции с данными выполняются корректно и полностью.
* Совместимость. Множество инструментов и библиотек поддерживают SQL-базы данных. Это делает их удобными для интеграции с различными приложениями и системами.
* Безопасность. SQL системы, как правило, имеют более высокий уровень безопасности, поскольку они были разработаны с учетом требований безопасности.

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

**Ответ 4**  

При выборе СУБД для большого количества вычислений при работе с огромным количеством данных стоит учитывать следующие критерии:

* Производительность. СУБД должна обеспечивать высокую производительность обработки запросов и операций с данными.
* Масштабируемость. СУБД должна позволять масштабировать вычислительные ресурсы в горизонтальном (добавление новых серверов) и вертикальном (увеличение мощности существующих серверов) направлении.
* Отказоустойчивость. СУБД должна иметь механизмы обеспечения безопасности данных и восстановления после сбоев.
* Распределённость. СУБД должна позволять распределять данные и запросы на выполнение между несколькими серверами для увеличения пропускной способности и ускорения обработки.

В части выбора модели распределённых вычислений, изучив информацию в сети, полагаю, лучше всего остановить выбор на MapReduce. Так как она изначально ориентирована на параллельные вычисления в распределенных кластерах. Принцип MapReduce состоит в разделении информационного массива на части, параллельной обработке каждой части на отдельном узле и финального объединения всех результатов.

---
