## Объект pm.request

Для работы с данными запроса в скриптах можно воспользоваться объектом pm.request. Нам потребуется добавить в коллекцию новый запрос:

`POST`	https://postman-echo.com/post

```json
Body:
{
    "var": "value"
}
```

Для начала рассмотрим несколько полезных свойств объекта **pm.request**.

```json
pm.request.method
```

Данное свойство содержит **HTTP** метод запроса.

```json
pm.request.url
```

Свойство содержит **url** запроса.

```json
pm.request.headers
```

Это свойство содержит список заголовков запроса.

```json
pm.request.body
```

Данное свойство содержит **тело** запроса. Добавим к нашему запросу следующий код, на вкладку pre-request:

```json
console.log("Request method : " + pm.request.method);
console.log("Request url : " + pm.request.url);
console.log("Request headers : " + pm.request.headers);
console.log("Request body : " + pm.request.body);
```

После нажатия на кнопку Send в консоли мы увидим такой вывод:

```json
Request method : POST
Request url : https://postman-echo.com/post
Request headers :
Request body : {
    "var": "value"
}
```

## Изменение заголовков

Используя **pm.request.headers** мы можем изменять заголовки, отправляемые в запросе. У нас есть возможность добавлять и удалять заголовки, а также менять значения уже существующих. Давайте сначала добавим два заголовка к нашему запросу:

- custom-header1: custom-value1
- custom-header2: custom-value2

Эти заголовки пригодятся нам позже.

```json
pm.request.headers.add({
  key: "headerName",
  value: "headerValue"
});
```

С помощью метода **add()** мы можем *добавить* новый заголовок к нашему запросу. В качестве параметра мы передаем пару *ключ-значение*, в которой содержится название заголовка и его значение.

```json
pm.request.headers.remove("headerName");
```

Используя метод **remove()** мы можем *удалить* заголовок с именем headerName из запроса.

```json
pm.request.headers.upsert({
  key: "headerName",
  value: "headerNewValue"
});
```

С помощью метода **upsert()** мы можем *добавить* заголовок к нашему запросу. Если заголовок с таким именем *уже существует, его значение обновится*. В качестве параметра мы передаем пару ключ-значение, в которой содержится название заголовка и его значение. Добавим к нашему запросу следующий код:

```json
pm.request.headers.add({
  key: "custom-header3",
  value: "custom-value3"
});
pm.request.headers.remove("custom-header1");
pm.request.headers.upsert({
  key: "custom-header2",
  value: "custom-value4"
});
```

Первый вызов добавляет к запросу новый заголовок с именем “custom-header3”. Второй удалит существующий заголовок с именем “custom-header1”. Третий вызов обновит значение для заголовка с именем “custom-header2”.

## Изменение параметров запроса

Следующие два метода позволяют менять параметры строки запроса.

```json
pm.request.addQueryParams("param1=value1");
```

С помощью метода **addQueryParams()** мы можем *добавить параметр* в строку запроса. Он принимает на вход строку, содержащую новый параметр и его значение.

```json
pm.request.removeQueryParams("param1");
```

Метод **removeQueryParams()** позволяет нам *удалить параметр* из строки запроса. Передаваемое значение - это имя параметра, который требуется удалить.

Если мы немного изменим наш изначальный запрос, и добавим к нему два query параметра:

`POST` https://postman-echo.com/post?param1=value1&param2=value2

Затем на вкладке *pre-request* добавим следующий код:

```json
pm.request.addQueryParams("param3=value3");
pm.request.removeQueryParams("param1");
```

Нажав кнопку Send, мы увидим что в запросе мы передавали два параметра строки запроса: param2=value2 и param3=value3.
