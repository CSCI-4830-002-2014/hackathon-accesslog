# Team Members

* [Ryan Roden](www.github.com/rodenr)
* [Chris Wittenberg](https://github.com/cwitty1919)
* [name-of-a-team-member](URL to this member's github account)
* [name-of-a-team-member](URL to this member's github account)
* [name-of-a-team-member](URL to this member's github account)

# Promotional campaign

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

# Loyalty program

## Description
{{High-Buyers: We find our highest-buying customers and offer a discount with our product with the least purchases per view}}

## Rationale 1

```
sourcetype=access_* | timechart count(eval(action="purchase")) As "Purchases" by clientip useother=f
```
![screenshot of a data table or a graph or both](image.png?raw=true) 
{{Find the highest buying customers}}

## Rationale 2

{{one more, use-the-same-template-structure-as-before}}

## Rationale 3

{{at least three, use-the-same-template-structure-as-before}}

## Rationale N

{{more if desired, use-the-same-template-structure-as-before}}
