**RIGHT JOIM** возвращает все строки из праавой таблицы, даже если нет совпадений в левой.

Синтаксис объединения RIGHT JOIN:  
```sql  
SELECT table1.column1, table2.column2...  
FROM table1 RIGHT OUTER JOIN table2  
ON table1.column_name = table2.column_name;  
```  
>Опять же, ключевое слово **OUTER** является опциональным и может быть опущено!

Пример из предыдущего урока, но с объединением RIGHT JOIN:  
```sql  
SELECT customers.Name, items.Name From customers  
RIGHT JOIN items ON customers.ID=items.Seller_id;  
```  
