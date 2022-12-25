# Домашнее задание к занятию 11.1. «Базы данных, их типы»

### Задание 1. СУБД

### Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать 
правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для
каждой предметной области. 

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему? 
 
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков.
СУБД должна гарантировать целостность и чёткую структуру данных.

#### *Ответ: судя по описанным требованиям, хорошо подойдет реляционная СУБД. Например, MySQL.*

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к 
маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? 
СУБД должны быть гибкими и быстрыми.

#### *Ответ: наверное, к требованиям в данном случае можно записать также масштабируемость. Так или иначе, если делать акцент на гибкость и скорость, то нужно рассмотреть нереляционную СУБД. К примеру: MongoDB*

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу 
и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

#### *Ответ: формат таких данных подразумевает строгую иерархию. Соответственно, следует выбрать СУБД иерархического, а лучше сетевого типа. Например: IDMS*

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов 
по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать
со связями.

#### *Ответ: быстро работать со связями сможет сетевая СУБД. Например, всё та же IDMS*

---

### Задание 2. Транзакции

2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы 
транзакция завершилась успешно. Ориентируйтесь на шесть действий.

#### Ответ:
*Если я правильно понял, то тут нужно описать 6 этапов, которые происходят в биллинге. То есть всё то, что происходит после того, как абонент произвёл внесение денежных средств (через платежный терминал или личный кабинет банка). Привожу ниже:*

*1. Поступление в систему запроса извне на пополнение баланса номера 8922ххххххх на сумму 100 руб.*

*2. Проверка баланса номера 8922ххххххх*

*3. Пополнение баланса номера 8922ххххххх на сумму 100 руб.*

*4. Повторная баланса номера 8922ххххххх после пополнения*

*5. Ответ в сторонню систему (будь то банк-эмитент карты, с которой пополнялся баланс или же банк, в котором открыт счет платежного терминала, через который вносилось 100 руб.*

*6. Сообщение на номер 8922ххххххх о пополнении баланса*

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

#### Ответ:

*1. Проверка даты и суммы автоплатежа*

*2. Пополнение баланса номера 8922ххххххх на определенную сумму*

*3. Повторная баланса номера 8922ххххххх после пополнения*

*4. Сообщение на номер 8922ххххххх о пополнении баланса*

*5. Начисление бонусов за использование автоплатежа (если такые имеются)*

*6. Сообщение на номер 8922ххххххх о начислении бонусов за использование автоплатежа (если такые имеются)*

---

### Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL. 

#### Ответ:

1. Соответствие принципам ACID, чем обеспечнивает высокий уровень надежности БД и безопасности данных в ней

2. Обширное комьюнити (в силу давности разработки и эксплуатации)

3. Хорошо подходит для работы с табличными данными по заранее определенным схемам (благодаря чему широко используется в фин.секторе)

4. Универсальность SQL. БД можно в случае необходимости перенести на другую СУБД

5. Многообразие запросов к БД

---

### Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу 
выделено 1000 машин. 

На основе какого критерия будете выбирать тип СУБД и какая модель *распределённых вычислений* 
здесь справится лучше всего и почему?

*Приведите ответ в свободной форме.*
