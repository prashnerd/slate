# Items

## Item Profile

```java
```

```python
```

```shell
```

```javascript
```

>The above code returns JSON structured like this:

```json
```

This endpoint retrieves the detailed profile of an item.

### HTTP Request
`GET https://gametize.com/api2/items/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired item ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 1 | 1 | Specify the number of results to be returned on each page.
game_id | optional | 0 | 124 | Get notifications with respect to a particular game.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7| Get data with respect to you. This includes whether you have earned this item or not.
