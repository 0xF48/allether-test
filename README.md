# 🍕 Anons Pizza Shop 🍕
The test project will consist of doing some basic backend routing using node and/or any complementary framework of your choice. Create an HTTP REST JSON API according to the following specifications and store the data in a mongodb database.

## Specs  
- You are building an online pizza builder where anonymous users can create and order pizzas with different toppings using a json rest api.
- Each pizza is a a subdocument of an "order" document in the db 
- Each order contains  information about the anonymous user who ordered the pizza (such as ip address, approx location / city? / etc...) and when it was ordered, and its delivery status. ( 0 - pending, 1- baking, 2 - delivering, 3 - delivered), add more data to order as you see fit.
- Each pizza has a list of ingredients, crust type, etc.. figure out your own pizza ingredients and pizza type from pizza recipes online eg [https://www.delish.com/cooking/recipe-ideas/a24893663/homemade-pizza-recipe/](https://www.delish.com/cooking/recipe-ideas/a24893663/homemade-pizza-recipe/)

**YOU CAN USE POSTMAN TO HELP YOU TEST AND DEBUG YOUR API**
---
## REST API Route Specification

| method | route | route description |
|--|--|--|
|POST | /order/create | create an order with json body and return the created order. post body will contain information about the order and items such as a pizza, pizza ingredients, pizza crust, bake temperature, etc. Reference the dominos online pizza delivery store for more detailed options (or get find a pizza menu online) . orders may contain different items such as side items (a drink or sauce, or something else if you want) along with a pizza.  |
|GET| /orders | list all orders with pagination and sorting in a querystring |
|POST| /order/:order_id/update | post json body with modified order, incase users need to go back and edit their order. users should not be able to up |
|GET| /order/:order_id | get a specific order by its id along with all the information about that order including items.
|GET| /order/:order_id/items|get all items in an array (pizza, sauce, drink) of the order.
|POST| /order/status/update|update order delivery/bake status
|GET| /order/:order_id/status|get order delivery/bake status
|GET| /stats | get global stats such as how many pizzas were created total, how many orders created total/today/last hour, add more interesting aggregated information such as popularity of a specific topping

## Extra Points
| method | route | route description |
|--|--|--|
|POST| /cron/create | create a cron that will automatically order pizzas at set intervals with a particular post body. use a popular node scheduling library from npm.
|GET|/crons|list all cron jobs.
|POST|/cron/:cron_id/stop| stop a specific cron, but keep it in the database.


### Suggested Packages
- mongoose ( elegant mongodb object modeling for node.js ) https://mongoosejs.com/
- expressjs https://expressjs.com/
- body-parser https://www.npmjs.com/package/body-parser
