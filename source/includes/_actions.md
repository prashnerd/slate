# Action

## Claim

<aside class="dev"><strong>OMG SO MANY THINGS TO WRITE</strong><br><em>I'll come back to this bit, promise...</em></aside>

## Purchase Item

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

This endpoint purchases an item available in the bundle store for the specified user.

### HTTP Request
`POST https://gametize.com/api2/action/purchase_item.json`

<aside class="notice">The specified user needs to have an adequate amount of credits awarded within the relevant bundle for the purchase to succeed!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description 
---|---|---|---|---
type_id | **required** | 0 | 4567 | The ID of the item to be purchased.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Update User

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

This endpoint updates the profile of the specified user.

### HTTP Request
`POST https://gametize.com/api2/action/update_user.json`

<aside class="notice">The specified user needs to have an adequate amount of credits awarded within the relevant bundle for the purchase to succeed!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description 
---|---|---|---|---
user_name | optional | null | Someone Cool | The user's name.
photo_url | optional | null | http://myprofile.com/image.png | The URL to a user's photo. Giving a blank string `""` resets the user's photo to the default image. Providing the `file` and `file_name` parameters will omit the `photo_url`. 
country_id | optional | 0 | 192 | Country ID of the user - *contact support@gametize.com if you are unsure of what this parameter should be. 
telephone | optional | null | +6512345678 | Phone number of the user.
file | optional | null | [Image Data] | The photo image file for the user profile. Acceptable formats include: png, jpg, gif - *Maximum Size: 2MB*. 
file_name | optional | null | photo.jpg | The name of the image file for the user profile. 

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
session_key | **required** | null | 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Identifies the user performing the action.

## Post Comment

## Like/Unlike

## Accept Challenge

## Follow/Unfollow User

## Join/Leave

## Use Item

## Delete Claim

## Add/Remove Bookmark