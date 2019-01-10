# Guides / Builds

## Search for guides

```php
<?php
    $searchQuery = 'frost';
    $query = '?query='.urlencode($searchQuery);
    
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/crownstoreitems/search'.$query);
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $sets = json_decode($output);
?>
```

```json
[
    {
      "id": 247,
      "name": "Crown Crafting Motifs: Frostcaster",
      "image": "8YLZvLwoaHAKuhzUIddZ.jpg",
      "category": "Crafting",
      "currency": "Crowns",
      "cost": 2000,
      "active": 0,
      "active_since": null,
      "created_at": "2018-12-14 09:47:13",
      "updated_at": "2019-01-05 15:56:08",
      "cleaned": "crowncraftingmotifs:frostcaster"
    }, {
      "id": 5,
      "name": "Sabre Cat Frost Atronach",
      "image": "d2pZ9RhqnTfMMZD5eqhN.jpg",
      "category": "Crown Crates",
      "currency": "Crown Gems",
      "cost": 600,
      "active": 0,
      "active_since": null,
      "created_at": "2018-12-14 09:45:35",
      "updated_at": "2019-01-05 15:56:06",
      "cleaned": "sabrecatfrostatronach"
    }
]
```

This endpoint searches guides anbd builds.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/guides/search`

### Query Parameters

Parameter | Description | Required | Default | type
--------- | ----------- | ----------- | ----------- | -----------
name | Guide name to search by | No | null | string
role | Role to search by | No | null | string
class | Class to search by | No | null | string
