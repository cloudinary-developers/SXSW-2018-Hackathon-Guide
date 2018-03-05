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

