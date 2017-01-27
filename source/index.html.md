---
title: API Reference

language_tabs:
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Dragon API! You can use our API to access Dragon API endpoints, which can get information on various cats, Dragons, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'Dragon'

api = Dragon::APIClient.authorize!('woooo')
```

```python
import Dragon

api = Dragon.authorize('woooo')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: woooo"
```

```javascript
const Dragon = require('kittn');

let api = kittn.authorize('woooo');
```

> Make sure to replace `woooo` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: woooo`

<aside class="notice">
You must replace <code>woooo</code> with your personal API key.
</aside>

# Dragons

## Get All Dragons

```ruby
require 'Dragon'

api = Kittn::APIClient.authorize!('woooo')
api.Dragons.get
```

```python
import Dragon

api = kittn.authorize('woooo')
api.Dragons.get()
```

```shell
curl "http://example.com/api/dragons"
  -H "Authorization:woooo"
```

```javascript
const kittn = require('dragon');

let api = kittn.authorize('woooo');
let Dragons = api.dragons.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all dragons.

### HTTP Request

`GET http://example.com/api/dragons`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated dragons!
</aside>

## Get a Specific Dragon

```ruby
require 'Dragon'

api = Dragon::APIClient.authorize!('woooo')
api.kittens.get(2)
```

```python
import Dragon

api = Dragon.authorize('woooo')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/dragons/2"
  -H "Authorization: woooo"
```

```javascript
const Dragon = require('dragon');

let api = Dragon.authorize('woooo');
let max = api.dragons.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific dragon.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/dragons/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

