---
title: Pathfinder API

language_tabs: # must be one of https://git.io/vQNgJ
  - php
  - json

toc_footers:
  - <a href='https://discord.gg/woeler'>Get a developer key in our Discord</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - crownstoreitems
  - pledges
  - prices
  - servers
  - sets
  - skills
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To check your authorization use this code:

```php
<?php
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/auth');
    $headers = [
        'Content-Type:application/json',
        'Authorization: Basic '.base64_encode('YourTokenHere'),
        ];
    curl_setopt($ch, CURLOPT_HTTPHEADER, $headers);
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
    $output = curl_exec($ch);
    curl_close($ch);
?>
```

> Make sure to replace `YourTokenHere` with your API key.

The endpoint in the example above can be used to test your authorization process. It will return status code 200 on success, and 401 on failure.

The system expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Basic base64encodedtoken`

<aside class="notice">
You must replace <code>YourTokenHere</code> with your personal API key.
</aside>