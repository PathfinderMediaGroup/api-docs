# Prices

## Search For Items

```php
<?php
    $searchQuery = 'runebox skin';
    $query = '?query='.urlencode($searchQuery);
    
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/eso/prices/search'.$query);
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    curl_setopt($ch, CURLOPT_CUSTOMREQUEST, 'GET');
    $output = curl_exec($ch);
    curl_close($ch);
    
    $items = json_decode($output);
?>
```

```json
[
    {
      "id": 37816,
      "name": "Runebox: Soul-Shriven Skin",
      "cleaned": "runebox: soul-shriven skin",
      "trait": null,
      "quality": "gold",
      "level": 1,
      "price": 641768.9,
      "server": "eu",
      "name_de": "Runenkiste: Seelenberaubter",
      "cleaned_de": "runenkiste: seelenberaubter",
      "name_fr": "Boîte Runique : Peau D'absous",
      "cleaned_fr": "boite runique : peau dabsous",
      "item_id": "18329"
    }, {
      "id": 85361,
      "name": "Runebox: Soul-Shriven Skin",
      "cleaned": "runebox: soul-shriven skin",
      "trait": null,
      "quality": "gold",
      "level": 1,
      "price": 622652.1,
      "server": "na",
      "name_de": "Runenkiste: Seelenberaubter",
      "cleaned_de": "runenkiste: seelenberaubter",
      "name_fr": "Boîte Runique : Peau D'absous",
      "cleaned_fr": "boite runique : peau dabsous",
      "item_id": "18329"
    }
]
```

This endpoint retrieves average prices for a search query.

This request can be used in two ways. The first is to specify the trait, quality and/or server of the search query in different parameters. This is allowed and will work. The second method is to simply leave everything in the query parameter. The server will automatically detected if traits/qualities/servers are mentioned in the query string.

**Valid values**

**Traits**:
`powered`, `charged`, `precise`, `infused`, `defending`,
`training`, `sharpened`, `decisive`, `sturdy`, `impenetrable`, `reinforced`,
`well-fitted`, `invigorating`, `divines`, `nirnhoned`, `intricate`, `ornate`, `arcane`,
`healthy`, `robust`, `bloodthirsty`, `harmony`, `protective`, `swift`, `triune`.

**Qualities**: `white`, `green`, `blue`, `purple`, `gold`.

**Languages**: `en`, `de`, `fr`.

Note that changing the language parameter will only affect the search by item name. Meaning that if you send `de` as a language parameter, your query string will be compared against German item names instead of English ones.

### HTTP Request

`GET https://beast.pathfindermediagroup.com/api/eso/prices/search`

### Query Parameters

Parameter | Description | Required | Default
--------- | ----------- | ----------- | -----------
query | A search query | Yes | 
trait | Item trait | No | null
quality | Item quality | No | null
lang | Language to search in | No | 'en'
