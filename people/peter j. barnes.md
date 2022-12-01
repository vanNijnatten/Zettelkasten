---
tags: 💨 💡
aliases:
  - P.J. Barnes
  - P. J. Barnes
  - Peter J. Barnes
  - P. Barnes
  - Peter Barnes
cssclass: idea
publish: false
---
## About

## Research

## Papers
```dataview
list title
from "papers" and -#🏡 
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
