Оператор **UNION** используется для комбинирования наборов результатов двух и более выражений SELECT.

Все выражения SELECT внутри UNION должны иметь **одинаковое количество столбцов**. Столбцы также должны иметь **одинаковые типы данных**. Также, столбцы в каждом выражении SELECT должны быть в одинаковом порядке.

Синтаксис оператора UNION:  
```sql  
SELECT column_name(s) FROM table1  
UNION  
SELECT column_name(s) FROM table2;  
```  
Пример применения оператора UNION:  
```sql  
SELECT ID, FirstName, LastName, City FROM First  
UNION  
SELECT ID, FirstName, LastName, City FROM Second;  
```  

Если ваши столбцы не совподают в точнности по всем запросам, то вы можете использовать значение **NULL**(или любое другое) следующим образом:  
```sql  
SELECT FirstName, LastName, Company FROM businessContacts  
UNION  
SELECT FirstName, LastName, NULL FROM otherContacts;  
```  
>Оператор UNION используется для комбинирования наборов результатов двух и более выражений SELECT!
