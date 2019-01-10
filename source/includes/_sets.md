# Sets

## Get All Sets

```php
<?php
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/sets');
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
      "id": 1,
      "name": "Death's Wind",
      "location": "Glenumbra, Auridon, Stonefalls",
      "type": "Craftable",
      "slug": "deaths-wind",
      "bonus_item_1": null,
      "bonus_item_2": "Adds 2975 Physical Resistance",
      "bonus_item_3": "Adds 1206 Maximum Health",
      "bonus_item_4": "Adds 1206 Maximum Health",
      "bonus_item_5": "When you take melee damage while you are under 35% Health, you knockback and stun all enemies within 8 meters of you for 4 seconds. This effect can occur once every 30 seconds.",
      "has_jewels": 1,
      "has_weapons": 1,
      "has_heavy_armor": 1,
      "has_light_armor": 1,
      "has_medium_armor": 1,
      "traits_needed": 2
    }, {
      "id": 2,
      "name": "Twilight's Embrace",
      "location": "Stormhaven, Grahtwood, Deshaan",
      "type": "Craftable",
      "slug": "twilights-embrace",
      "bonus_item_1": null,
      "bonus_item_2": "Adds 1206 Maximum Health",
      "bonus_item_3": "Adds 833 Spell Critical",
      "bonus_item_4": "Adds 129 Spell Damage",
      "bonus_item_5": "Increases your healing received by 10%.",
      "has_jewels": 1,
      "has_weapons": 1,
      "has_heavy_armor": 1,
      "has_light_armor": 1,
      "has_medium_armor": 1,
      "traits_needed": 3
    }
]
```

This endpoint retrieves all sets.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/sets`

## Get a Specific Set

```php
<?php
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/sets/1');
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $set = json_decode($output);
?>
```

```json
{
  "id": 1,
  "name": "Death's Wind",
  "location": "Glenumbra, Auridon, Stonefalls",
  "type": "Craftable",
  "slug": "deaths-wind",
  "bonus_item_1": null,
  "bonus_item_2": "Adds 2975 Physical Resistance",
  "bonus_item_3": "Adds 1206 Maximum Health",
  "bonus_item_4": "Adds 1206 Maximum Health",
  "bonus_item_5": "When you take melee damage while you are under 35% Health, you knockback and stun all enemies within 8 meters of you for 4 seconds. This effect can occur once every 30 seconds.",
  "has_jewels": 1,
  "has_weapons": 1,
  "has_heavy_armor": 1,
  "has_light_armor": 1,
  "has_medium_armor": 1,
  "traits_needed": 2
}
```

This endpoint retrieves a specific set.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/sets/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the set to retrieve

## Search for sets

```php
<?php
    $searchQuery = 'death\'s';
    $query = '?query='.urlencode($searchQuery);
    
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/sets/search'.$query);
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
      "id": 1,
      "name": "Death's Wind",
      "location": "Glenumbra, Auridon, Stonefalls",
      "type": "Craftable",
      "slug": "deaths-wind",
      "bonus_item_1": null,
      "bonus_item_2": "Adds 2975 Physical Resistance",
      "bonus_item_3": "Adds 1206 Maximum Health",
      "bonus_item_4": "Adds 1206 Maximum Health",
      "bonus_item_5": "When you take melee damage while you are under 35% Health, you knockback and stun all enemies within 8 meters of you for 4 seconds. This effect can occur once every 30 seconds.",
      "has_jewels": 1,
      "has_weapons": 1,
      "has_heavy_armor": 1,
      "has_light_armor": 1,
      "has_medium_armor": 1,
      "traits_needed": 2
    }
]
```

This endpoint searches sets by name.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/sets/search`

### Query Parameters

Parameter | Description
--------- | -----------
query | A search query
