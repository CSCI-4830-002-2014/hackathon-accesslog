# Team Members

* [Ryan Roden](www.github.com/rodenr)
* [Chris Wittenberg](https://github.com/cwitty1919t)
* [Michael Fyk](https://github.com/thefyk)
* [Niklas Fejes](www.github.com/nfejes)

# Promotional campaign

## Description
The goal of this promotional campaign is to target the product with the lowest purchases per view and offer a discount in order to drive sales.

## Rationale 1

```
sourcetype=access_* status=200 action=* | stats count(eval(action="view")) AS "Views", count(eval(action="purchase")) AS "Purchases" by productId | eval Ratio=(Purchases/Views) | sort -Ratio
```
![rationale 1](rationale1.png?raw=true) 
The graph shows the ratio between purchases and views, and shows that the product 
`CU-PG-G06` (Curling 2014) has the least purchases per view.


# Loyalty program

## Description
High-Buyers: We find our highest-buying customers and offer a discount with our product with the least purchases per view

## Rationale 1

```
sourcetype=access_* | timechart count(eval(action="purchase")) As "Purchases" by clientip useother=f
```
![screenshot of a data table or a graph or both](image.png?raw=true) 
Find the highest buying customers

