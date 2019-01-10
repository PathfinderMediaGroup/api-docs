# Servers

## Get All Servers

```php
<?php
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/servers');
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $servers = json_decode($output);
?>
```

```json
[
    {
      "id": 1,
      "name": "PC EU",
      "status": 1,
      "created_at": null,
      "updated_at": null
    }, {
      "id": 2,
      "name": "PC NA",
      "status": 1,
      "created_at": null,
      "updated_at": null
    }
]
```

This endpoint retrieves all servers. Status 1 means the server is up. Status 0 means the server is down.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/servers`