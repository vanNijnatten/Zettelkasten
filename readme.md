---
tags: 🏡
aliases: [home]
cssclass: home
publish: true
---
# Zettelkasten project for my PhD
This is a new zettelkasten project, to organize my thoughts on the many papers I read for my PhD. The program I use to take these notes is [Obsidian](https://www.obsidian.md). Therefore the notes are written in plain text, using Obsidian [markdown](https://help.obsidian.md/How+to/Format+your+notes), with some [modifications](https://help.obsidian.md/How+to/Use+callouts) and [extensions](https://obsidian.md/plugins). It is even possible to include [flashcards](https://github.com/NeuraCache/markdown-flashcards-spaced-repetition).

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

## How to take notes from a journal article
1. Title - pull out your keywords
2. Abstract - results + methods
3. Intro - first and last paragraph of Intro
4. Results - scroll through subsection headings of the Results
5. Conclusion - quick summary of what this paper found <br />At this point you don't need to do anything else UNLESS you want to go more in depth
6. Results - key results/figures
7. Limitations
8. References - pull out useful ones

## How to take general notes
**Cornell Metod**
Title, notes, keywords, summary

## Tags
#🏡 - Home (entry point)

#🏛 - Permament note (Single idea, understandable, linked)
#💨 - Fleeting note

#📚 - Book
#🔬 - Basic research
#🚀 - Literature review
#💡 - Idea

#⚕️ - Cohort
#📱 - Tool

#👓 - To read
#✍️ - To edit

**Tags to color the  graph view**
#🔖 - What I am editing atm
#🌟 - Very important
#⭐️ - Important
#📒 - Writing ideas

**Types of output**
#📕 - Article (Research/Review etc)
#📗 - Blogpost
#📘 - ???
#🧑‍🏫 - Presentation
