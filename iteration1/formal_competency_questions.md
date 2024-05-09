# Formal Competency Questions

## CQ_1
What are all the explicit mentions of Software1 in Article1?
```
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ExplicitMention .
  ?mention mito:hasMentionedEntity mito:Software1 .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```

## CQ_2
What are all the explicit mentions of Methodology1 in Article1
```
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 


SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ExplicitMention .
  ?mention mito:hasMentionedEntity mito:Methodology1 .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```

## CQ_3
What are all the explicit mentions of Dataset1 in Article1?

```
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ExplicitMention .
  ?mention mito:hasMentionedEntity mito:Dataset1 .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```

## CQ_4
What are all the implicit mentions of Person1 in Article1?
```
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 


SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ExplicitMention .
  ?mention mito:hasMentionedEntity mito:Person1 .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```

## CQ_5
What are all the implicit mentions of Theory1 in Article1?
```
PREFIX mito: <https://github.com/matteo-guenci/MiTO/blob/main/MiTO%20Ontology/MiTO_Samod_it_1.owl> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ImplicitMention .
  ?mention mito:hasMentionedEntity mito:Theory1 .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```

## CQ_6
What are all the implicit mentions in Article1?
```
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ImplicitMention .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```

## CQ_7
What are all the explicit mentions in Article1?
```
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ExplicitMention .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```

## CQ_8
Who and what is mentioned by Article 1?

PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?thing
WHERE {
	?thing mito:isMentionedBy mito:Article1.
	}

## CQ_9
What are all the explicit mentions of Dataset3 in Article4 and Article5?


PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ExplicitMention .
  ?mention mito:hasMentionedEntity mito:Dataset3 .
  ?mention mito:hasMentioningEntity mito:Article4 .
  ?mention mito:hasMentioningEntity mito:Article5 .
}

ALTERNATIVELY (if "Article4 or Article5" is required as clause)

PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT DISTINCT ?mention
WHERE {
  { ?mention mito:hasMentionType mito:ExplicitMention .
    ?mention mito:hasMentionedEntity mito:Dataset3 .
    ?mention mito:hasMentioningEntity mito:Article4 . }
  UNION
  { ?mention mito:hasMentionType mito:ExplicitMention .
    ?mention mito:hasMentionedEntity mito:Dataset3 .
    ?mention mito:hasMentioningEntity mito:Article5 . }
}


## CQ_10
What are all the explicit mentions of Methodology1 in Article4 and Article5?

PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT DISTINCT ?mention
WHERE {
  { ?mention mito:hasMentionType mito:ExplicitMention .
    ?mention mito:hasMentionedEntity mito:Methodology1 .
    ?mention mito:hasMentioningEntity mito:Article4 . }
  UNION
  { ?mention mito:hasMentionType mito:ExplicitMention .
    ?mention mito:hasMentionedEntity mito:Methodology1 .
    ?mention mito:hasMentioningEntity mito:Article5 . }
}

## CQ_11
What are all the mentions in Article4 and Article5 that mention Dataset3 and Methodology1?

PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  { ?mention mito:hasMentioningEntity mito:Article4 .
    ?mention mito:hasMentionedEntity mito:Dataset3 .
    ?mention mito:hasMentionedEntity mito:Methodology1 . }
  UNION
  { ?mention mito:hasMentioningEntity mito:Article5 .
    ?mention mito:hasMentionedEntity mito:Dataset3 .
    ?mention mito:hasMentionedEntity mito:Methodology1 . }
}

## CQ_12
Who and what is mentioned by Article4 and Article5?


PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?thing
WHERE {
	?thing mito:isMentionedBy mito:Article4.
  ?thing mito:isMentionedBy mito:Article5.
	}

PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT DISTINCT ?thing
WHERE {
  {?thing mito:isMentionedBy mito:Article4.}
  UNION
  {?thing mito:isMentionedBy mito:Article5.}
}

ALTERNATIVELY (same logic as before "or" instad of "and")
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT DISTINCT ?thing
WHERE {
  { ?thing mito:isMentionedBy mito:Article4.
}
  UNION
  { 	?thing mito:isMentionedBy mito:Article5.}
}

## CQ_13
What are all the mentions in Article4 that mention Dataset3?
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionedEntity mito:Dataset3.
  ?mention mito:hasMentioningEntity miti:Article4.
}

## CQ_14
What are all the mentions in Article5 that mention Methodology1?

PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionedEntity mito:Methodology1.
  ?mention mito:hasMentioningEntity mito:Article5.
}

## CQ_15
What are all the explicit mentions in Article4 and Article5?

PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ExplicitMention.
  ?mention mito:hasMentioningEntity mito:Article4.
  ?mention mito:hasMentioningEntity mito:Article5.
}

# CQ_16
Which Article does mention Software2 or Theory3?

PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT DISTINCT ?article
WHERE {
  {?article mito:mentions mito:Software2.}
UNION
  {?article mito:mentions mito:Theory3.}
}