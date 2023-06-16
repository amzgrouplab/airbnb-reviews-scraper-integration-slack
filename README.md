# Airbnb Scraper

Airbnb Scraper actor is designed to extract most of publicly available data for home listings. 
You can get all of the basic pieces of information about the listing and all of the reviews.

The actor was meant to be used for extracting all listings for a particular location.
You can specify the price range, checkin and checkout dates. 
Normally Airbnb provides only the first 300 results on their website and limits the API to 1000 results, but with our Airbnb Scraper you can access all of them.
The actor can be used for various use cases. 
You can monitor amount of Airbnb listings around your listing and get the newest prices updates and follow trends for the given location.
Another possible use case is to analyze reviews using sentiment analysis and find the best location in town.

## Get all listing for given location
It is super easy to get all Airbnb listings for a given location. If you are looking for more specific results, then you can also add `priceMin`, `priceMax`, `checkIn`, `checkOut`,`currency`. Description of these fields can be found in the Input schema.
You have to only fill in the location field in the UI or pass the `INPUT` in the following shape:
``` javascript
   {
    "locationQuery": "London"
   }
```

## Get listing detail for specified list of urls
The only thing you have to do is provide a list of urls pointing to the Airbnb listing detail, for example:`https://www.airbnb.cz/rooms/31021739?adults=1&toddlers=0&check_in=2019-05-15&check_out=2019-05-23&guests=1&source_impression_id=p3_1557753504_RkhYbgY4jm9gY%2FVh&s=wUZdYw7_`

You can either use UI to pass the list of urls or you can specify the `INPUT` directly. In that case the file should like this:
``` javascript
    "startUrls":[
         {
            "url": "https://www.airbnb.cz/rooms/31021739?adults=1&toddlers=0&check_in=2019-05-15&check_out=2019-05-23&guests=1&source_impression_id=p3_1557753504_RkhYbgY4jm9gY%2FVh&s=wUZdYw7_"
         }
    ]
```
