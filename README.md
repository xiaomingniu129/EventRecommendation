# EventRecommendation
This is a personalization-based event recommendation systems for event search. 
# Description
Developed a dynamic web application for users to search for events and update preferences.
Improved personalized event recommendation based on favorite records. 
* Back End:
  * Created Java servlets with RESTful APIs to handle HTTP requests and responses.
  * Built both relational databases MySQL and NoSQL databases MongoDB to capture real events data from TicketMaster API.
  * Designed content-based recommendation algorithms based on categories and distance of events to implement the events recommendation.
  * Deployed server side to Amazon EC2: http://13.57.35.36/EventRecommender/
* Front End:
  * Designed an interactive web page utilizing AJAX with HTML, CSS and JavaScript.
# Overview
* Presentation tier
  * It’s the tier that user can access directly. It provides the application’s user interface. For example, how to show nearby events in browser, how to provide easy way for user to send request to backend.
  * Language: HTML, CSS, JavaScript.
* Data tier
  * Use an existing existing databases: MySQL and MongoDB to define tables, the relationship between each other and the mechanism to store data.
  * Language: SQL
* Logic tier
  * Maintain the business logic of the application, sitting between presentation tier and data tier, receive request from presentation tier, make correct database operation, and return the final result back to presentation tier.
  * Language: Java
  ![image](https://github.com/XiaomingNiu-Sam/EventRecommendation/blob/master/images/Overview.png)
# API Design
* Search
  * Use TicketMaster API to search events.
* History
  * Save and get events by querying database.
* Recommendation
  * Based on favorite events and recommendation algorithm to return similar events.
* Register
  * Set a new user in database.
* Login
  * Query database to verify and return response.
* Logout
  * Invalidate the session and redirect to index.html.
 ![image](https://github.com/XiaomingNiu-Sam/EventRecommendation/blob/master/images/APIs.png)
  
# Database Design
* MySQL
  * users
    * store user information: user_id, password, first_name, last_name.
  * items
    * store item information: item_id, name, rating, address, image_url, url, distance.
  * category
    * store item-category relationship: item_id, category.
  * history
    * store item-user relationship: user_id, item_id, last_favor_time.
  ![image](https://github.com/XiaomingNiu-Sam/EventRecommendation/blob/master/images/mysql.png)

* MongoDB
  * users
    * store user information and favorite items.
  * items
    * store item information and item-category relatioship.
  * logs
    * store log information
    
