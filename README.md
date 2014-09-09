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

{{one more, use-the-same-template-structure-as-before}}

## Rationale 3

{{at least three, use-the-same-template-structure-as-before}}

## Rationale N

{{more if desired, use-the-same-template-structure-as-before}}

# Loyalty program

## Description
{{an-one-paragraph-description}}

## Rationale 1

```
{{splunk query producing the table or graph below}}
```
![screenshot of a data table or a graph or both](image.png?raw=true) 
{{write-an-one-sentence-caption}}

## Rationale 2

{{one more, use-the-same-template-structure-as-before}}

## Rationale 3

{{at least three, use-the-same-template-structure-as-before}}

## Rationale N

{{more if desired, use-the-same-template-structure-as-before}}
