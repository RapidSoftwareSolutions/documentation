#Google Places
##Places.getNearbyPlaces

**Name of the backend functions:** Get places near by; based on longitude, latitude and radius.

**How to use:** Go to [LatLong Generator](http://www.latlong.net/convert-address-to-lat-long.html) and get the latitued and longtitude of the point place you want to track.

**Use Case:** You want to show a user which places are near his location.

**Parameters information:**

Parameter | Use | Description
--------- | ------- | -----------
latitude | For example: 32.075001| Use generater or Google Maps to get lat |
longitude | For example: 34.783453 | Use generater or Google Maps to get long
radius | Use numbers | In meters. For example: 50 meters.
to | object | where do you want to save the file? Give it a name. For example: places

<aside class="warning">
For Example:
Error - Use the **response.SendMessage** block to get an error message back.</aside>

<aside class="success">
For Example:
- Use response.sendMessage block,
- Message = Use the object you have used in the 'to' field to print the result. In this case we used #places
- Status = 200 (Success).
</aside>
