# Skills

## Get All Skills

```php
<?php
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/skills');
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $skills = json_decode($output);
?>
```

```json
[
    {
      "id": 18,
      "name": "Absorption Field",
      "skillline": 7,
      "parent": 13,
      "type": 3,
      "effect_1": "Create a globe of magic suppression, dispelling enemy placed effects instantly. Enemies within the globe are stunned for 12 seconds. Enemy players will be silenced rather than stunned.  The globe also heals you and your allies for 179 Health every 0.5 sec",
      "effect_2": "The globe also heals you and your allies standing inside it.",
      "cost": "225 Ultimate",
      "icon": "1n9PT4fpzCG9c7zAv3P5XA9F85Pzp4KgeOELxnnI.png",
      "pts": 0,
      "slug": "absorption-field",
      "cast_time": "Instant",
      "target": "Ground",
      "range": "28 meter range, 8 meter radius",
      "unlocks_at": 12
    }, {
      "id": 611,
      "name": "Accelerate",
      "skillline": 34,
      "parent": null,
      "type": 1,
      "effect_1": "Bend time and space around you to gain Major Expedition for 3 seconds and Minor Force for 12 seconds, increasing your Movement Speed by 30% and Critical Damage by 10%",
      "effect_2": null,
      "cost": "2984 Magicka",
      "icon": "pZFwm4BzeQWnWK0QjylHp0cIklT736HYdCrH9LEf.png",
      "pts": 0,
      "slug": "accelerate",
      "cast_time": "Instant, 12s duration",
      "target": "Self",
      "range": null,
      "unlocks_at": 5
    }
]
```

This endpoint retrieves all skills.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/skills`

## Get a Specific Skill

```php
<?php
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/skills/18');
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $skill = json_decode($output);
?>
```

```json
{
    "id": 18,
    "name": "Absorption Field",
    "skillline": 7,
    "parent": 13,
    "type": 3,
    "effect_1": "Create a globe of magic suppression, dispelling enemy placed effects instantly. Enemies within the globe are stunned for 12 seconds. Enemy players will be silenced rather than stunned.  The globe also heals you and your allies for 179 Health every 0.5 sec",
    "effect_2": "The globe also heals you and your allies standing inside it.",
    "cost": "225 Ultimate",
    "icon": "1n9PT4fpzCG9c7zAv3P5XA9F85Pzp4KgeOELxnnI.png",
    "pts": 0,
    "slug": "absorption-field",
    "cast_time": "Instant",
    "target": "Ground",
    "range": "28 meter range, 8 meter radius",
    "unlocks_at": 12
}
```

This endpoint retrieves a specific skill.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/skills/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the skill to retrieve

## Search for skills

```php
<?php
    $searchQuery = 'absorption';
    $query = '?query='.urlencode($searchQuery);
    
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/skills/search'.$query);
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $skills = json_decode($output);
?>
```

```json
[
    {
        "id": 18,
        "name": "Absorption Field",
        "skillline": 7,
        "parent": 13,
        "type": 3,
        "effect_1": "Create a globe of magic suppression, dispelling enemy placed effects instantly. Enemies within the globe are stunned for 12 seconds. Enemy players will be silenced rather than stunned.  The globe also heals you and your allies for 179 Health every 0.5 sec",
        "effect_2": "The globe also heals you and your allies standing inside it.",
        "cost": "225 Ultimate",
        "icon": "1n9PT4fpzCG9c7zAv3P5XA9F85Pzp4KgeOELxnnI.png",
        "pts": 0,
        "slug": "absorption-field",
        "cast_time": "Instant",
        "target": "Ground",
        "range": "28 meter range, 8 meter radius",
        "unlocks_at": 12
    }
]
```

This endpoint searches skills by name.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/skills/search`

### Query Parameters

Parameter | Description
--------- | -----------
query | A search query
