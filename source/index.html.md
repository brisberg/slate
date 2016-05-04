---
title: BetterWorks API

language_tabs:
  - shell: cURL
  - ruby: Ruby
  - python: Python

toc_footers:
  - <a href='#'>Sign Up for a BetterWorks Developer Key</a>
  - <a href='#'>Best API Ever</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors
  - keyresults

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/tripit/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('BWApiToken')
```

```python
import kittn

api = kittn.authorize('BWApiToken')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: BWApiToken"
```

> Make sure to replace `BWApiToken` with your API key.

BetterWorks uses API keys to allow access to the API. You can register a new BetterWorks API key at our [developer portal](http://example.com/developers).

BetterWorks expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: BWApiToken`

<aside class="notice">
You must replace <code>BWApiToken</code> with your personal API key.
</aside>

# Goals

## Get All Goals

```ruby
require 'bwapi'

api = BWAPI::APIClient.authorize!('BWApiToken')
api.kittens.get
```

```python
import bwapi

api = BWAPI.authorize('BWApiToken')
api.goals.get()
```

```shell
curl "http://example.com/api/goals"
  -H "Authorization: BWApiToken"
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

This endpoint retrieves all Goals.

### HTTP Request

`GET http://example.com/api/goals`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
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

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

