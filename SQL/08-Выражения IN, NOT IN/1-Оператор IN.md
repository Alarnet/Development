Оператор **IN** используется тогда, когда вы хотите сравнить столбец больше чем с одним значением.

Например, возможно вам понадобится выбрать всех клиентов из городов New York, Los Angeles и Chicago.

С условием **OR**,ваш SQL будет выглядеть так:

- SELECT * FROM customers WHERE City = 'New York' OR City = 'Los Angeles' OR City = 'Chicago';

!Оператор IN используется тогда, когда вы хотите сравнить столбец больше чем с одним значением!

Вы можете получить такой же результат с одним условием **IN**, вместо использования нескольких условий **OR**:

- SELECT * FROM customers WHERE City IN ('New York', 'Los Angeles', 'Chicago');

!Обратите внимание на использование **скобок** в синтаксисе!
