---
title: Agency API v2.0.9
language_tabs:
  - curl: Curl
  - csharp: CSharp
  - go: Go
  - http: HTTP
  - javascript: JavaScript
  - javascript--node: Node.JS
  - python: Python
  - ruby: Ruby
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="agency-api">Agency API v2.0.9</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

API Document of end-points required by agencies to set up voucher sales on their own websites

Email: <a href="mailto:toptiskish@gmail.com">TopTis.Ltd</a> Web: <a href="https://toptis.ir">TopTis.Ltd</a> 

# Authentication

- oAuth2 authentication. 

    - Flow: authorizationCode
    - Authorization URL = [https://api.touristpanel.ir/connect/authorize](https://api.touristpanel.ir/connect/authorize)
    - Token URL = [https://api.touristpanel.ir/connect/token](https://api.touristpanel.ir/connect/token)

|Scope|Scope Description|
|---|---|
|TouristPanel|TouristPanel API|

<h1 id="agency-api-reservation-entertainment">Reservation : Entertainment</h1>

## get__api_agency_reservation_entertainment_locations

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/agency/reservation/entertainment/locations";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/agency/reservation/entertainment/locations", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /api/agency/reservation/entertainment/locations HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/locations',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/agency/reservation/entertainment/locations', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/agency/reservation/entertainment/locations',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /api/agency/reservation/entertainment/locations`

*Get Active Locations*

> Example responses

> 200 Response

```
[{"code":"string","name":"string","native":"string"}]
```

```json
[
  {
    "code": "string",
    "name": "string",
    "native": "string"
  }
]
```

<h3 id="get__api_agency_reservation_entertainment_locations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="get__api_agency_reservation_entertainment_locations-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TopTis.TouristPanel.Core.Reservation.LocationDto](#schematoptis.touristpanel.core.reservation.locationdto)]|false|none|none|
|» code|string¦null|false|none|none|
|» name|string¦null|false|none|none|
|» native|string¦null|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## get__api_agency_reservation_entertainment_categories

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/agency/reservation/entertainment/categories";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/agency/reservation/entertainment/categories", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /api/agency/reservation/entertainment/categories HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/categories',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/agency/reservation/entertainment/categories', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/agency/reservation/entertainment/categories',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /api/agency/reservation/entertainment/categories`

*Get Active Categories*

<h3 id="get__api_agency_reservation_entertainment_categories-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|locationCode|query|string|false|none|

> Example responses

> 200 Response

```
[{"index":0,"code":0,"title":"string"}]
```

```json
[
  {
    "index": 0,
    "code": 0,
    "title": "string"
  }
]
```

<h3 id="get__api_agency_reservation_entertainment_categories-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="get__api_agency_reservation_entertainment_categories-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramCategoryDto](#schematoptis.touristpanel.core.reservation.entertainment.programcategorydto)]|false|none|none|
|» index|integer(int32)|false|none|none|
|» code|integer(int32)|false|none|none|
|» title|string¦null|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## get__api_agency_reservation_entertainment_programs

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/agency/reservation/entertainment/programs";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/agency/reservation/entertainment/programs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /api/agency/reservation/entertainment/programs HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/programs',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/agency/reservation/entertainment/programs', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/agency/reservation/entertainment/programs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /api/agency/reservation/entertainment/programs`

*Get List Of Active Programs*

<h3 id="get__api_agency_reservation_entertainment_programs-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|locationCode|query|string|false|none|
|categoryCodes|query|array[integer]|false|none|

> Example responses

> 200 Response

```
[{"programId":"bc59f66b-913a-48ec-ae2b-7ee29d7bcfbb","indexImageUrl":"string","title":"string"}]
```

```json
[
  {
    "programId": "bc59f66b-913a-48ec-ae2b-7ee29d7bcfbb",
    "indexImageUrl": "string",
    "title": "string"
  }
]
```

<h3 id="get__api_agency_reservation_entertainment_programs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="get__api_agency_reservation_entertainment_programs-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramDto](#schematoptis.touristpanel.core.reservation.entertainment.programdto)]|false|none|none|
|» programId|string(uuid)|false|none|none|
|» indexImageUrl|string¦null|false|none|none|
|» title|string¦null|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## get__api_agency_reservation_entertainment_program

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/agency/reservation/entertainment/program";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/agency/reservation/entertainment/program", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /api/agency/reservation/entertainment/program HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/program',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/agency/reservation/entertainment/program', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/agency/reservation/entertainment/program',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /api/agency/reservation/entertainment/program`

*Get Program Detail*

<h3 id="get__api_agency_reservation_entertainment_program-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|programId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"programId":"bc59f66b-913a-48ec-ae2b-7ee29d7bcfbb","title":"string","description":"string","rules":"string","indexImageUrl":"string","extraProperties":{"property1":null,"property2":null},"programCategory":{"index":0,"code":0,"title":"string"},"providers":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","title":"string","logo":"string","supportPhone":"string","address":"string","isCharter":true,"programIsPublic":true}],"location":{"code":"string","name":"string","native":"string"}}
```

```json
{
  "programId": "bc59f66b-913a-48ec-ae2b-7ee29d7bcfbb",
  "title": "string",
  "description": "string",
  "rules": "string",
  "indexImageUrl": "string",
  "extraProperties": {
    "property1": null,
    "property2": null
  },
  "programCategory": {
    "index": 0,
    "code": 0,
    "title": "string"
  },
  "providers": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "title": "string",
      "logo": "string",
      "supportPhone": "string",
      "address": "string",
      "isCharter": true,
      "programIsPublic": true
    }
  ],
  "location": {
    "code": "string",
    "name": "string",
    "native": "string"
  }
}
```

<h3 id="get__api_agency_reservation_entertainment_program-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramDetailDto](#schematoptis.touristpanel.core.reservation.entertainment.programdetaildto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="get__api_agency_reservation_entertainment_program-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## get__api_agency_reservation_entertainment_events

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/agency/reservation/entertainment/events";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/agency/reservation/entertainment/events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /api/agency/reservation/entertainment/events HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/events',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/agency/reservation/entertainment/events', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/agency/reservation/entertainment/events',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /api/agency/reservation/entertainment/events`

*Get Program's Events*

<h3 id="get__api_agency_reservation_entertainment_events-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|providerAppId|query|string(uuid)|false|none|
|programId|query|string(uuid)|false|none|
|start|query|string(date-time)|false|none|
|end|query|string(date-time)|false|none|

> Example responses

> 200 Response

```
[{"date":"string","events":[{"excuteTime":"2019-08-24T14:15:22Z","eventId":"d6703cc8-9e79-415d-ac03-a4dc7f6ab43c","start":"string","end":"string","endReservation":"string","label":"string","description":"string","capacity":0,"isVisible":true}]}]
```

```json
[
  {
    "date": "string",
    "events": [
      {
        "excuteTime": "2019-08-24T14:15:22Z",
        "eventId": "d6703cc8-9e79-415d-ac03-a4dc7f6ab43c",
        "start": "string",
        "end": "string",
        "endReservation": "string",
        "label": "string",
        "description": "string",
        "capacity": 0,
        "isVisible": true
      }
    ]
  }
]
```

<h3 id="get__api_agency_reservation_entertainment_events-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="get__api_agency_reservation_entertainment_events-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TopTis.TouristPanel.Core.Reservation.Entertainment.EventListDto](#schematoptis.touristpanel.core.reservation.entertainment.eventlistdto)]|false|none|none|
|» date|string¦null|false|none|none|
|» events|[[TopTis.TouristPanel.Core.Reservation.Entertainment.EventDto](#schematoptis.touristpanel.core.reservation.entertainment.eventdto)]¦null|false|none|none|
|»» excuteTime|string(date-time)|false|none|none|
|»» eventId|string(uuid)|false|none|none|
|»» start|string¦null|false|none|none|
|»» end|string¦null|false|none|none|
|»» endReservation|string¦null|false|none|none|
|»» label|string¦null|false|none|none|
|»» description|string¦null|false|none|none|
|»» capacity|integer(int32)|false|none|none|
|»» isVisible|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## get__api_agency_reservation_entertainment_event-ticket-types

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/agency/reservation/entertainment/event-ticket-types";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/agency/reservation/entertainment/event-ticket-types", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /api/agency/reservation/entertainment/event-ticket-types HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/event-ticket-types',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/agency/reservation/entertainment/event-ticket-types', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/agency/reservation/entertainment/event-ticket-types',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /api/agency/reservation/entertainment/event-ticket-types`

*GetEventsTicketTypes*

<h3 id="get__api_agency_reservation_entertainment_event-ticket-types-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|providerAppId|query|string(uuid)|false|none|
|eventId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
[{"eventTicketTypeId":"a3d07f45-12e7-47fa-ac5b-d0728d2a60ae","title":"string","description":"string","capacity":0,"ticketPrice":0,"buyPrice":0,"commissionPrice":0}]
```

```json
[
  {
    "eventTicketTypeId": "a3d07f45-12e7-47fa-ac5b-d0728d2a60ae",
    "title": "string",
    "description": "string",
    "capacity": 0,
    "ticketPrice": 0,
    "buyPrice": 0,
    "commissionPrice": 0
  }
]
```

<h3 id="get__api_agency_reservation_entertainment_event-ticket-types-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="get__api_agency_reservation_entertainment_event-ticket-types-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TopTis.TouristPanel.Core.Reservation.Entertainment.TicketTypeDto](#schematoptis.touristpanel.core.reservation.entertainment.tickettypedto)]|false|none|none|
|» eventTicketTypeId|string(uuid)|false|none|none|
|» title|string¦null|false|none|none|
|» description|string¦null|false|none|none|
|» capacity|integer(int32)|false|none|none|
|» ticketPrice|integer(int32)|false|none|none|
|» buyPrice|integer(int32)|false|none|none|
|» commissionPrice|integer(int32)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## post__api_agency_reservation_entertainment_add-temp-vouchers

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/agency/reservation/entertainment/add-temp-vouchers";
      
      string json = @"{
  ""providerAppId"": ""7b99990f-bbdc-4931-a372-b70f7ae94ddb"",
  ""eventId"": ""d6703cc8-9e79-415d-ac03-a4dc7f6ab43c"",
  ""ticketTypes"": [
    {
      ""eventTicketTypeId"": ""a3d07f45-12e7-47fa-ac5b-d0728d2a60ae"",
      ""count"": 0
    }
  ]
}";
      TopTis.TouristPanel.Core.Reservation.AddTempVoucherDto content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(TopTis.TouristPanel.Core.Reservation.AddTempVoucherDto content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(TopTis.TouristPanel.Core.Reservation.AddTempVoucherDto content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/agency/reservation/entertainment/add-temp-vouchers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
POST /api/agency/reservation/entertainment/add-temp-vouchers HTTP/1.1

Content-Type: application/json
Accept: text/plain

```

```javascript
const inputBody = '{
  "providerAppId": "7b99990f-bbdc-4931-a372-b70f7ae94ddb",
  "eventId": "d6703cc8-9e79-415d-ac03-a4dc7f6ab43c",
  "ticketTypes": [
    {
      "eventTicketTypeId": "a3d07f45-12e7-47fa-ac5b-d0728d2a60ae",
      "count": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/add-temp-vouchers',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/agency/reservation/entertainment/add-temp-vouchers', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/agency/reservation/entertainment/add-temp-vouchers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /api/agency/reservation/entertainment/add-temp-vouchers`

*AddTempVouchers*

> Body parameter

```json
{
  "providerAppId": "7b99990f-bbdc-4931-a372-b70f7ae94ddb",
  "eventId": "d6703cc8-9e79-415d-ac03-a4dc7f6ab43c",
  "ticketTypes": [
    {
      "eventTicketTypeId": "a3d07f45-12e7-47fa-ac5b-d0728d2a60ae",
      "count": 0
    }
  ]
}
```

<h3 id="post__api_agency_reservation_entertainment_add-temp-vouchers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|basketId|query|string(uuid)|false|none|
|body|body|[TopTis.TouristPanel.Core.Reservation.AddTempVoucherDto](#schematoptis.touristpanel.core.reservation.addtempvoucherdto)|false|none|

> Example responses

> 200 Response

```
{"basketId":"de1bcc32-c8ef-4097-ac69-c99a222050f2","basketGroup":{"groupReference":"string","title":"string","description":"string","expireDateTime":"2019-08-24T14:15:22Z","providerApp":null,"entertainment":[{"id":"497f6eca-6276-4993-bfeb-53cbbbba6f08","eventTicketTypeTitle":"string","count":0,"totalTicketPrice":0,"totalBuyPrice":0,"totalCommissionPrice":0,"providerDiscountAmount":0,"agencyDiscountAmount":0}]}}
```

```json
{
  "basketId": "de1bcc32-c8ef-4097-ac69-c99a222050f2",
  "basketGroup": {
    "groupReference": "string",
    "title": "string",
    "description": "string",
    "expireDateTime": "2019-08-24T14:15:22Z",
    "providerApp": null,
    "entertainment": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "eventTicketTypeTitle": "string",
        "count": 0,
        "totalTicketPrice": 0,
        "totalBuyPrice": 0,
        "totalCommissionPrice": 0,
        "providerDiscountAmount": 0,
        "agencyDiscountAmount": 0
      }
    ]
  }
}
```

<h3 id="post__api_agency_reservation_entertainment_add-temp-vouchers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[TopTis.TouristPanel.Core.Reservation.TempVoucherBasketDto](#schematoptis.touristpanel.core.reservation.tempvoucherbasketdto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="post__api_agency_reservation_entertainment_add-temp-vouchers-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## delete__api_agency_reservation_entertainment_remove-temp-vouchers

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    
    
    /// Make a dummy request
    public async Task MakeDeleteRequest()
    {
      int id = 1;
      string url = "/api/agency/reservation/entertainment/remove-temp-vouchers";

      await DeleteAsync(id, url);
    }

    /// Performs a DELETE Request
    public async Task DeleteAsync(int id, string url)
    {
        //Execute DELETE request
        HttpResponseMessage response = await Client.DeleteAsync(url + $"/{id}");

        //Return response
        await DeserializeObject(response);
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "/api/agency/reservation/entertainment/remove-temp-vouchers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
DELETE /api/agency/reservation/entertainment/remove-temp-vouchers HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/remove-temp-vouchers',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('/api/agency/reservation/entertainment/remove-temp-vouchers', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete '/api/agency/reservation/entertainment/remove-temp-vouchers',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`DELETE /api/agency/reservation/entertainment/remove-temp-vouchers`

*RemoveTempVouchers*

One of the parameters is essential

<h3 id="delete__api_agency_reservation_entertainment_remove-temp-vouchers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tempVoucherId|query|string(uuid)|false|none|
|basketId|query|string(uuid)|false|none|
|groupReference|query|string|false|none|

> Example responses

> 200 Response

```
true
```

```json
true
```

<h3 id="delete__api_agency_reservation_entertainment_remove-temp-vouchers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|boolean|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="delete__api_agency_reservation_entertainment_remove-temp-vouchers-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## post__api_agency_reservation_entertainment_create-temp-invoice

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/agency/reservation/entertainment/create-temp-invoice";
      
      string json = @"{
  ""tempVouchers"": [
    {
      ""id"": ""497f6eca-6276-4993-bfeb-53cbbbba6f08"",
      ""agencyDiscountAmount"": 0
    }
  ],
  ""purchaseType"": 1,
  ""customerFullName"": ""string"",
  ""customerMobile"": ""string"",
  ""customerAddress"": ""string"",
  ""internalTrackingCode"": ""string"",
  ""description"": ""string"",
  ""totalAgencyDiscount"": 0
}";
      TopTis.TouristPanel.Core.Reservation.CreateTempInvoiceDto content = JsonConvert.DeserializeObject(json);
      await PostAsync(content, url);
      
      
    }

    /// Performs a POST Request
    public async Task PostAsync(TopTis.TouristPanel.Core.Reservation.CreateTempInvoiceDto content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(TopTis.TouristPanel.Core.Reservation.CreateTempInvoiceDto content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/agency/reservation/entertainment/create-temp-invoice", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
POST /api/agency/reservation/entertainment/create-temp-invoice HTTP/1.1

Content-Type: application/json
Accept: text/plain

```

```javascript
const inputBody = '{
  "tempVouchers": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "agencyDiscountAmount": 0
    }
  ],
  "purchaseType": 1,
  "customerFullName": "string",
  "customerMobile": "string",
  "customerAddress": "string",
  "internalTrackingCode": "string",
  "description": "string",
  "totalAgencyDiscount": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/create-temp-invoice',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/agency/reservation/entertainment/create-temp-invoice', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/agency/reservation/entertainment/create-temp-invoice',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /api/agency/reservation/entertainment/create-temp-invoice`

*CreateTempInvoice*

> Body parameter

```json
{
  "tempVouchers": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "agencyDiscountAmount": 0
    }
  ],
  "purchaseType": 1,
  "customerFullName": "string",
  "customerMobile": "string",
  "customerAddress": "string",
  "internalTrackingCode": "string",
  "description": "string",
  "totalAgencyDiscount": 0
}
```

<h3 id="post__api_agency_reservation_entertainment_create-temp-invoice-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|basketId|query|string(uuid)|false|none|
|body|body|[TopTis.TouristPanel.Core.Reservation.CreateTempInvoiceDto](#schematoptis.touristpanel.core.reservation.createtempinvoicedto)|false|none|

> Example responses

> 200 Response

```
{"jobId":"string","basketId":"de1bcc32-c8ef-4097-ac69-c99a222050f2","purchaseStatus":1,"purchaseType":1,"createDateTime":"2019-08-24T14:15:22Z","tempInvoiceExpireTime":"2019-08-24T14:15:22Z","vouchersUrl":"string","invoiceUrl":"string","gatewayUrl":"string","customerFullName":"string","reservationReference":"string","message":"string","status":true}
```

```json
{
  "jobId": "string",
  "basketId": "de1bcc32-c8ef-4097-ac69-c99a222050f2",
  "purchaseStatus": 1,
  "purchaseType": 1,
  "createDateTime": "2019-08-24T14:15:22Z",
  "tempInvoiceExpireTime": "2019-08-24T14:15:22Z",
  "vouchersUrl": "string",
  "invoiceUrl": "string",
  "gatewayUrl": "string",
  "customerFullName": "string",
  "reservationReference": "string",
  "message": "string",
  "status": true
}
```

<h3 id="post__api_agency_reservation_entertainment_create-temp-invoice-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[TopTis.TouristPanel.Core.Reservation.TempInvoiceResultDto](#schematoptis.touristpanel.core.reservation.tempinvoiceresultdto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="post__api_agency_reservation_entertainment_create-temp-invoice-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## post__api_agency_reservation_entertainment_pay-temp-invoice

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    
    /// Make a dummy request
    public async Task MakePostRequest()
    {
      string url = "/api/agency/reservation/entertainment/pay-temp-invoice";
      
      
      await PostAsync(null, url);
      
    }

    /// Performs a POST Request
    public async Task PostAsync(undefined content, string url)
    {
        //Serialize Object
        StringContent jsonContent = SerializeObject(content);

        //Execute POST request
        HttpResponseMessage response = await Client.PostAsync(url, jsonContent);
    }
    
    
    
    /// Serialize an object to Json
    private StringContent SerializeObject(undefined content)
    {
        //Serialize Object
        string jsonObject = JsonConvert.SerializeObject(content);

        //Create Json UTF8 String Content
        return new StringContent(jsonObject, Encoding.UTF8, "application/json");
    }
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/api/agency/reservation/entertainment/pay-temp-invoice", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
POST /api/agency/reservation/entertainment/pay-temp-invoice HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/pay-temp-invoice',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/api/agency/reservation/entertainment/pay-temp-invoice', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/api/agency/reservation/entertainment/pay-temp-invoice',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`POST /api/agency/reservation/entertainment/pay-temp-invoice`

*PayTempInvoice*

Pay Temperory Invoice From Credit Or Wallet

<h3 id="post__api_agency_reservation_entertainment_pay-temp-invoice-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|basketId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"jobId":"string","basketId":"de1bcc32-c8ef-4097-ac69-c99a222050f2","purchaseStatus":1,"purchaseType":1,"createDateTime":"2019-08-24T14:15:22Z","tempInvoiceExpireTime":"2019-08-24T14:15:22Z","vouchersUrl":"string","invoiceUrl":"string","gatewayUrl":"string","customerFullName":"string","reservationReference":"string","message":"string","status":true}
```

```json
{
  "jobId": "string",
  "basketId": "de1bcc32-c8ef-4097-ac69-c99a222050f2",
  "purchaseStatus": 1,
  "purchaseType": 1,
  "createDateTime": "2019-08-24T14:15:22Z",
  "tempInvoiceExpireTime": "2019-08-24T14:15:22Z",
  "vouchersUrl": "string",
  "invoiceUrl": "string",
  "gatewayUrl": "string",
  "customerFullName": "string",
  "reservationReference": "string",
  "message": "string",
  "status": true
}
```

<h3 id="post__api_agency_reservation_entertainment_pay-temp-invoice-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[TopTis.TouristPanel.Core.Reservation.TempInvoiceResultDto](#schematoptis.touristpanel.core.reservation.tempinvoiceresultdto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="post__api_agency_reservation_entertainment_pay-temp-invoice-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

## get__api_agency_reservation_entertainment_get-reservation-result

> Code samples

```csharp
using System;
using System.Collections.Generic;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
using Newtonsoft.Json;

/// <<summary>>
/// Example of Http Client
/// <</summary>>
public class HttpExample
{
    private HttpClient Client { get; set; }

    /// <<summary>>
    /// Setup http client
    /// <</summary>>
    public HttpExample()
    {
      Client = new HttpClient();
    }
    
    /// Make a dummy request
    public async Task MakeGetRequest()
    {
      string url = "/api/agency/reservation/entertainment/get-reservation-result";
      var result = await GetAsync(url);
    }

    /// Performs a GET Request
    public async Task GetAsync(string url)
    {
        //Start the request
        HttpResponseMessage response = await Client.GetAsync(url);

        //Validate result
        response.EnsureSuccessStatusCode();

    }
    
    
    
    
    /// Deserialize object from request response
    private async Task DeserializeObject(HttpResponseMessage response)
    {
        //Read body 
        string responseBody = await response.Content.ReadAsStringAsync();

        //Deserialize Body to object
        var result = JsonConvert.DeserializeObject(responseBody);
    }
}

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"text/plain"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/api/agency/reservation/entertainment/get-reservation-result", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /api/agency/reservation/entertainment/get-reservation-result HTTP/1.1

Accept: text/plain

```

```javascript

const headers = {
  'Accept':'text/plain',
  'Authorization':'Bearer {access-token}'
};

fetch('/api/agency/reservation/entertainment/get-reservation-result',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```python
import requests
headers = {
  'Accept': 'text/plain',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/api/agency/reservation/entertainment/get-reservation-result', headers = headers)

print(r.json())

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/plain',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/api/agency/reservation/entertainment/get-reservation-result',
  params: {
  }, headers: headers

p JSON.parse(result)

```

`GET /api/agency/reservation/entertainment/get-reservation-result`

*GetReservationResult*

Checking Voucher Status After Creating A Temperory Invoice

<h3 id="get__api_agency_reservation_entertainment_get-reservation-result-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|basketId|query|string(uuid)|false|none|

> Example responses

> 200 Response

```
{"basketId":"de1bcc32-c8ef-4097-ac69-c99a222050f2","purchaseStatus":1,"purchaseType":1,"vouchersUrl":"string","invoiceUrl":"string","customerFullName":"string","customerMobile":"string","reservationReference":"string","message":"string","status":true}
```

```json
{
  "basketId": "de1bcc32-c8ef-4097-ac69-c99a222050f2",
  "purchaseStatus": 1,
  "purchaseType": 1,
  "vouchersUrl": "string",
  "invoiceUrl": "string",
  "customerFullName": "string",
  "customerMobile": "string",
  "reservationReference": "string",
  "message": "string",
  "status": true
}
```

<h3 id="get__api_agency_reservation_entertainment_get-reservation-result-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[TopTis.TouristPanel.Core.Reservation.ReservationResultDto](#schematoptis.touristpanel.core.reservation.reservationresultdto)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Error|None|
|501|[Not Implemented](https://tools.ietf.org/html/rfc7231#section-6.6.2)|Server Error|None|

<h3 id="get__api_agency_reservation_entertainment_get-reservation-result-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2
</aside>

# Schemas

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.AddTempVoucherDto">TopTis.TouristPanel.Core.Reservation.AddTempVoucherDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.addtempvoucherdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.AddTempVoucherDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.addtempvoucherdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.addtempvoucherdto"></a>

```json
{
  "providerAppId": "7b99990f-bbdc-4931-a372-b70f7ae94ddb",
  "eventId": "d6703cc8-9e79-415d-ac03-a4dc7f6ab43c",
  "ticketTypes": [
    {
      "eventTicketTypeId": "a3d07f45-12e7-47fa-ac5b-d0728d2a60ae",
      "count": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|providerAppId|string(uuid)|false|none|none|
|eventId|string(uuid)|false|none|none|
|ticketTypes|[[TopTis.TouristPanel.Core.Reservation.AddTempVoucherTicketTypeDto](#schematoptis.touristpanel.core.reservation.addtempvouchertickettypedto)]¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.AddTempVoucherTicketTypeDto">TopTis.TouristPanel.Core.Reservation.AddTempVoucherTicketTypeDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.addtempvouchertickettypedto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.AddTempVoucherTicketTypeDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.addtempvouchertickettypedto"></a>
<a id="tocstoptis.touristpanel.core.reservation.addtempvouchertickettypedto"></a>

```json
{
  "eventTicketTypeId": "a3d07f45-12e7-47fa-ac5b-d0728d2a60ae",
  "count": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|eventTicketTypeId|string(uuid)|false|none|none|
|count|integer(int32)|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.BasketGroupDto">TopTis.TouristPanel.Core.Reservation.BasketGroupDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.basketgroupdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.BasketGroupDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.basketgroupdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.basketgroupdto"></a>

```json
{
  "groupReference": "string",
  "title": "string",
  "description": "string",
  "expireDateTime": "2019-08-24T14:15:22Z",
  "providerApp": null,
  "entertainment": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "eventTicketTypeTitle": "string",
      "count": 0,
      "totalTicketPrice": 0,
      "totalBuyPrice": 0,
      "totalCommissionPrice": 0,
      "providerDiscountAmount": 0,
      "agencyDiscountAmount": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|groupReference|string¦null|false|none|none|
|title|string¦null|false|none|none|
|description|string¦null|false|none|none|
|expireDateTime|string(date-time)|false|none|none|
|providerApp|[TopTis.TouristPanel.Core.Applications.AppDto](#schematoptis.touristpanel.core.applications.appdto)|false|none|none|
|entertainment|[[TopTis.TouristPanel.Core.Reservation.EntertainmentTempVoucherDetailDto](#schematoptis.touristpanel.core.reservation.entertainmenttempvoucherdetaildto)]¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.CreateTempInvoiceDto">TopTis.TouristPanel.Core.Reservation.CreateTempInvoiceDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.createtempinvoicedto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.CreateTempInvoiceDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.createtempinvoicedto"></a>
<a id="tocstoptis.touristpanel.core.reservation.createtempinvoicedto"></a>

```json
{
  "tempVouchers": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "agencyDiscountAmount": 0
    }
  ],
  "purchaseType": 1,
  "customerFullName": "string",
  "customerMobile": "string",
  "customerAddress": "string",
  "internalTrackingCode": "string",
  "description": "string",
  "totalAgencyDiscount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|tempVouchers|[[TopTis.TouristPanel.Core.Reservation.TempVoucherDto](#schematoptis.touristpanel.core.reservation.tempvoucherdto)]¦null|false|none|none|
|purchaseType|[TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseType](#schematoptis.touristpanel.core.reservation.vouchers.purchasetype)|false|none|none|
|customerFullName|string¦null|false|none|none|
|customerMobile|string¦null|false|none|none|
|customerAddress|string¦null|false|none|none|
|internalTrackingCode|string¦null|false|none|none|
|description|string¦null|false|none|none|
|totalAgencyDiscount|integer(int32)|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Entertainment.EventDto">TopTis.TouristPanel.Core.Reservation.Entertainment.EventDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.entertainment.eventdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Entertainment.EventDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.entertainment.eventdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.entertainment.eventdto"></a>

```json
{
  "excuteTime": "2019-08-24T14:15:22Z",
  "eventId": "d6703cc8-9e79-415d-ac03-a4dc7f6ab43c",
  "start": "string",
  "end": "string",
  "endReservation": "string",
  "label": "string",
  "description": "string",
  "capacity": 0,
  "isVisible": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|excuteTime|string(date-time)|false|none|none|
|eventId|string(uuid)|false|none|none|
|start|string¦null|false|none|none|
|end|string¦null|false|none|none|
|endReservation|string¦null|false|none|none|
|label|string¦null|false|none|none|
|description|string¦null|false|none|none|
|capacity|integer(int32)|false|none|none|
|isVisible|boolean|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Entertainment.EventListDto">TopTis.TouristPanel.Core.Reservation.Entertainment.EventListDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.entertainment.eventlistdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Entertainment.EventListDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.entertainment.eventlistdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.entertainment.eventlistdto"></a>

```json
{
  "date": "string",
  "events": [
    {
      "excuteTime": "2019-08-24T14:15:22Z",
      "eventId": "d6703cc8-9e79-415d-ac03-a4dc7f6ab43c",
      "start": "string",
      "end": "string",
      "endReservation": "string",
      "label": "string",
      "description": "string",
      "capacity": 0,
      "isVisible": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|date|string¦null|false|none|none|
|events|[[TopTis.TouristPanel.Core.Reservation.Entertainment.EventDto](#schematoptis.touristpanel.core.reservation.entertainment.eventdto)]¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramCategoryDto">TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramCategoryDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.entertainment.programcategorydto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramCategoryDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.entertainment.programcategorydto"></a>
<a id="tocstoptis.touristpanel.core.reservation.entertainment.programcategorydto"></a>

```json
{
  "index": 0,
  "code": 0,
  "title": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|index|integer(int32)|false|none|none|
|code|integer(int32)|false|none|none|
|title|string¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramDetailDto">TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramDetailDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.entertainment.programdetaildto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramDetailDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.entertainment.programdetaildto"></a>
<a id="tocstoptis.touristpanel.core.reservation.entertainment.programdetaildto"></a>

```json
{
  "programId": "bc59f66b-913a-48ec-ae2b-7ee29d7bcfbb",
  "title": "string",
  "description": "string",
  "rules": "string",
  "indexImageUrl": "string",
  "extraProperties": {
    "property1": null,
    "property2": null
  },
  "programCategory": {
    "index": 0,
    "code": 0,
    "title": "string"
  },
  "providers": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "title": "string",
      "logo": "string",
      "supportPhone": "string",
      "address": "string",
      "isCharter": true,
      "programIsPublic": true
    }
  ],
  "location": {
    "code": "string",
    "name": "string",
    "native": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|programId|string(uuid)|false|none|none|
|title|string¦null|false|none|none|
|description|string¦null|false|none|none|
|rules|string¦null|false|none|none|
|indexImageUrl|string¦null|false|none|none|
|extraProperties|object¦null|false|none|none|
|» **additionalProperties**|any|false|none|none|
|programCategory|[TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramCategoryDto](#schematoptis.touristpanel.core.reservation.entertainment.programcategorydto)|false|none|none|
|providers|[[TopTis.TouristPanel.Core.Reservation.Entertainment.ProviderDto](#schematoptis.touristpanel.core.reservation.entertainment.providerdto)]¦null|false|none|none|
|location|[TopTis.TouristPanel.Core.Reservation.LocationDto](#schematoptis.touristpanel.core.reservation.locationdto)|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramDto">TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.entertainment.programdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Entertainment.ProgramDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.entertainment.programdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.entertainment.programdto"></a>

```json
{
  "programId": "bc59f66b-913a-48ec-ae2b-7ee29d7bcfbb",
  "indexImageUrl": "string",
  "title": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|programId|string(uuid)|false|none|none|
|indexImageUrl|string¦null|false|none|none|
|title|string¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Entertainment.ProviderDto">TopTis.TouristPanel.Core.Reservation.Entertainment.ProviderDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.entertainment.providerdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Entertainment.ProviderDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.entertainment.providerdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.entertainment.providerdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "title": "string",
  "logo": "string",
  "supportPhone": "string",
  "address": "string",
  "isCharter": true,
  "programIsPublic": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|title|string¦null|false|none|none|
|logo|string¦null|false|none|none|
|supportPhone|string¦null|false|none|none|
|address|string¦null|false|none|none|
|isCharter|boolean|false|none|none|
|programIsPublic|boolean|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Entertainment.TicketTypeDto">TopTis.TouristPanel.Core.Reservation.Entertainment.TicketTypeDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.entertainment.tickettypedto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Entertainment.TicketTypeDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.entertainment.tickettypedto"></a>
<a id="tocstoptis.touristpanel.core.reservation.entertainment.tickettypedto"></a>

```json
{
  "eventTicketTypeId": "a3d07f45-12e7-47fa-ac5b-d0728d2a60ae",
  "title": "string",
  "description": "string",
  "capacity": 0,
  "ticketPrice": 0,
  "buyPrice": 0,
  "commissionPrice": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|eventTicketTypeId|string(uuid)|false|none|none|
|title|string¦null|false|none|none|
|description|string¦null|false|none|none|
|capacity|integer(int32)|false|none|none|
|ticketPrice|integer(int32)|false|none|none|
|buyPrice|integer(int32)|false|none|none|
|commissionPrice|integer(int32)|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.EntertainmentTempVoucherDetailDto">TopTis.TouristPanel.Core.Reservation.EntertainmentTempVoucherDetailDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.entertainmenttempvoucherdetaildto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.EntertainmentTempVoucherDetailDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.entertainmenttempvoucherdetaildto"></a>
<a id="tocstoptis.touristpanel.core.reservation.entertainmenttempvoucherdetaildto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "eventTicketTypeTitle": "string",
  "count": 0,
  "totalTicketPrice": 0,
  "totalBuyPrice": 0,
  "totalCommissionPrice": 0,
  "providerDiscountAmount": 0,
  "agencyDiscountAmount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|eventTicketTypeTitle|string¦null|false|none|none|
|count|integer(int32)|false|none|none|
|totalTicketPrice|integer(int32)|false|none|none|
|totalBuyPrice|integer(int32)|false|none|none|
|totalCommissionPrice|integer(int32)|false|none|none|
|providerDiscountAmount|integer(int32)|false|none|none|
|agencyDiscountAmount|integer(int32)|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.LocationDto">TopTis.TouristPanel.Core.Reservation.LocationDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.locationdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.LocationDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.locationdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.locationdto"></a>

```json
{
  "code": "string",
  "name": "string",
  "native": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string¦null|false|none|none|
|name|string¦null|false|none|none|
|native|string¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.ReservationResultDto">TopTis.TouristPanel.Core.Reservation.ReservationResultDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.reservationresultdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.ReservationResultDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.reservationresultdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.reservationresultdto"></a>

```json
{
  "basketId": "de1bcc32-c8ef-4097-ac69-c99a222050f2",
  "purchaseStatus": 1,
  "purchaseType": 1,
  "vouchersUrl": "string",
  "invoiceUrl": "string",
  "customerFullName": "string",
  "customerMobile": "string",
  "reservationReference": "string",
  "message": "string",
  "status": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|basketId|string(uuid)|false|none|none|
|purchaseStatus|[TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseStatus](#schematoptis.touristpanel.core.reservation.vouchers.purchasestatus)|false|none|none|
|purchaseType|[TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseType](#schematoptis.touristpanel.core.reservation.vouchers.purchasetype)|false|none|none|
|vouchersUrl|string¦null|false|none|none|
|invoiceUrl|string¦null|false|none|none|
|customerFullName|string¦null|false|none|none|
|customerMobile|string¦null|false|none|none|
|reservationReference|string¦null|false|none|none|
|message|string¦null|false|none|none|
|status|boolean|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.TempInvoiceResultDto">TopTis.TouristPanel.Core.Reservation.TempInvoiceResultDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.tempinvoiceresultdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.TempInvoiceResultDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.tempinvoiceresultdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.tempinvoiceresultdto"></a>

```json
{
  "jobId": "string",
  "basketId": "de1bcc32-c8ef-4097-ac69-c99a222050f2",
  "purchaseStatus": 1,
  "purchaseType": 1,
  "createDateTime": "2019-08-24T14:15:22Z",
  "tempInvoiceExpireTime": "2019-08-24T14:15:22Z",
  "vouchersUrl": "string",
  "invoiceUrl": "string",
  "gatewayUrl": "string",
  "customerFullName": "string",
  "reservationReference": "string",
  "message": "string",
  "status": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jobId|string¦null|false|none|none|
|basketId|string(uuid)|false|none|none|
|purchaseStatus|[TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseStatus](#schematoptis.touristpanel.core.reservation.vouchers.purchasestatus)|false|none|none|
|purchaseType|[TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseType](#schematoptis.touristpanel.core.reservation.vouchers.purchasetype)|false|none|none|
|createDateTime|string(date-time)|false|none|none|
|tempInvoiceExpireTime|string(date-time)|false|none|none|
|vouchersUrl|string¦null|false|none|none|
|invoiceUrl|string¦null|false|none|none|
|gatewayUrl|string¦null|false|none|none|
|customerFullName|string¦null|false|none|none|
|reservationReference|string¦null|false|none|none|
|message|string¦null|false|none|none|
|status|boolean|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.TempVoucherBasketDto">TopTis.TouristPanel.Core.Reservation.TempVoucherBasketDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.tempvoucherbasketdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.TempVoucherBasketDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.tempvoucherbasketdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.tempvoucherbasketdto"></a>

```json
{
  "basketId": "de1bcc32-c8ef-4097-ac69-c99a222050f2",
  "basketGroup": {
    "groupReference": "string",
    "title": "string",
    "description": "string",
    "expireDateTime": "2019-08-24T14:15:22Z",
    "providerApp": null,
    "entertainment": [
      {
        "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
        "eventTicketTypeTitle": "string",
        "count": 0,
        "totalTicketPrice": 0,
        "totalBuyPrice": 0,
        "totalCommissionPrice": 0,
        "providerDiscountAmount": 0,
        "agencyDiscountAmount": 0
      }
    ]
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|basketId|string(uuid)|false|none|none|
|basketGroup|[TopTis.TouristPanel.Core.Reservation.BasketGroupDto](#schematoptis.touristpanel.core.reservation.basketgroupdto)|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.TempVoucherDto">TopTis.TouristPanel.Core.Reservation.TempVoucherDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.tempvoucherdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.TempVoucherDto"></a>
<a id="tocStoptis.touristpanel.core.reservation.tempvoucherdto"></a>
<a id="tocstoptis.touristpanel.core.reservation.tempvoucherdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "agencyDiscountAmount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|agencyDiscountAmount|integer(int32)|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseStatus">TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseStatus</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.vouchers.purchasestatus"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseStatus"></a>
<a id="tocStoptis.touristpanel.core.reservation.vouchers.purchasestatus"></a>
<a id="tocstoptis.touristpanel.core.reservation.vouchers.purchasestatus"></a>

```json
1

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|
|*anonymous*|4|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseType">TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseType</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.vouchers.purchasetype"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Vouchers.PurchaseType"></a>
<a id="tocStoptis.touristpanel.core.reservation.vouchers.purchasetype"></a>
<a id="tocstoptis.touristpanel.core.reservation.vouchers.purchasetype"></a>

```json
1

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherFinancialTransactionType">TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherFinancialTransactionType</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.vouchers.voucherfinancialtransactiontype"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherFinancialTransactionType"></a>
<a id="tocStoptis.touristpanel.core.reservation.vouchers.voucherfinancialtransactiontype"></a>
<a id="tocstoptis.touristpanel.core.reservation.vouchers.voucherfinancialtransactiontype"></a>

```json
1

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|2|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherState">TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherState</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.vouchers.voucherstate"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherState"></a>
<a id="tocStoptis.touristpanel.core.reservation.vouchers.voucherstate"></a>
<a id="tocstoptis.touristpanel.core.reservation.vouchers.voucherstate"></a>

```json
100

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|100|
|*anonymous*|200|
|*anonymous*|210|
|*anonymous*|221|
|*anonymous*|222|
|*anonymous*|223|
|*anonymous*|300|
|*anonymous*|301|

<h2 id="tocS_TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherType">TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherType</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.reservation.vouchers.vouchertype"></a>
<a id="schema_TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherType"></a>
<a id="tocStoptis.touristpanel.core.reservation.vouchers.vouchertype"></a>
<a id="tocstoptis.touristpanel.core.reservation.vouchers.vouchertype"></a>

```json
1

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|2|
|*anonymous*|3|
|*anonymous*|4|

<h2 id="tocS_TopTis.TouristPanel.Core.Vouchers.Revoking.EventDto">TopTis.TouristPanel.Core.Vouchers.Revoking.EventDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.vouchers.revoking.eventdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Vouchers.Revoking.EventDto"></a>
<a id="tocStoptis.touristpanel.core.vouchers.revoking.eventdto"></a>
<a id="tocstoptis.touristpanel.core.vouchers.revoking.eventdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "label": "string",
  "excuteDateTime": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|label|string¦null|false|none|none|
|excuteDateTime|string¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Vouchers.Revoking.EventGroupDto">TopTis.TouristPanel.Core.Vouchers.Revoking.EventGroupDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.vouchers.revoking.eventgroupdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Vouchers.Revoking.EventGroupDto"></a>
<a id="tocStoptis.touristpanel.core.vouchers.revoking.eventgroupdto"></a>
<a id="tocstoptis.touristpanel.core.vouchers.revoking.eventgroupdto"></a>

```json
{
  "programId": "bc59f66b-913a-48ec-ae2b-7ee29d7bcfbb",
  "programTitle": "string",
  "programReference": "string",
  "eventId": "d6703cc8-9e79-415d-ac03-a4dc7f6ab43c",
  "eventTitle": "string",
  "start": "2019-08-24T14:15:22Z",
  "end": "2019-08-24T14:15:22Z",
  "endReservation": "2019-08-24T14:15:22Z",
  "excuteDateTime": "string",
  "totalVouchersCount": 0,
  "totalRevokedCount": 0,
  "vouchers": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "voucherNo": 0,
      "groupReference": "string",
      "customerFullName": "string",
      "customerMobile": "string",
      "voucherState": 100
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|programId|string(uuid)|false|none|none|
|programTitle|string¦null|false|none|none|
|programReference|string¦null|false|none|none|
|eventId|string(uuid)|false|none|none|
|eventTitle|string¦null|false|none|none|
|start|string(date-time)|false|none|none|
|end|string(date-time)|false|none|none|
|endReservation|string(date-time)|false|none|none|
|excuteDateTime|string¦null|false|none|none|
|totalVouchersCount|integer(int32)|false|none|none|
|totalRevokedCount|integer(int32)|false|none|none|
|vouchers|[[TopTis.TouristPanel.Core.Vouchers.Revoking.VoucherDto](#schematoptis.touristpanel.core.vouchers.revoking.voucherdto)]¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Vouchers.Revoking.ProgramDto">TopTis.TouristPanel.Core.Vouchers.Revoking.ProgramDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.vouchers.revoking.programdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Vouchers.Revoking.ProgramDto"></a>
<a id="tocStoptis.touristpanel.core.vouchers.revoking.programdto"></a>
<a id="tocstoptis.touristpanel.core.vouchers.revoking.programdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "title": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|title|string¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Vouchers.Revoking.RevokedVoucherDto">TopTis.TouristPanel.Core.Vouchers.Revoking.RevokedVoucherDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.vouchers.revoking.revokedvoucherdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Vouchers.Revoking.RevokedVoucherDto"></a>
<a id="tocStoptis.touristpanel.core.vouchers.revoking.revokedvoucherdto"></a>
<a id="tocstoptis.touristpanel.core.vouchers.revoking.revokedvoucherdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "voucherNo": 0,
  "forcedRevokeing": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|voucherNo|integer(int64)|false|none|none|
|forcedRevokeing|boolean|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Vouchers.Revoking.SyncEventDataDto">TopTis.TouristPanel.Core.Vouchers.Revoking.SyncEventDataDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.vouchers.revoking.synceventdatadto"></a>
<a id="schema_TopTis.TouristPanel.Core.Vouchers.Revoking.SyncEventDataDto"></a>
<a id="tocStoptis.touristpanel.core.vouchers.revoking.synceventdatadto"></a>
<a id="tocstoptis.touristpanel.core.vouchers.revoking.synceventdatadto"></a>

```json
{
  "eventId": "d6703cc8-9e79-415d-ac03-a4dc7f6ab43c",
  "revoked": [
    {
      "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
      "voucherNo": 0,
      "forcedRevokeing": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|eventId|string(uuid)|false|none|none|
|revoked|[[TopTis.TouristPanel.Core.Vouchers.Revoking.RevokedVoucherDto](#schematoptis.touristpanel.core.vouchers.revoking.revokedvoucherdto)]¦null|false|none|none|

<h2 id="tocS_TopTis.TouristPanel.Core.Vouchers.Revoking.VoucherDto">TopTis.TouristPanel.Core.Vouchers.Revoking.VoucherDto</h2>
<!-- backwards compatibility -->
<a id="schematoptis.touristpanel.core.vouchers.revoking.voucherdto"></a>
<a id="schema_TopTis.TouristPanel.Core.Vouchers.Revoking.VoucherDto"></a>
<a id="tocStoptis.touristpanel.core.vouchers.revoking.voucherdto"></a>
<a id="tocstoptis.touristpanel.core.vouchers.revoking.voucherdto"></a>

```json
{
  "id": "497f6eca-6276-4993-bfeb-53cbbbba6f08",
  "voucherNo": 0,
  "groupReference": "string",
  "customerFullName": "string",
  "customerMobile": "string",
  "voucherState": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string(uuid)|false|none|none|
|voucherNo|integer(int64)|false|none|none|
|groupReference|string¦null|false|none|none|
|customerFullName|string¦null|false|none|none|
|customerMobile|string¦null|false|none|none|
|voucherState|[TopTis.TouristPanel.Core.Reservation.Vouchers.VoucherState](#schematoptis.touristpanel.core.reservation.vouchers.voucherstate)|false|none|none|

