---
tags:
  - _type/person
  - e_k_silverman
aliases:
  - E.K. Silverman
  - E. K. Silverman
  - Edwin K. Silverman
  - E. Silverman
  - Edwin Silverman
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
  contains(authors, "E.K. Silverman")
  or contains(authors, "E. K. Silverman")
  or contains(authors, "Edwin K. Silverman")
  or contains(authors, "E. Silverman")
  or contains(authors, "Edwin Silverman")
)
```
