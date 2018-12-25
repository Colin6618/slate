---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - SDKAuthentication
  - errors

search: true
---

# Introduction

Welcome to the takemepay API! You can use our API to access takemepay API endpoints, which can get information on various cats, tokens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# TakeMe Pay Authentication

> To authorize, use this code:

```ruby
require 'takemepay'

api = takemepay::APIClient.authorize!('meowmeowmeow')
```

```python
import takemepay

api = takemepay.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const takemepay = require('takemepay');

let api = takemepay.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

takemepay uses API keys to allow access to the API. You can register a new takemepay API key at our [developer portal](http://example.com/developers).

takemepay expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# tokens

## Get All tokens

```ruby
require 'takemepay'

api = takemepay::APIClient.authorize!('meowmeowmeow')
api.tokens.get
```

```python
import takemepay

api = takemepay.authorize('meowmeowmeow')
api.tokens.get()
```

```shell
curl "http://example.com/api/tokens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const takemepay = require('takemepay');

let api = takemepay.authorize('meowmeowmeow');
let tokens = api.tokens.get();
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

This endpoint retrieves all tokens.

### HTTP Request

`GET http://example.com/api/tokens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include tokens that have already been adopted.

<aside class="success">
Remember — a happy token is an authenticated token!
</aside>

## Get a Specific token

```ruby
require 'takemepay'

api = takemepay::APIClient.authorize!('meowmeowmeow')
api.tokens.get(2)
```

```python
import takemepay

api = takemepay.authorize('meowmeowmeow')
api.tokens.get(2)
```

```shell
curl "http://example.com/api/tokens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const takemepay = require('takemepay');

let api = takemepay.authorize('meowmeowmeow');
let max = api.tokens.get(2);
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

This endpoint retrieves a specific token.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/tokens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the token to retrieve

## Delete a Specific token

```ruby
require 'takemepay'

api = takemepay::APIClient.authorize!('meowmeowmeow')
api.tokens.delete(2)
```

```python
import takemepay

api = takemepay.authorize('meowmeowmeow')
api.tokens.delete(2)
```

```shell
curl "http://example.com/api/tokens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const takemepay = require('takemepay');

let api = takemepay.authorize('meowmeowmeow');
let max = api.tokens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific token.

### HTTP Request

`DELETE http://example.com/tokens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the token to delete

