# Team Members

* Nikita Voskoboynik (https://github.com/nikitavoskoboynik)
* Marc Simpson (https://github.com/masi8397)
* Jake White (https://github.com/jakewhite8)
* Jake Charland (https://github.com/jakecharland)

# Promotional campaign

## Description
We decided to promote the product that has recently suffered the largest decrease in sales, but is still a top performer. Because it was popular in the past, we know it is a good product and want to get performance back to previous levels. If you purchases it within the next day, you get 5% off.

## Rationale 1

```
sourcetype=access_* productId cart.do action=purchase | timechart span=2d limit=16 count by productId
```
[Imgur](http://i.imgur.com/kks3m4A.jpg)

Shows a line chart of product sales performance over the span of a week.

## Rationale 2

```
sourcetype=access_* productId cart.do action=purchase | table clientip, action, productId, date_month, date_mday, date_wday | top productId
```
[Imgur](http://i.imgur.com/oZfXJDt.png)

Shows top sales performance of products in a statistics table.


## Rationale 3

```
sourcetype=access_* productId cart.do action=purchase | stats count by productId | SORT by productId
```
[Imgur](http://i.imgur.com/XqybCxz.jpg)

Shows the largest difference in sales of each product in the past 2 days.


## Rationale N

{{more if desired, use-the-same-template-structure-as-before}}

# Loyalty program

## Description
The clients who have made the most purchases should be targeted for the loyalty program because of top customer retention. The top 10 clients will qualify for the program. After n amount of purchases, the client will be rewarded.

## Rationale 1

```
sourcetype=access_* productId cart.do action=purchase| 
	table clientip, action, productId, date_month, date_mday, date_wday | top clientip
```
[Imgur](http://i.imgur.com/iHI7DHv.jpg)

Shows a statistics table of the clients with the most purchases.

## Rationale 2

```
sourcetype=access_* productId cart.do action=purchase| timechart span=2d count by clientip useother=f
```
[Imgur](http://i.imgur.com/7I2J4VZ.jpg)

Shows a line chart of the clients with the top purchases over time.

## Rationale 3

```
sourcetype=access_* productId cart.do action=purchase clientip=107.3.146.207| top categoryId
```
[Imgur](http://i.imgur.com/CRIddXc.jpg)

This shows the category of the top clients purchases.


## Rationale N

{{more if desired, use-the-same-template-structure-as-before}}
