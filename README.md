# Team Members

* [Peyman Mortazavi](https://github.com/peymanmortazavi)
* [Dawson Botsford](https://github.com/dawsonbotsford)
* [Brian Newsom](https://github.com/briannewsom)
* [Andrian Chen](https://github.com/adrian-chen)
* [Michael Aaron](https://github.com/develra)

# Promotional campaign

## Description
We decided to target the product with the lowest purchase to view ratio for our promotional campaign (for a none-NULL product). We figured this was an "opportunity" product for our business where people were expressing interest but failing to follow through with a purchase. By targeting this product, we hope to bring the purchase rate up closer to that of our most successful game "World of Cheese"

## Rationale 1
We decided to target the product with the lowest purchase to view ratio, the two lowest values were NULL, with Curling 2014 being the next one up the list. 
```
sourcetype=access_* action = "purchase" OR action = "view" status="200" | stats count(eval(action="view")) AS Views , count(eval(action="purchase")) AS Purchases by productId | eval Ratio=Purchases/Views
```
![screenshot of a data table or a graph or both](http://i.imgur.com/rLf27Z9.png) 
See a the ratio in the left-most column for our product choice

## Rationale 2

Why?
Curling 2014 seemed like game we were loosing the most visitors on, with interested viewers but a failure to follow through with the purchase. By promoting Curling 2014 we are hoping to get a ratio closer to that enjoyed by our most successful product
```
sourcetype=access_* action = "purchase" OR action = "view" status="200" | stats count(eval(action="view")) AS Views , count(eval(action="purchase")) AS Purchases by productId | eval Ratio=Purchases/Views
```
![screenshot of a data table or a graph or both](http://i.imgur.com/Y5GHhJy.png) 
The higher the ratio, the more common a viewing vistor follows through with a purchase.

## Rationale 3
When?
Across all of our products, the most purchases happen on the weekend. Therefor to maximize our revenue we decided to run the promotion on Saturday and Sunday.
```
sourcetype=access_* action=purchase | timechart span=day count
```
![screenshot of a data table or a graph or both](http://i.imgur.com/hDsyc7L.png) 
Even discounting the likely "false" two end datapoints based on partial aggregation, we can see most purchases on weekends.

# Loyalty program

## Description
In order to increase sales, we are going to offer a loyalty program to the top 30 customers.
There is no doubt that the same product for less of a cost is more desirable, but you cannot offer reduced priced products to everyone as we cannot simply make profit. Thus, in order to increase revenue and increase sales, these reduced prices will only be offered to the 30 most "loyal" customers. We defined a loyal customer as someone who is within the sites top 30 purchasers.

## Rationale 1

```
productId=* (action="purchase") | top limit=30 clientip
```
![Imgur](http://i.imgur.com/WARgN09.png)

The top 30 users that performed the most "purchase" actions.

## Rationale 2

It's likely that top 30 customers will increase their purchases to our company because they've already proven that they use our product.

## Rationale 3

By being in the top 30 customers list, you show that you use our product heavily.

## Rationale N

We can provide special price discounts for purchases. A reduced price will cause an increase in purchases for those in our loyalty program because we can provide a service (a game in this case) for even less cost.
