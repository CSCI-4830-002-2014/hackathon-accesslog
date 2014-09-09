# Team Members

* [Alexia Newgord](https://github.com/alne4294)
* [Austin Wood](https://github.com/indiesquidge)
* [Ian K.](https://github.com/ianks)
* [Daniel Nolan](https://github.com/dano8957)
* [Alex Tsankov](https://github.com/antsankov)

# Promotional campaign

## Description
Our promotional campagin will be based on graphing different actions over time for different products. We can take the HTTP requests for the different products and judge customer interest. 

Some of the data point that we might pay attention to are: 

1. Products that me might be gaining in popularity, but are still relatively unpopular.
2. Which days of the week are the best in terms of sales. 
3. Which types of games are most purchased. 
4. Which games are least popular. 

## Rationale 1

```
{{sourcetype=access_* action = "purchase" OR "addtocart" | timechart count(action) by productId useother=f usenull=f limit=16}}
```
![Rationale 1](http://i.imgur.com/7gY7AHb.png)
This shows products that are added to the cart and actually pruchased, which can show us broad interest in a product

## Rationale 2

```
sourcetype=access_* productId=* action="purchase" | timechart count by categoryId limit=16 useother=false
```
![screenshot of a data table or a graph or both](https://www.dropbox.com/s/s1jjwbsvue5u4fs/Screenshot%202014-09-08%2018.20.03.png?dl=1) 
Strategy games are wildly popular in our stores, let's focus more resources on that.

## Rationale 3

```
sourcetype=access_* categoryId=STRATEGY | timechart count by productId usenull=f
```
![Rationale 3 ](http://i.imgur.com/qEG7bye.png)
The graph clearly indicates that out of the puppies vs zombies game is typically the least popular of all the strategy games offered.


## Rationale 4

```
sourcetype=access_* | top productId by date_wday limit=1
```
![Rationale 5](http://imgur.com/aNiNyLz.png) 
This shows the top product of each given day of the week.

# Loyalty program

## Description
{{an-one-paragraph-description}}

## Rationale 1

```
sourcetype=access_* action=purchase categoryId=STRATEGY productId!=pz_sg_g05 | chart count by clientip
```
![Imgur](http://i.imgur.com/etdU50u.png)
We may want to specifically talk to these clients who enjoy strategy games but have not explored our less popular strategy "Puppies vs Zombies" game.

## Rationale 2

{{one more, use-the-same-template-structure-as-before}}

## Rationale 3

{{at least three, use-the-same-template-structure-as-before}}

## Rationale 4

```
sourcetype=access_* | timechart c(action) by clientip usenull=f useother=f
```
![Rationale 4](http://imgur.com/qN6pT1E.png) 
This shows the top transactions by clientIp. We can use this to quickly find the top clients for a given day. 

## Rationale 5

```
sourcetype=access_* | top clientip by date_wday limit=1
```
![Rationale 5](http://imgur.com/pX4XVHk.png) 
This shows the top IP addresses of each given day of the week.
