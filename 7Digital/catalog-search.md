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

