### Artist - chart

### GET /artist/chart

This method returns a territory-specific rolling weekly chart, based on the most purchased artists over the past 7 days.

| Attribute | Type | Description |
| :--- | :--- | :--- |
| **country** _required_ | _string_ | ISO 2-character code of the country the end user resides in. |
| **page** | _integer_ | Page number of the result set. If not supplied, defaults to 1. |
| **pageSize** | _integer_ | Number of items to be returned per page. If not supplied this defaults to 10. Maximum page size is 50. |



#### EXAMPLE REQUEST:

```
http://api.7digital.com/1.2/artist/chart?oauth_consumer_key=YOUR_KEY_HERE&country=GB
```

APPLICATION/JSON

```
{
  "status" : "ok",
  "version" : "1.2",
  "chart" : {
    "page" : 1,
    "pageSize" : 2,
    "totalItems" : 100,
    "type" : "artist",
    "fromDate" : "2013-11-25T00:00:00+00:00",
    "toDate" : "2013-12-01T00:00:00+00:00",
    "chartItem" : [{
        "position" : 1,
        "change" : "New",
        "artist" : {
          "id" : 276,
          "name" : "McFly",
          "appearsAs" : null,
          "url" : "http://www.7digital.com/artist/mcfly/?partner=1401"
        }
      }, {
        "position" : 2,
        "change" : "New",
        "artist" : {
          "id" : 386,
          "name" : "Robbie Williams",
          "appearsAs" : null,
          "url" : "http://www.7digital.com/artist/robbie-williams/?partner=1401"
        }
      }
    ]
  }
}
```

