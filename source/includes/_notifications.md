# Notifications

## All Notifications

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

This endpoint retrieves the list of notifications for the specified user.

### HTTP Request
`GET https://gametize.com/api2/notifications.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 1 | 1 | Specify the number of results to be returned on each page.
game_id | optional | 0 | 124 | Get notifications with respect to a particular game.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | **required** | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7| Get your notifications.

## Unread Notification Count

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

This endpoint retrieves the **number of unread notifications** for the specified user.

### HTTP Request
`GET https://gametize.com/api2/notifications/unread.json`

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
game_id | optional | 0 | 124 | Get notifications with respect to a particular game.

<aside class="dev">No <code>page</code> and <code>limit</code> parameters for this, but required above for all notifications? May require fix/standardization.</aside>

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | **required** | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7| Get your notifications.
