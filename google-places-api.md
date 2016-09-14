# How we used the Google Places API to calculate train route distances

For our story on the cost of rail season tickets we needed to calculate a cost per mile of each route. Initially this was done using [Mapline](https://mapline.com/), which provides a distance between two points *as the crow flies* (i.e. in a straight line).

However, trains do not run in a straight line. This is particularly an issue for routes where a body of water is between the start and end of a journey (such as Merseyrail services around the River Mersey and services near the River Avon).

Of course, you can search Google Maps to find out the distance between two points - but it only provides distances when you select travel by car, or foot. For train journeys it will only tell you the journey time.

But Google Maps *does* have that data - you just need to use their API to get it. 

## Using the Google Places API

Specifically, you need to use the [Google Places Distance Matrix API](https://developers.google.com/maps/documentation/distance-matrix/intro). By specifying a starting point, a destination point, and other details such as the time and mode of transit, you can get back data on the time and distance of the route.

You query the API by creating a URL which contains information about your question. Here's an example of a query asking what the distance is between Liverpool Lime Street and New Brighton stations: 

`https://maps.googleapis.com/maps/api/distancematrix/json?origins=liverpool%20lime%20street%20station&destinations=new%20brighton%20station%20uk&transit_mode=train&key=ENTERYOURKEYHERE`

The more specific you are about the origin and destination, the better: adding 'UK' is pretty essential: otherwise Google Places will look for places in the US first. Likewise 'Manchester Piccadilly Station' is much more accurate than 'Manchester'.

In the example above data is returned in JSON format, but you can change 'json' to 'xml' if you prefer that. 

At the end of the query is an API 'key'. This is personal to you. To get a key [apply for it here](https://developers.google.com/places/ios-api/start#get-key). You will also need to [activate it here](https://console.developers.google.com/projectselector/apis/api/distance_matrix_backend?pli=1). 

You can find [documentation on using the 'distance matrix' here](https://developers.google.com/maps/documentation/distance-matrix/intro). It is actually possible to query a whole series of journeys using just one URL.

## Running multiple queries

We generated URLs for each route in Excel: we already had origins and destinations in different cells. All we had to do was write a formula which grabbed each one and placed it into a URL. That formula was then copied down to generate 80 or so different URLs.

That data was then brought into Open Refine using the 'Add column by fetching URLs' facility, and the the parseJson function to extract the specific data on distance ([tutorial here](https://onlinejournalismblog.com/2010/12/16/adding-geographical-information-to-a-spreadsheet-based-on-postcodes-google-refine-and-apis/)).

Other processes would have worked just as easily, such as using Python or R to loop through and grab the URLs and then parse the information in a similar way.

## Lessons from the process

As a byproduct of the process we found that Google Maps distances by car were closer to the real train route distances than the straight line distances. So if you can't use an API, those are your next best bet.

Of course the other byproduct of the process is to never assume that because Google Maps doesn't have information just because it doesn't show it when you esarch: you can get a much more accurate guide by thinking about the data hidden in APIs.

