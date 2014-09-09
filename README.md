# Team Members

* [Ryan Roden](www.github.com/rodenr)
* [name-of-a-team-member](URL to this member's github account)
* [Niklas Fejes](www.github.com/nfejes)
* [name-of-a-team-member](URL to this member's github account)
* [name-of-a-team-member](URL to this member's github account)

# Promotional campaign

## Description
{{an-one-paragraph-description}}

## Rationale 1

```
sourcetype=access_* status=200 action=* | stats count(eval(action="view")) AS "Views", count(eval(action="purchase")) AS "Purchases" by productId | eval Ratio=(Purchases/Views) | sort -Ratio
```
![rationale 1](rationale1.png?raw=true) 
The graph shows the ratio between purchases and views, and shows that the product 
`CU-PG-G06` (Curling 2014) has the least purchases per view.

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
