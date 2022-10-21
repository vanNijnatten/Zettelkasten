---
tags: 🏡
aliases: [home]
cssclass: home
publish: true
---
# Zettelkasten project for my PhD
This is a new zettelkasten project, to organize my thoughts on the many papers I read for my PhD. The program I use to take these notes is [Obsidian](https://www.obsidian.md). Therefore the notes are written in plain text, using Obsidian [markdown](https://help.obsidian.md/How+to/Format+your+notes), with some [modifications](https://help.obsidian.md/How+to/Use+callouts) and [extensions](https://obsidian.md/plugins). It is even possible to include [flashcards](https://github.com/NeuraCache/markdown-flashcards-spaced-repetition).

See also [[note-taking]] and [[tags]].

## Entry points to the digital garden
 - [[databases]]
 - [[gene]]
 - [[immune-system]]
 - [[lung-disease]]
 - [[signaling-pathway]]
 - [[snp]]
 - [[writing]]

**Current Focus (papers):**
```dataview
list
from #🔖  and #🏛 and -#🏡 
where !contains(file.name, "template")
```

**Current Focus (ideas):**
```dataview
list
from #🔖  and -#🏛 and -#🏡 
where !contains(file.name, "template")
```
