# Rail season tickets cost 10% of net pay

![](https://raw.githubusercontent.com/BBC-Data-Unit/rail-season-tickets/master/Most%20expensive%20rail%20season%20tickets.png)

In September 2016 we [reported that commuters spend more than a tenth of disposable income on annual rail season tickets](http://www.bbc.co.uk/news/uk-england-37166033).

The data came from analysis of season ticket prices for the most popular commuter routes by Dan Wainwright, combined with data on local earnings, and data on route distances. Analysis was based on full time workers using an annual season ticket five days a week.

Season ticket price data was compiled manually by entering the most commonly used commuter services in six major cities (obtained from the Campaign for Better Transport) into the [National Rail season ticket calculator](http://ojp.nationalrail.co.uk/service/seasonticket/search)

Route distances were calculated using the [Google Places Distance Matrix API](https://developers.google.com/maps/documentation/distance-matrix/intro).

## Visualisation

* Infographic: Cost of commuting
* Bar chart: Most expensive rail season tickets (shown above)
* Bar chart: Least expensive rail tickets per mile travelled
* Bar chart: Where your money goes

## Data

* [Routes, distances, prices, local median wages, and calculations](https://github.com/BBC-Data-Unit/rail-season-tickets/blob/master/Breakdown%20of%20annual%20rail%20passes%20-%20BBC%20News.csv). Also [available as a Google spreadsheet](https://docs.google.com/spreadsheets/d/1mUb-HMoNw10tYmdhmoDotqenrF5Y3e5ItkbWNXYFL_E/pub?output=csv)
* [Office for National Statistics: median earnings by place of work](http://www.ons.gov.uk/employmentandlabourmarket/peopleinwork/earningsandworkinghours/datasets/placeofworkbylocalauthorityashetable7)
* [Google Places Distance Matrix API](https://developers.google.com/maps/documentation/distance-matrix/intro)

## Interviews and other sources

* Rail Delivery Group
* Campaign for Better Transport
* Commuters Natasha Ellingham and Matt Steel
* Merseyrail
* Department for Transport

## How we used the Google Places API

We've written [an explanation of how the Google Places API can be used to find out train journey distances here](https://github.com/BBC-Data-Unit/rail-season-tickets/blob/master/google-places-api.md)

## Related repos

In January 2017 we used similar techniques to report on rail season ticket rises. A [separate repository for that story can be found here](https://github.com/BBC-Data-Unit/rail-season-ticket-rises). You can [see all fares-related stories under the 'fares' tag](https://github.com/BBC-Data-Unit?utf8=%E2%9C%93&q=fares&type=&language=)
