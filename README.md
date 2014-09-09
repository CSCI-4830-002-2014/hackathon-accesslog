# Team Members

* [Josh Ferge](https://github.com/JoshFerge)
* [Irfan Nadiadi](https://github.com/Irfann1)
* [Justin McBride](https://github.com/dare599z)
* [Manpreet Singh](https://github.com/msg425)
* [LoganBates](https://github.com/LoganBates)

# Promotional campaign

## Description
We want to make a campaign for a product whose sales go down during a certain span of days. We will choose the product which we believe most suffers during those certain days and plan a promotion for those days. We will futher ananlyze this game to make our promotion more effective. 


## Rationale 1
We wanted to see which product sales go down during which days during the week. We will use this query to choose which product to create a promotion for. We decided to use Resistance Suit of Provolone because it suffers from severve midweek slump.
```
sourcetype=access_* productId=* | timechart count(eval(action="purchase")) by productName span=1h useother=f
```
![screenshot of a data table or a graph or both](Hack1.png?raw=true) 
One can see that Resistance Suit of Provolone suffers from a midweek slump.

## Rationale 2

We wanted to further examine Resistance Suit of Provolone to see if it was the proper game to run a promotion for. We wanted compare top products removed from cart to top products purchased. 
```
sourcetype=access_* productId cart.do action=remove | table clientip, action, productId, productName, date_month, date_mday, date_wday | top productName

and 

sourcetype=access_* productId cart.do action=purchase | table clientip, action, productId, productName, date_month, date_mday, date_wday | top productName
```
![screenshot of a data table or a graph or both](Hack2.png?raw=true)
![screenshot of a data table or a graph or both](Hack3.png?raw=true)
We compared these charts to verify that the game we're analyzing was the correct one.
## Rationale 3
We wanted to see if the other game that sufferd this midweek slum (Orvil) had any correlation to our game we were analyzing, perhaps as a way to package these products together to increase sales.
```
sourcetype=access_* productId=* productName="Orvil the Wolverine" OR productName="Fire Resistance Suit of Provolone"| timechart count(eval(action="purchase")) by productName span=1h useother=f
```
![screenshot of a data table or a graph or both](Hack4.png?raw=true)
We can see that these games suffer on the same days! :(

# Loyalty program

## Description
For loyal customer who purchase 25 games, they are automatically entered into our loyalty program. Many of the customers on the website are purchasing 20 - 80 games and as a reward for loyalty, we would like to reward those customers with 5% off on all future purchases. Further queries show that many customers purchase multiple copies of the same game, likely to gift to friends. To encourage more purchases, we will offer a significant discount if a customer is gifting a game they already own.

## Rationale 1

```
{{splunk query producing the table or graph below}}
```
![screenshot of a data table or a graph or both](image.png?raw=true) 
{{write-an-one-sentence-caption}}

## Rationale 2

{{one more, use-the-same-template-structure-as-before}}

## Rationale 3

This tells us how many games each person purchased. This way we can set a number for the bottom tier of games purchased for the loyalty program.
```
sourcetype=access_* action=purchase | stats count by clientip | rename clientip as Customer | rename count as "Number Purchased"
```
![screenshot of a data table or a graph or both](Hack3Loyal.png?raw=true)
One can see that numerous customers have purchased a game more than one time.