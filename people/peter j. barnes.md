---
tags:
  - _type/person
  - p_j_barnes
aliases:
  - P.J. Barnes
  - P. J. Barnes
  - Peter J. Barnes
  - P. Barnes
  - Peter Barnes
cssclasses:
  - idea
publish: true
---
## About

## Research

## Papers
```dataview
list title
from "papers" and -#_home 
where !contains(file.name, "template")
and contains(file.name, "@")
and (
  contains(authors, "P.J. Barnes")
  or contains(authors, "P. J. Barnes")
  or contains(authors, "Peter J. Barnes")
  or contains(authors, "P. Barnes")
  or contains(authors, "Peter Barnes")
)
```
