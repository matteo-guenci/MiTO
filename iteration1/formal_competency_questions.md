# Formal Competency Questions

## CQ_1.1
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

## CQ_1.2
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

## CQ_1.3
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

## CQ_1.4
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

## CQ 1.5
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

## CQ 1.6
What are all the implicit mentions in Article1?
```
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ImplicitMention .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```

## CQ 1.7
What are all the explicit mentions in Article1?
```
PREFIX mito: <https://raw.githubusercontent.com/matteo-guenci/MiTO/main/MiTO%20Ontology/MiTO_Samod_it_1.owl#> 

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:ExplicitMention .
  ?mention mito:hasMentioningEntity mito:Article1 .
}
```