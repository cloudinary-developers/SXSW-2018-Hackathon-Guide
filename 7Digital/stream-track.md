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



