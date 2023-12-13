# Домашнее задание к занятию «Базы данных, их типы»

---

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

------
**Ответ 1.1:** Я предплогаю что сэтой задачей справится колночная БД. В них данные хранятся последовательно в виде одной колонки, и предполагается, что на одном и том же месте в каждой колонке хранятся элементы, которые относятся к одной строке. Это позволяет эффективно сжимать данные и анализировать их — находить сумму, количество или среднее значение. Колоночные базы данных позволяют загружать новые данные непрерывным потоком или порциями. При этом удалять их так нельзя. Главная область применения колоночных баз данных — анализ данных. Такие базы аналитики и менеджеры компаний используют, чтобы хранить историю событий.

---

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

------
**Ответ 1.2:** Я пологаю, что в конкртном примере подойдёт документо-ориентированая БД. В отличие от реляционных баз данных, документо-ориентированные хранят информацию в виде «документов», а не таблиц и строк. Главное преимущество документных баз данных — возможность хранить информацию без строгого ограничения по структуре. Документные базы данных умеют хранить информацию целиком и получать её одним запросом. Даже если структура элементов будет разной. Ещё документные базы данных позволяют использовать ссылки на другие записи в базе, что чем-то напоминает реляционную модель.

---

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

------
**Ответ 1.3:** Я пологаю тут подойдёт реляционная модель. Данные в ней лежат в виде таблиц, которые связаны друг с другом через сквозные параметры. Такая архитектура обеспечивает построчное хранение данных и нужна для создания строгой структуры. Ещё одна их особенность: за одно обращение к базе пользователь сможет получить лишь небольшое число элементов.Каждая строка имеет уникальный идентификатор, или ключ. Поэтому найти нужные данные и связать их между собой в такой базе данных легко. Реляционные базы данных используют, когда объём данных не превышает нескольких терабайт. Это делает их подходящими практически любому проекту.

---
1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.

------
**Ответ 1.4:** Я пологаю, что с этой задачей справится графовый тип БД. В них элементы имеют взаимосвязи в виде графа, где у каждого его узла есть множество связей с другими узлами. Такой вид баз данных напоминает паутину. Обычно эти базы данных используют в соцсетях или рекомендательных сервисах. Каждый узел графовой базы данных содержит в себе данные, а чтобы составить взаимосвязи между узлами, используют рёбра. В них хранятся начальный и конечный узлы, направление и тип. Рёбра описывают взаимосвязи между двумя узлами — например, «родитель — потомок», — а также действия над ними. Обойти весь граф можно очень быстро, потому что связи между узлами не считаются во время запроса, а сразу хранятся в базе данных. Поэтому графовые базы данных применяются в соцсетях, рекомендательных сервисах и системах выявления мошенничества, когда нужно построить взаимосвязи между данными и запросить их.

---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

------
**Ответ 2.1:**
1. Прочесть баланс на счету карты.
2. Уменьшить баланс на N денежных единиц.
3. Сохранить новый баланс счета карты.
4. Прочесть баланс на счету телефона.
5. Увеличить баланс на N денежных единиц.
6. Сохранить новый баланс счёта телефона.
---
2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

---

**Ответ 3.1:**
1. Производительность: SQL-базы данных имеют более развитое индексирование, чем NoSQL-базы, что обеспечивает более высокую производительность при выполнении сложных запросов, но может снижать скорость работы при выполнении простых запросов. 
2. Схема данных: SQL-база данных имеет строгую схему данных, которая определяет типы данных и связи между таблицами. В NoSQL-базах данных нет строгой схемы данных.
3. Масштабируемость: SQL-базы данных имеют ограничения на масштабируемость, из-за чего они могут быть неэффективны в обработке большого количества данных. NoSQL-базы данных обладают большой масштабируемостью, из-за чего они могут обрабатывать большие объёмы данных.
4. Гибкость запросов: SQL имеет очень мощный язык запросов, что делает его лучшим выбором для сложных запросов, связанных с большим количеством таблиц. С другой стороны, NoSQL имеет простой язык запросов, который хорошо подходит для запросов, связанных с большим количеством данных.
5. Скорость обработки: Несмотря на то, что SQL обычно работает медленнее, чем NoSQL, его мощный язык запросов позволяет быстро обрабатывать сложные запросы. С другой стороны, NoSQL работает очень быстро с неструктурированными данными в больших объёмах.


3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

---
**Ответ 3.1*:** SQL соответствует свойствам ACID и хорошо справляется с вертикальной масштабируемостью, тогда как NoSQL предлагает собственное горизонтальное масштабирование и обеспечивает свойства BASE. Однако NoSQL не соблюдает правила ACID, необходимые для поддержания надежной и согласованной базы данных. Быстро развивающиеся предприятия и организации ежедневно генерируют терабайты транзакционных данных, работая в OLTP-системе. NewSQL — идеальный выбор. NewSQL совершенствует SQL, обеспечивая горизонтальную масштабируемость при сохранении свойств ACID. Это облегчает работу с большими данными за счет реализации параллелизма. Он также хорошо справляется с соблюдением требований ACID. Таким образом, NewSQL, похоже, нашел золотую середину между скоростью, масштабируемостью, согласованностью и доступностью. Несмотря на то, что NewSQL все еще находится на зачаточном этапе, он отвечает всем требованиям, чтобы стать идеальной базой данных для приложений больших данных и OLTP.

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

---
**Ответ 4.1:** Я пологаю, что тут лучьше справится пиринговая архитектура. Пиринговые распределенные системы возлагают на все компьютеры в сети одинаковые обязанности. Разделение на клиентские и серверные компьютеры отсутствует, и любой компьютер может выполнять все функции. Пиринговая архитектура стала популярной в сфере совместного использования контента, потоковой передачи файлов и сетях блокчейн.

---
