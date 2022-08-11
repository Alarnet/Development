**UNION ALL** выбирает все строки из каждой таблицы и комбинирует их в одну таблицу.

Следующее SQL выражение использует UNION ALL для выбора информации из Первой и Второй таблиц:  
```sql  
SELECT ID, FirstName, LastName, City FROM First   
UNION ALL  
SELECT ID, FirstName, LastName, City FROM Second;  
```  
