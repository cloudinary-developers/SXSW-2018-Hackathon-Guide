#### 7Digital API Cheat Sheet: 


> **Success** Complete Docs: [http://docs.7digital.com/#api-basics ](http://docs.7digital.com/#api-basics "API-BASICS")

#### Request Format {#api-basics_Request-Format}

Access to 7digital services is provided through a REST style interface.

The production API is located at the following address:

[http://api.7digital.com/1.2/](http://api.7digital.com/1.2/)

A typical API request will look as follows:

[http://api.7digital.com/1.2/artist/details?country=GB&oauth\_consumer\_key=YOUR\_KEY\_HERE&artistId=1](http://api.7digital.com/1.2/artist/details?country=GB&oauth_consumer_key=YOUR_KEY_HERE&artistId=1)

The supported HTTP methods are displayed underneath each API method in our documentation, e.g. GET or POST.

HTTP POST requests to the 7digital API require all their parameters \(including country, page, etc.\) to be supplied within the POST body in the [application/x-www-form-urlencoded](http://www.w3.org/TR/html401/interact/forms.html#h-17.13.4.1) content type format, e.g. 

#### Lists & paging {#api-basics_Lists---paging}

All API methods that return a list of items in the response accept the following paging parameters:

| Name | Type | Use | Description |
| :--- | :--- | :--- | :--- |
| page | integer | optional | Page number - defaults to 1 |
| pageSize | integer | optional | Number of items to be returned per page. Defaults to 10. Maximum page size is 50 |

Paging information will also be included in the response as per the format below:

```
<page>1</page>
<itemsPerPage>10</itemsPerPage>
<totalItems>21</totalItems>
```

The value of totalItems is the maximum number of results. There will sometimes be fewer results available than the totalItems count. This is more noticeable when paging through a large result set. As you advance through the pages the totalItems count may drop.

#### Image sizes {#api-basics_Image-sizes}

Some API responses may contain URL's of cover art and artist pictures.

For release**cover art images**the following sizes are supported:

**33, 50, 100, 180, 182, 200, 350, 500 \* **and **800 \***pixels

The size of images returned by any API response can be adjusted by adding imageSize parameter to the request

| Name | Type | Use | Description |
| :--- | :--- | :--- | :--- |
| imageSize | integer | optional | the requested width of the image in pixels |

  
\*Cover art at this size is not available for some releases \(less than 0.1% of the catalogue\)

Example

```
http://api.7digital.com/1.2/artist/releases?artistId=1&imageSize=350&oauth_consumer_key=YOUR_KEY_HERE

```

**Artist **pictures are available in these sizes::

**150, 200 **and **300 **pixels

Please note: The image size is defined by the width of the picture. The height of the picture may vary.

Example

```
http://api.7digital.com/1.2/artist/details?artistId=1&imageSize=200&oauth_consumer_key=YOUR_KEY_HERE
```



