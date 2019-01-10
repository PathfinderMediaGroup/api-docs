# Pledges

## Get Pledges

```php
<?php
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/pledges');
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $pledges = json_decode($output);
?>
```

```json
{
  "en": {
    "1": "Spindleclutch I",
    "2": "City of Ash I",
    "3": "Bloodroot Forge"
  },
  "de": {
    "1": "Spindeltiefen I",
    "2": "Stadt der Asche I",
    "3": "Blutquellschmiede"
  },
  "fr": {
    "1": "Tressefuseau I",
    "2": "Cité des cendres I",
    "3": "Forge de Sangracine"
  }
}
```

This endpoint retrieves all pledges for a given day.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/pledges`

### Query Parameters

Parameter | Description | Default
--------- | ----------- | -----------
daysFromNow | Retrieve the pledges for x days from now | 0