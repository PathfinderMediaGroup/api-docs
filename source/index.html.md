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

Welcome to the PMG API documentation. Here you can see examples on how to interact with our API. If you are using PHP check out our <a href="https://github.com/PathfinderMediaGroup/api-library">API Library package</a> to make your life easier.

# Authentication

> To check your authorization use this code:

```php
<?php
    $token = 'YourTokenHere';
    $ch = curl_init();
    curl_setopt($ch, CURLOPT_URL, 'https://beast.pathfindermediagroup.com/api/auth');
    $headers = [
        'Content-Type:application/json',
        'Authorization: Bearer '.$token,
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

`Authorization: Bearer YourTokenHere`

<aside class="notice">
You must replace <code>YourTokenHere</code> with your personal API key.
</aside>
