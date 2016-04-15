#eBay API

You can connect to the eBay API using the RapidAPI system. This let's you do things like querying products and prices, placing bids and more...

To use the eBay API you need to first obtain an API key. You may obtain that key set from the eBay developer portal. to start, [sign up](https://developer.ebay.com/signin) for a developer account. Once in the account you'll be immidiatly prompted to create a new app. Give your app a name and choose production. You may be required to enter additional personal details.

<aside class="warning">
You must use production keys (and not sandbox) in order to make API requests to the eBay API.
</aside>

![](http://i.giphy.com/d3FxGZTIcGOMWuFG.gif)

Once you are finished your app will be created and you'll see 3 different keys:

 - App ID - the main key we'll use
 - Dev ID
 - Cert ID

Take note of these as you'll need to put them in the eBay API blocks to connect to the eBay API.

<aside class="notice">
The eBay API allows you to make 5,000 API calls / month. After that you'll be required to verify your app with eBay.
</aside>

##ebay.findItemsByKeyword

This block let's you query the entire eBay product base and find products based on search keywords.

**Use Case:** if you want to suggest products your users may need - you can present some options from eBay. For example, a camping app may present tents as users will probably need those.

Parameter | Use | Description
--------- | ------- | -----------
FreeShippingOnly | `true` or `false`	| If true, the block will only look for products with free shipping.
MaxPrice | Number / empty	| Will limit the price of the found products (in USD). Leave empty for unlimited price.
appId | App ID | Your App ID generated in the eBay Developer Portal (see the beggining of the section for reference)
data | `to` | The object the returned items will be saved to. You can use `#to` to get the found items.
domainName | Digital_cameras | Catalog Name
error | 'e' | If there is an error, the error message will ve saved there (so you can use `#e` to see the message)
keyword | `iPhone 6`, `Harry potter box set` | The keywords you are searching for

If there is success, use `#t` to use the returned items. It'll hold an array with all the found items. Each item will look like:

```json

{
"itemId": "272146040512",
"title": "New Apple iPhone 6s - 64GB - Factory GSM Unlocked 12.0MP Smartphone - All Colors",
"globalId": "EBAY-US",
"subtitle": "Free Shipping. 1 Year Apple Warranty. Apple UK Charger.",
"primaryCategory": {
"categoryId": "9355",
"categoryName": "Cell Phones & Smartphones"
},
"galleryURL": "http://thumbs1.ebaystatic.com/pict/272146040512404000000001_2.jpg",
"viewItemURL": "http://www.ebay.com/itm/New-Apple-iPhone-6s-64GB-Factory-GSM-Unlocked-12-0MP-Smartphone-All-Colors-/272146040512?var=570957295960",
"paymentMethod": "PayPal",
"autoPay": "true",
"postalCode": "11205",
"location": "Brooklyn,NY,USA",
"country": "US",
"shippingInfo": {
"shippingServiceCost": {
"amount": 0,
"currencyId": "USD"
},
"shippingType": "FlatDomesticCalculatedInternational",
"shipToLocations": [
"US",
"CA",
"GB",
"AU",
"AT",
"BE",
"FR",
"DE",
"IT",
"JP",
"ES",
"TW",
"NL",
"CN",
"HK",
"MX",
"DK",
"RO",
"SK",
"BG",
"CZ",
"FI",
"HU",
"LV",
"LT",
"MT",
"EE",
"GR",
"PT",
"CY",
"SI",
"SE",
"KR",
"ID",
"ZA",
"TH",
"IE",
"PL",
"RU",
"IL"
],
"expeditedShipping": "true",
"oneDayShippingAvailable": "false",
"handlingTime": "1"
},
"sellingStatus": {
"currentPrice": {
"amount": 699.99,
"currencyId": "USD"
},
"convertedCurrentPrice": {
"amount": 699.99,
"currencyId": "USD"
},
"sellingState": "Active",
"timeLeft": "P10DT17H53M11S"
},
"listingInfo": {
"bestOfferEnabled": "false",
"buyItNowAvailable": "false",
"startTime": "2016-02-25T19:04:55.000Z",
"endTime": "2016-04-25T19:09:55.000Z",
"listingType": "StoreInventory",
"gift": "false"
},
"returnsAccepted": "true",
"condition": {
"conditionId": "1000",
"conditionDisplayName": "New"
},
"isMultiVariationListing": "true",
"discountPriceInfo": {
"originalRetailPrice": {
"amount": 999.99,
"currencyId": "USD"
},
"pricingTreatment": "STP",
"soldOnEbay": "false",
"soldOffEbay": "false"
},
"topRatedListing": "true"
},

```

##ebay.getSingleItem

This block gets information about a single item in the eBay catalog.

**Use case:** A user saves a list of favorite items and you want to get their up-to-date details.

Parameter | Use | Description
--------- | ------- | -----------
appId | App ID | Your App ID generated in the eBay Developer Portal (see the beggining of the section for reference)
itemId | `272146040512` | The unique ID of that item. Recieved when performing a query. Also, when looking at an item in the ebay site, it's the number at the end of the URL. (For example, for [this](http://www.ebay.com/itm/RC-6-Axis-Quadcopter-Flying-Drone-Toy-Gyro-HD-Camera-Remote-Control-LED-Lights-/381503849423), it'll be `381503849423`).
to | `to` | The object the returned items will be saved to. You can use `#to` to get the found items.

The data returned by the block will be formatted like that:

```json
{
"$": {
"xmlns": "urn:ebay:apis:eBLBaseComponents"
},
"Timestamp": "2016-04-15T01:13:29.397Z",
"Ack": "Success",
"Build": "E963_CORE_APILW_17911290_R1",
"Version": "963",
"Item": {
"ItemID": "381503849423",
"EndTime": "2016-04-26T07:49:23.000Z",
"ViewItemURLForNaturalSearch": "http://www.ebay.com/itm/RC-6-Axis-Quadcopter-Flying-Drone-Toy-Gyro-HD-Camera-Remote-Control-LED-Lights-/381503849423",
"ListingType": "FixedPriceItem",
"Location": "Rancho Cucamonga, California",
"GalleryURL": "http://thumbs4.ebaystatic.com/pict/3815038494238080_1.jpg",
"PictureURL": [
"http://i.ebayimg.com/00/s/MTYwMFgxNjAw/z/KbAAAOSwCQNWgOmK/$_1.JPG?set_id=880000500F",
"http://i.ebayimg.com/00/s/MTYwMFgxNjAw/z/1IIAAOSwLpdW8rVs/$_1.JPG?set_id=880000500F",
"http://i.ebayimg.com/00/s/MTYwMFgxNjAw/z/3iUAAOSw9uFW8rVs/$_1.JPG?set_id=880000500F",
"http://i.ebayimg.com/00/s/MTYwMFgxNjAw/z/kZEAAOSwZ8ZW8rVs/$_1.JPG?set_id=880000500F",
"http://i.ebayimg.com/00/s/MTYwMFgxNjAw/z/oFgAAOSwBnVW8rVt/$_1.JPG?set_id=880000500F"
],
"PrimaryCategoryID": "34053",
"PrimaryCategoryName": "Toys & Hobbies:Radio Control & Control Line:Radio Control Vehicles:Airplanes & Helicopters",
"BidCount": "0",
"ConvertedCurrentPrice": {
"amount": 49.95,
"currencyID": "USD"
},
"ListingStatus": "Active",
"TimeLeft": "P11DT6H35M54S",
"Title": "RC 6-Axis Quadcopter Flying Drone Toy Gyro HD Camera Remote Control LED Lights",
"Country": "US",
"AutoPay": "false",
"ConditionID": "1000",
"ConditionDisplayName": "New",
"QuantityAvailableHint": "Limited",
"DiscountPriceInfo": {
"OriginalRetailPrice": {
"amount": 119.95,
"currencyID": "USD"
},
"PricingTreatment": "STP",
"SoldOneBay": "true",
"SoldOffeBay": "false"
},
"GlobalShipping": "true"
}
}

```