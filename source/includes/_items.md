# Items

## Item Profile

```java
import java.io.**;
import java.net.URL;
import java.net.HttpURLConnection;

public class ApiTest {
    public static void main(String[] args) {
        System.out.println(executeGet("https://gametize.com/api2/item/1.json"));
    }
    
    public static String executeGet(String targetURL, String... params) {
        HttpURLConnection con = null;
        // Prepare request URL
        if (params != null) {
            targetURL += "?";
            for (String param : params) {
                targetURL += param + "&";
            }
        }
        try {
            // Attempt a connection to the API server
            URL url = new URL(targetURL);
            con = (HttpURLConnection) url.openConnection();
            con.setRequestMethod("GET");
            // Add header fields
            con.setRequestProperty("Accept", "application/json");
            con.setRequestProperty("Content-Type", "application/json");
            con.setRequestProperty("Authorization", "Bearer *-********-****-****-****-************");
            con.setUseCaches(false);

            // Get response
            if (con.getResponseCode() == 200) {
                // If success code is returned, use InputStream
                InputStream input = con.getInputStream();
                BufferedReader reader = new BufferedReader(new InputStreamReader(input));
                StringBuffer response = new StringBuffer();
                response.append(reader.readLine());
                reader.close();
                return response.toString();
            }
            else {
                // If an error code is returned, check the ErrorStream instead
                InputStream input = con.getErrorStream();
                BufferedReader reader = new BufferedReader(new InputStreamReader(input));
                StringBuffer response = new StringBuffer();
                response.append(reader.readLine());
                reader.close();
                return response.toString();
            }
        } catch (Exception e) {
            e.printStackTrace();
            return null;
        } finally {
            if (con != null) {
                con.disconnect();
            }
        }
    }
}
```

```python
```

```javascript
```

```shell
curl -i -H "Accept: application/json" "Content-Type: application/json" -H "Authorization: Bearer *-********-****-****-****-************" -X https://gametize.com/api2/item/1.json
```

>The above code returns JSON structured like this:

```json
{
    "ownedQuantity": 1,
    "createdAt": "2018-02-09 12:09:12.0",
    "code": 200,
    "price": 10,
    "name": "Reward 1",
    "imageSmall": "https://gametize.com/somepath/someimage.png",
    "description": "Reward 1 Description",
    "id": 1,
    "createdAtFormatted": "4 days ago",
    "imageLarge": "https://gametize.com/somepath/someimage.png",
    "type": "store",
    "adminToAward": false
}
```

This endpoint retrieves the **detailed profile** of the specified item.

### HTTP Request
`GET https://gametize.com/api2/items/ID.json`

<aside class="notice">Remember to replace "<code>ID</code>" with the desired item ID!</aside>

### Parameter(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
page | optional | 1 | 1 | Specify which page of results to retrieve.
limit | optional | 1 | 1 | Specify the number of results to be returned on each page.
user_id | optional | 0 | 124 | The user_id with respect to whom the items will be retrieved.

### Header(s)
Name | Usage | Default | Example | Description
---|---|---|---|---
Authorization | optional | null | Bearer 2073-02fde5e7-097a-4971-a4d4-de7154113ed7 | Get data with respect to you. This includes whether you have earned this item or not.
