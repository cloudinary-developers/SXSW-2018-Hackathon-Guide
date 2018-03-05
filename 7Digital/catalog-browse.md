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

