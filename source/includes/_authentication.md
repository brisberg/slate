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
