---
tags: _home
aliases: [home]
cssclass: home
publish: true
---
# Zettelkasten project for my PhD
This is a new zettelkasten project, to organize my thoughts on the many papers I read for my PhD. The program I use to take these notes is [Obsidian](https://www.obsidian.md). Therefore the notes are written in plain text, using Obsidian [markdown](https://help.obsidian.md/How+to/Format+your+notes), with some [modifications](https://help.obsidian.md/How+to/Use+callouts) and [extensions](https://obsidian.md/plugins). It is even possible to include [flashcards](https://github.com/NeuraCache/markdown-flashcards-spaced-repetition).

See also [[note-taking|note taking]], [[ask-questions|ask questions]] and [[tags]].

## Entry points to the digital garden
 - [[lung-disease]]
 - [[writing-ideas]]

**To Read:**
```dataview
list 
from #_status/to_read and -#_home
where !contains(file.name, "template")
```

**To Edit:**
```dataview
list 
from #_status/to_edit and -#_home
where !contains(file.name, "template")
```

**To Do:**
```dataview
list 
from #_status/to_do and -#_home
where !contains(file.name, "template")
```

**Doing:**
```dataview
list 
from #_status/doing and -#_home
where !contains(file.name, "template")
```

**Done:**
```dataview
list
from #_status/done  and -#_home 
where !contains(file.name, "template")
```

## Plugins used for this Obsidian project
- [Obsidian Citations](https://github.com/hans/obsidian-citation-plugin)
- [Obsidian Footnotes](https://github.com/MichaBrugger/obsidian-footnotes)
- [Highlightr](https://github.com/chetachiezikeuzor/Highlightr-Plugin)
- [Editor Syntax Highlighter](https://github.com/deathau/cm-editor-syntax-highlight-obsidian)
- And some more normal ones.