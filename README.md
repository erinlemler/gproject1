# Food Route

## Overview

Created with foodies in mind, this tool provides comparison between all the top rated restaurants in the user's search parameters. Users are presented with 3 different search parameters: city, cuisine and distance. Users fill in all the parameters and the tool generates a map with markers containing the top 5 restaurants based on cuisine. Increasing the search radius will include more searches, but will always display the top 5 restaurants only. The current weather will be displayed under the map as well. Once the list has been generated, users can see all the pertinent information on each restaurant, as well as pictures provided by Google Photo-reference. The number of users will be tracked using Firebase which displays at the top of the page.

* * *
<img src="https://cdn.discordapp.com/attachments/446103300069392385/446104605890183189/unknown.png" height=500 width=900>

## Process

- The user is given a set of instructions at the top of the screen.
- Users input their city, desired cuisine and radius of search.
    - By default, radius of search is 2.5 miles.

<img src="https://cdn.discordapp.com/attachments/446103300069392385/446103316045234186/unknown.png" height=150 width=800>

- Upon search, multiple Google API calls will generate a map with markers, as well as populate a dynamically created card with the top 5 restaurants serving the desired cuisine.
- A weather API will provide temperature and status of the weather by location.

<img src="https://cdn.discordapp.com/attachments/446103300069392385/446103867684290578/unknown.png" height=400 width=250>

- The newly created card will have more detailed information on each restaurant that was populated including:
    - Name
    - Address
    - Photos
    - Price Range
    - Rating
    - Most recent reviewer and the review rating
    - Exerpt of review

<img src="https://cdn.discordapp.com/attachments/446103300069392385/446104283621097482/unknown.png" height=500 width=700>

## Challenges

- Dynamically creating entire cards with information from the search presented a huge problem within the javascript. Our solution was to create the entire card in HTML, then moving it into the generateCard() function.
- Originally there was to be a "more info" button that would take the user to a new tab with more detailed information on the restaurant selected. We opted to bypass that due to time constraints.
- We wanted to utilize Google Firebase in showing users a live counter on how popular a specific restaurant was. However, without a relational database, this became a large challenge that we had to change. We decided on a counter on how many users were using the website concurrently.
- Trying to work with Bootstrap to make a dynamic carousel was a constant thorn in the site. We spent many hours to finally make a quasi-working version, though it still cuts images that are dynamically created by the generateCard() function.
- The google maps, geolocation and places API had hard limits on Ajax calls, in addition to being slow to return data. There is a possible solution to speed up the Ajax calls in the future.

## Future Developments

- Speeding up the Ajax calls from Google API's are a large priority.
- Automatically displaying the top 3 results in the initial card generation.
    - Users can then close any of the results and a new one will append to the bottom.
    - Will also prevent users from accidentally opening the same markers.
- Converting the integer rating system into dollar signs $-$$$$.
- Markers will display a modal or infowindow with the name and an option for directions from Google Maps.
- Using a new database (not Google Firebase) that is relational so we can save user data and allow "favoriting" and "liking" restaurants. This will allow users to remember what their favorite restaurants are and see how popular searched restaurants are.
- Connecting users with more information on a restaurant via another API, may it be tripadvisor, yelp, or expedia.
- Expand the application from the food theme, to other themes; i.e. adventure activities and accommodations.

## Techonologies

### API's

- Google Maps API - [Google Maps API](https://developers.google.com/maps/documentation/javascript/tutorial)
- Google Geocoding API - [Google Geocoding API](https://developers.google.com/maps/documentation/geocoding/start)
- Google Places API - [GOogle Places API](https://developers.google.com/places/web-service/intro)
- Openweathermap - [Openweathermap API](https://openweathermap.org/api)

### CDN Used

- Bootstrap v4.1.0 - [getbootstrap](https://getbootstrap.com/)
- jQuery v3.3.1 (uncompressed) - [jQuery core](https://code.jquery.com/)
- FontAwesome v4.7 - [Font Awesome](https://fontawesome.com/get-started)
- Google Fonts - [Google Fonts](https://fonts.google.com/)


### Applications

- Adobe Photoshop v15.0.0 - [Adobe Photoshop](https://www.adobe.com/products/photoshopfamily.html)
- Adobe Illustrator v19.2.0 - [Adobe Illustrator](https://www.adobe.com/products/illustrator.html)

### Database

- Firebase 5.0.1 - [Google Firebase](https://firebase.google.com/)