### Catalogue

#### About this API {#catalogue_About-this-API}

This section details the endpoints used to retrieve details of tracks, releases and artists in our [catalogue](http://docs.7digital.com/#catalogue)

### Artist - browse by name

### GET /artist/browse

This method returns a list of artists from the 7digital catalogue whose names match the start letter\(s\) supplied.

| Attribute | Type | Description |
| :--- | :--- | :--- |
| **letter** _required_ | _string_ | The first letter\(s\) of the artist name to browse. |
| **country** _required_ | _string_ | ISO 2-character code of the country the end user resides in. |

#### EXAMPLE REQUEST:

```
http://api.7digital.com/1.2/artist/browse?letter=p&country=US&oauth_consumer_key=YOUR_KEY_HERE
```

APPLICATION/JSON

```
{
    "status": "ok",
    "version": "1.2",
    "artists": {
        "page": 1,
        "pageSize": 10,
        "totalItems": 23817,
        "artist": [
            {
                "id": 314018,
                "name": "P & P",
                "sortName": "P & P",
                "url": "http://www.7digital.com/artist/p-and-p/?partner=1401",
                "image": "http://artwork-cdn.7static.com/static/img/artistimages/00/003/140/0000314018_150.jpg",
                "popularity": 0.29
            },
            ...
        ]
    }
}
```

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

### Artist - search

### GET /artist/search

This method returns a list of artists from the 7digital catalogue that match the search query.

| Attribute | Type | Description |
| :--- | :--- | :--- |
| **q** _required_ | _string_ | The search query string. |
| **country** _required_ | _string_ | ISO 2-character code of the country the end user resides in. |
| **sort** | _string_ | Orders the returned results. Supplied as a string in the format: "{sortColumn} {sortOrder}", for example: "popularity desc" will show most popular artists first regardless of search match score. Currently you can sort by name, popularity and score. If no sort is supplied, the default is "score desc". If no order is supplied the default is ascending. |
| **page** | _integer_ | Page number of the result set. If not supplied, defaults to 1. |
| **pageSize** | _integer_ | Number of items to be returned per page. If not supplied this defaults to 10. Maximum page size is 50. |
| **imageSize** | _integer_ | The requested width of the image in pixels.[Available image sizes are listed here](http://docs.7digital.com/#api-basics_Image-sizes). |

**Method specific error codes:**

**`1001`- Required parameter q is missing**  
You must supply a value for the q parameter.

**`1003`- Requested page out of range**  
You specified a page number which does not exist.

#### EXAMPLE REQUEST:

```
http://api.7digital.com/1.2/artist/search?q=pink&sort=score%20desc&country=US&oauth_consumer_key=YOUR_KEY_HERE&pagesize=2

```

APPLICATION/JSON

```
{
   "status": "ok",
   "version": "1.2",
   "schema": "http://api.7digital.com/1.2/static/7digitalAPI.xsd",
   "tracks": {
      "page": 1,
      "pageSize": 2,
      "totalItems": 1208,
      "track": [
         {
            "id": 148,
            "title": "All The Small Things",
            "version": "",
            "artist": {
               "id": 2,
               "name": "Blink 182",
               "appearsAs": "Blink-182",
               "image": "http://artwork-cdn.7static.com/static/img/artistimages/00/000/000/0000000002_150.jpg",
               "slug": "blink-182",
               "isPlaceholderImage": true
            },
            "trackNumber": 8,
            "duration": 172,
            "explicitContent": false,
            "isrc": "USMC19959123",
            "type": "Audio",
            "release": {
               "id": 20,
               "title": "Enema Of The State",
               "version": "",
               "type": "Album",
               "barcode": "00008811195021",
               "explicitContent": false,
               "artist": {
                  "id": 2,
                  "name": "Blink 182",
                  "appearsAs": "Blink-182",
                  "image": "http://artwork-cdn.7static.com/static/img/artistimages/00/000/000/0000000002_150.jpg",
                  "slug": "blink-182",
                  "isPlaceholderImage": true
               },
               "image": "http://artwork-cdn.7static.com/static/img/sleeveart/00/000/000/0000000020_50.jpg",
               "label": {
                  "id": 464954,
                  "name": "(P) 1999 Geffen Records"
               },
               "licensor": {
                  "id": 1,
                  "name": "Universal"
               },
               "duration": 0,
               "slug": "enema-of-the-state-1-1"
            },
            "discNumber": 1,
            "popularity": 0.4,
            "number": 8,
            "download": {
               "releaseDate": "2015-11-14T00:00:00Z",
               "previewDate": "2015-11-14T00:00:00Z",
               "packages": [
                  {
                     "id": 2,
                     "description": "Standard",
                     "price": {
                        "currencyCode": "GBP",
                        "recommendedRetailPrice": 0.99
                     },
                     "formats": [
                        {
                           "id": 17,
                           "description": "MP3 320"
                        }
                     ]
                  }
               ]
            },
            "subscriptionStreaming": {
               "releaseDate": "2015-11-14T00:00:00Z"
            },
            "adSupportedStreaming": {
               "releaseDate": "2015-11-14T00:00:00Z"
            }
         },
         {
            "id": 151,
            "title": "What's My Age Again?",
            "version": "Explicit",
            "artist": {
               "id": 2,
               "name": "Blink 182",
               "appearsAs": "Blink-182",
               "image": "http://artwork-cdn.7static.com/static/img/artistimages/00/000/000/0000000002_150.jpg",
               "slug": "blink-182",
               "isPlaceholderImage": true
            },
            "trackNumber": 5,
            "duration": 150,
            "explicitContent": true,
            "isrc": "USMC19959007",
            "type": "Audio",
            "release": {
               "id": 20,
               "title": "Enema Of The State",
               "version": "",
               "type": "Album",
               "barcode": "00008811195021",
               "explicitContent": false,
               "artist": {
                  "id": 2,
                  "name": "Blink 182",
                  "appearsAs": "Blink-182",
                  "image": "http://artwork-cdn.7static.com/static/img/artistimages/00/000/000/0000000002_150.jpg",
                  "slug": "blink-182",
                  "isPlaceholderImage": true
               },
               "image": "http://artwork-cdn.7static.com/static/img/sleeveart/00/000/000/0000000020_50.jpg",
               "label": {
                  "id": 464954,
                  "name": "(P) 1999 Geffen Records"
               },
               "licensor": {
                  "id": 1,
                  "name": "Universal"
               },
               "duration": 0,
               "slug": "enema-of-the-state-1-1"
            },
            "discNumber": 1,
            "popularity": 0.39,
            "number": 5,
            "download": {
               "releaseDate": "2015-11-14T00:00:00Z",
               "previewDate": "2015-11-14T00:00:00Z",
               "packages": [
                  {
                     "id": 2,
                     "description": "Standard",
                     "price": {
                        "currencyCode": "GBP",
                        "recommendedRetailPrice": 0.99
                     },
                     "formats": [
                        {
                           "id": 17,
                           "description": "MP3 320"
                        }
                     ]
                  }
               ]
            },
            "subscriptionStreaming": {
               "releaseDate": "2015-11-14T00:00:00Z"
            },
            "adSupportedStreaming": {
               "releaseDate": "2015-11-14T00:00:00Z"
            }
         }
      ]
   }
}

```

###  Artist - releases

### GET /artist/releases

This method returns a list of releases by given artist. Releases can be filtered by type.

| Attribute | Type | Description |
| :--- | :--- | :--- |
| **artistId** _required_ | _integer_ | The unique identifier of the artist. |
| **usageTypes** _required_ | _string_ | Only use the usageTypes you need, e.g. download, subscriptionstreaming or adsupportedstreaming. |
| **type** | _one of album,single,video_ | Releases can be of type album, single or video. If specified, results are filtered by release type. |
| **packageIds** | _string_ | Contains a comma-separated list of package ids. When specified, only releases that have one of the specified packages will be returned. Used to filter searches to releases that have at least one high quality format.[Package ids are listed here](http://docs.7digital.com/#api-basics_Download-packages---formats).This parameter only takes effect when using 'usageTypes=download', and is otherwise ignored. |
| **country** _required_ | _string_ | ISO 2-character code of the country the end user resides in. |
| **page** | _integer_ | Page number of the result set. If not supplied, defaults to 1. |
| **pageSize** | _integer_ | Number of items to be returned per page. If not supplied this defaults to 10. Maximum page size is 50 |
| **imageSize** | _integer_ | The requested width of the image in pixels.[Available image sizes are listed here](http://docs.7digital.com/#api-basics_Image-sizes). |

**Method specific error codes:**

**`1001`- Required parameter artistId is missing**  
You must supply a value for the artistId parameter.

**`1003`- Requested page out of range**  
You specified a page number which does not exist.

#### EXAMPLE REQUEST:

```
http://api.7digital.com/1.2/artist/releases?artistid=1&oauth_consumer_key=YOUR_KEY_HERE&country=GB&pagesize=2&usageTypes=download,subscriptionstreaming,adsupportedstreaming

```

APPLICATION/JSON

```
{
   "status": "ok",
   "version": "1.2",
   "schema": "http://api.7digital.com/1.2/static/7digitalAPI.xsd",
   "releases": {
      "page": 1,
      "pageSize": 2,
      "totalItems": 59,
      "releases": [
         {
            "id": 809798,
            "title": "A Bad Dream",
            "version": "",
            "type": "Single",
            "barcode": "00602527390970",
            "year": "2010",
            "explicitContent": false,
            "artist": {
               "id": 1,
               "name": "Keane",
               "appearsAs": "Keane",
               "image": "http://artwork-cdn.7static.com/static/img/artistimages/00/000/000/0000000001_150.jpg",
               "slug": "keane",
               "isPlaceholderImage": false
            },
            "image": "http://artwork-cdn.7static.com/static/img/sleeveart/00/008/097/0000809798_50.jpg",
            "label": {
               "id": 471977,
               "name": "(P) 2010 Universal Island Records Ltd. A Universal Music Company."
            },
            "licensor": {
               "id": 1,
               "name": "Universal"
            },
            "popularity": 0,
            "duration": 307,
            "trackCount": 1,
            "download": {
               "releaseDate": "2015-11-15T00:00:00Z",
               "packages": [
                  {
                     "id": 2,
                     "description": "Standard",
                     "price": {
                        "currencyCode": "GBP",
                        "sevendigitalPrice": 0.99,
                        "recommendedRetailPrice": 0.99
                     },
                     "formats": [
                        {
                           "id": 17,
                           "description": "MP3 320"
                        }
                     ]
                  }
               ]
            },
            "subscriptionStreaming": {
               "releaseDate": "2015-11-15T00:00:00Z"
            },
            "adSupportedStreaming": {
               "releaseDate": "2015-11-15T00:00:00Z"
            },
            "slug": "a-bad-dream-1"
         },
         {
            "id": 470,
            "title": "AOL Session",
            "version": "",
            "type": "Single",
            "barcode": "00602498672938",
            "year": "2004",
            "explicitContent": false,
            "artist": {
               "id": 1,
               "name": "Keane",
               "appearsAs": "Keane",
               "image": "http://artwork-cdn.7static.com/static/img/artistimages/00/000/000/0000000001_150.jpg",
               "slug": "keane",
               "isPlaceholderImage": false
            },
            "image": "http://artwork-cdn.7static.com/static/img/sleeveart/00/000/004/0000000470_50.jpg",
            "label": {
               "id": 465499,
               "name": "(P) 2004 Universal Island Records Ltd. A Universal Music Company."
            },
            "licensor": {
               "id": 1,
               "name": "Universal"
            },
            "popularity": 0,
            "duration": 1404,
            "trackCount": 6,
            "download": {
               "releaseDate": "2015-11-15T00:00:00Z",
               "packages": [
                  {
                     "id": 2,
                     "description": "Standard",
                     "price": {
                        "currencyCode": "GBP",
                        "sevendigitalPrice": 3.99,
                        "recommendedRetailPrice": 3.99
                     },
                     "formats": [
                        {
                           "id": 17,
                           "description": "MP3 320"
                        },
                        {
                           "id": 33,
                           "description": "AAC 320"
                        }
                     ]
                  }
               ]
            },
            "subscriptionStreaming": {
               "releaseDate": "2015-11-15T00:00:00Z"
            },
            "adSupportedStreaming": {
               "releaseDate": "2015-11-15T00:00:00Z"
            },
            "slug": "aol-session"
         }
      ]
   }
}

```

### Stream any track \(radio use\)

### GET /stream/catalogue

Allows user to stream any track in the 7digital catalogue available in their region. This endpoint is designed for radio style play where individual tracks cannot be selected by the user \(i.e. "non-interactive" streaming\), and is licensed differently than other streaming endpoints. Tracks can be cached \(in an encrypted format\) on the end user's device, but all plays from either the cache or live must be reported with the catalogue/log endpoint. Please contact us for more details. Endpoint's full location:[https://stream.svc.7digital.net/stream/catalogue](https://stream.svc.7digital.net/stream/catalogue)

| Attribute | Type | Description |
| :--- | :--- | :--- |
| **trackId** _required_ | _integer_ | The 7digital ID of the track to be streamed. |
| **formatId** _required_ | _integer_ | The 7digital ID of the format requested. Please contact us for available formats. |
| **country** _required_ | _string_ | ISO 2-character code of the country the end user resides in. |

**Method specific error codes:**

**`1001`- Error: Missing "parameter name" query parameter.**Not all mandatory parameters were specified in the request.

**`1002`- Invalid value for "parameter name": parameter value.**Value for parameter in error message is not valid.

**`2001`- Track not found.**This track isn't available for streaming in your country or shop.

**`2002`- Pre-release availability.**The track is not available for radio streaming \(note that release dates may differ from subscription/locker streaming release dates\).  
EXAMPLE REQUEST:

```
https://stream.svc.7digital.net/stream/catalogue?country=US&trackid=123456&formatid=??
```



