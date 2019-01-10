# News Articles

## Get All Servers

```php
<?php
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/articles');
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $articles = json_decode($output);
?>
```

```json
[
    {
      "id": 573,
      "title": "Get ready for ESO’s Next Big Announcement ",
      "link": "https:\/\/www.elderscrollsonline.com\/en-us\/news\/post\/55495",
      "source": "artisan command",
      "channel": "eso-news",
      "pub_date": {
        "date": "2019-01-06 18:17:00.000000",
        "timezone_type": 3,
        "timezone": "UTC"
      },
      "date": "2019-01-06 19:20:07",
      "content": "The cat's out of bag! Ready yourself, adventurer. A massive announcement for The Elder Scrolls Online is on the way! Find out how you can learn about the upcoming ESO Chapter and what's coming to the game in 2019.",
      "image": "https:\/\/esosslfiles-a.akamaihd.net\/cms\/2019\/01\/995cca336e61a5f25928270de5ca8a65.jpg",
      "created_at": "2019-01-06 19:20:07",
      "updated_at": "2019-01-06 19:20:07"
    }, {
      "id": 575,
      "title": "Macht euch bereit für ESOs nächste große Ankündigung ",
      "link": "https:\/\/www.elderscrollsonline.com\/de\/news\/post\/55495",
      "source": "artisan command",
      "channel": "eso-news-german",
      "pub_date": {
        "date": "2019-01-06 18:17:00.000000",
        "timezone_type": 3,
        "timezone": "UTC"
      },
      "date": "2019-01-06 19:20:08",
      "content": "Die Katze ist aus dem Sack! Macht euch bereit, Abenteurer. Eine gewaltige Ankündigung für The Elder Scrolls Online steht an! Erfahrt mehr über das kommende Kapitel für ESO und was euch sonst noch 2019 im Spiel erwartet.",
      "image": "https:\/\/esosslfiles-a.akamaihd.net\/cms\/2019\/01\/761597fc043c946085f1994f41c6a114.jpg",
      "created_at": "2019-01-06 19:20:08",
      "updated_at": "2019-01-06 19:20:08"
    }
]
```

This endpoint retrieves ESO articles sorted by publish date (desc).

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/articles`

Parameter | Description | Required | Default | type
--------- | ----------- | ----------- | ----------- | -----------
limit | Size of the maximum result set | No | 25 | int
only | Limit the return list to only include these channels | No | null | array
exclude | Limit the return list to not include these channels | No | null | array