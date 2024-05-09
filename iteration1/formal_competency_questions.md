# Formal Competency Questions

## CQ_1
What are all the explicit mentions of software-1 in article-1?
```
PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:explicit-mention .
  ?mention mito:hasMentionedEntity mito:software-1 .
  ?mention mito:hasMentioningEntity mito:article-1 .
}
```

## CQ_2
What are all the explicit mentions of methodology-1 in article-1
```
PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:explicit-mention .
  ?mention mito:hasMentionedEntity mito:methodology-1 .
  ?mention mito:hasMentioningEntity mito:article-1 .
}
```

## CQ_3
What are all the explicit mentions of dataset-1 in article-1?

```
PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:explicit-mention .
  ?mention mito:hasMentionedEntity mito:dataset-1 .
  ?mention mito:hasMentioningEntity mito:article-1 .
}
```

## CQ_4
What are all the implicit mentions of person-1 in article-1?
```
PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:explicit-mention .
  ?mention mito:hasMentionedEntity mito:person-1 .
  ?mention mito:hasMentioningEntity mito:article-1 .
}
```

## CQ_5
What are all the implicit mentions of theory-1 in article-1?
```
PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:implicit-mention .
  ?mention mito:hasMentionedEntity mito:theory-1 .
  ?mention mito:hasMentioningEntity mito:article-1 .
}
```

## CQ_6
What are all the implicit mentions in article-1?
```
PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:implicit-mention .
  ?mention mito:hasMentioningEntity mito:article-1 .
}
```

## CQ_7
What are all the explicit mentions in article-1?
```
PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:explicit-mention .
  ?mention mito:hasMentioningEntity mito:article-1 .
}
```

## CQ_8
Who and what is mentioned by article-1?

PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?thing
WHERE {
	?thing mito:isMentionedBy mito:article-1.
	}

## CQ_9
What are all the explicit mentions of dataset-3 in article-4 and article-5?


PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:explicit-mention .
  ?mention mito:hasMentionedEntity mito:dataset-3 .
  ?mention mito:hasMentioningEntity mito:article-4 .
  ?mention mito:hasMentioningEntity mito:article-5 .
}

ALTERNATIVELY (if "article-4 or article-5" is required as clause)

PREFIX mito: <http://purl.org/spar/mito#>

SELECT DISTINCT ?mention
WHERE {
  { ?mention mito:hasMentionType mito:explicit-mention .
    ?mention mito:hasMentionedEntity mito:dataset-3 .
    ?mention mito:hasMentioningEntity mito:article-4 . }
  UNION
  { ?mention mito:hasMentionType mito:explicit-mention .
    ?mention mito:hasMentionedEntity mito:dataset-3 .
    ?mention mito:hasMentioningEntity mito:article-5 . }
}


## CQ_10
What are all the explicit mentions of methodology-1 in article-4 and article-5?

PREFIX mito: <http://purl.org/spar/mito#>

SELECT DISTINCT ?mention
WHERE {
  { ?mention mito:hasMentionType mito:explicit-mention .
    ?mention mito:hasMentionedEntity mito:methodology-1 .
    ?mention mito:hasMentioningEntity mito:article-4 . }
  UNION
  { ?mention mito:hasMentionType mito:explicit-mention .
    ?mention mito:hasMentionedEntity mito:methodology-1 .
    ?mention mito:hasMentioningEntity mito:article-5 . }
}

## CQ_11
What are all the mentions in article-4 and article-5 that mention dataset-3 and methodology-1?

PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  { ?mention mito:hasMentioningEntity mito:article-4 .
    ?mention mito:hasMentionedEntity mito:dataset-3 .
    ?mention mito:hasMentionedEntity mito:methodology-1 . }
  UNION
  { ?mention mito:hasMentioningEntity mito:article-5 .
    ?mention mito:hasMentionedEntity mito:dataset-3 .
    ?mention mito:hasMentionedEntity mito:methodology-1 . }
}

## CQ_12
Who and what is mentioned by article-4 and article-5?

PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?thing
WHERE {
	?thing mito:isMentionedBy mito:article-4.
  ?thing mito:isMentionedBy mito:article-5.
	}

PREFIX mito: <http://purl.org/spar/mito#>

SELECT DISTINCT ?thing
WHERE {
  {?thing mito:isMentionedBy mito:article-4.}
  UNION
  {?thing mito:isMentionedBy mito:article-5.}
}

ALTERNATIVELY (same logic as before "or" instad of "and")
PREFIX mito: <http://purl.org/spar/mito#>

SELECT DISTINCT ?thing
WHERE {
  { ?thing mito:isMentionedBy mito:article-4.
}
  UNION
  { 	?thing mito:isMentionedBy mito:article-5.}
}

## CQ_13
What are all the mentions in article-4 that mention dataset-3?
PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionedEntity mito:dataset-3.
  ?mention mito:hasMentioningEntity miti:article-4.
}

## CQ_14
What are all the mentions in article-5 that mention methodology-1?

PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionedEntity mito:methodology-1.
  ?mention mito:hasMentioningEntity mito:article-5.
}

## CQ_15
What are all the explicit mentions in article-4 and article-5?

PREFIX mito: <http://purl.org/spar/mito#>

SELECT ?mention
WHERE {
  ?mention mito:hasMentionType mito:explicit-mention.
  ?mention mito:hasMentioningEntity mito:article-4.
  ?mention mito:hasMentioningEntity mito:article-5.
}

# CQ_16
Which article- does mention software-2 or theory-3?

PREFIX mito: <http://purl.org/spar/mito#>

SELECT DISTINCT ?article
WHERE {
  {?article mito:mentions mito:software-2.}
UNION
  {?article mito:mentions mito:theory-3.}
}