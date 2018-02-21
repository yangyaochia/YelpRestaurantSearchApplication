# YelpRestaurantSearchApplication
Yelp Restaurant Search Application

##Highlights
 - input => query options (main category, sub categories, attributes, day, location, open hour)
 - output => filtered business and review info
 - Data Model Design, Oracle Database, SQL queries
 - Java Swing GUI Application

##Input Dataset
 - subset of Yelp challenge datasets
 
##Objective
 - Develop a data analysis application for yelp review data
 
##Step
 - Design the relational table schema based on yelp dataset
 - Parse the json dataset and store into the database
 - Dynamically generate query based on the selected item and query the wanted restaurant/review efficiently

##Dataset format
Business Objects Business objects contain basic information about local businesses. 
{ 'business_id': (encrypted business id), 
  'full_address': (localized address), 
  ‘hours’: (the days of the week when business is open; the opening and closing times on those days) 
  'open': True / False (corresponds to closed, not business hours), 
  ‘categories’: (categories associated with the business) 
  'city': (city), 
  'state': (state), 
  'latitude': latitude, 
  'longitude': longitude, 
  'review_count': review count, 
  'name': (business name), 
  'neighborhoods': [(hood names)], 
  'stars': (star rating, rounded to half-stars), 
  ‘attributes’: (business properties), 
  'type': 'business' 
} 
 
Review Objects Review objects contain the review text, the star rating, and information on votes Yelp users have cast on the review. Use user_id to associate this review with others by the same user. Use business_id to associate this review with others of the same business. 
{ 'votes': { 'useful': (count of useful votes), 
  'funny': (count of funny votes), 
  'cool': (count of cool votes) } 
  'user_id': (the identifier of the authoring user), 
  'review_id': (the identifier of the reviewed business), 
  'stars': (star rating, integer 1-5), 
  'date': (date, formatted like '2011-04-19'), 
  'text': (review text), 
  'type': 'review', 
  'business_id': (the identifier of the reviewed business) 
} 
 
User Objects User objects contain aggregate information about a single user across all of Yelp (including businesses and reviews not in this dataset). 
{ 
‘yelping_since’: (the date when user account was created) 
'votes': { 'useful': (count of useful votes across all reviews), 
           'funny': (count of funny votes across all reviews), 
           'cool': (count of cool votes across all reviews) 
          } 
 'review_count': (review count), 
 'name': (first name, last initial, like 'Matt J.'), 
 'user_id': (unique user identifier),
 ‘friends’: (friends of the user), 
 ‘fans’: (number fans of the user), 
 'average_stars': (floating point average, like 4.31), 
 'type': 'user', 
 ‘compliments’: (comments from other users), ‘elite’: () 
}
