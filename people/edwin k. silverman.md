---
tags: 🧍
aliases:
  - E.K. Silverman
  - E. K. Silverman
  - Edwin K. Silverman
  - E. Silverman
  - Edwin Silverman
cssclass: idea
publish: true
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
  contains(authors, "E.K. Silverman")
  or contains(authors, "E. K. Silverman")
  or contains(authors, "Edwin K. Silverman")
  or contains(authors, "E. Silverman")
  or contains(authors, "Edwin Silverman")
)
```
