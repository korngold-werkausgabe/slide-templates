---
marp: true
theme: ewk-wa
paginate: true
date: today
footer: 'Korngold-Werkausgabe | Names | Topic'
---

<!-- _class: title  -->
<!-- paginate: false -->
# Title

## Subtitle

---
<!-- paginate: true -->

# First Slide

- First
- Second
- Third
- [Jump to slide 4](#4)

<!-- 
I'm a spreakers note.
-->

---

# Second Slide

> What a wonderful quote.
<p class="small">Description</p>

---

# Table 

| Head1 | Head2 |
|---------------|---|
| Row 1 Col 1 | Row 1 Col 2 |
| Row 2 Col 1 | Row 2 Col 2 |

---

# Image
![Alt Description](./imgs/image.png)
<p class="small">Description</p>

---

# Video
<video controls>
  <source src="./video/video.mp4" type="video/mp4">
</video>
<p class="small">Description</p>

---

# Audio
 <audio controls>
  <source src="./audio/music.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>
<p class="small">Description</p>

---

# Code

```html
<html>
    <h1>Heading</h1>
    <p>Lorem impsum</p>
</html>
```

--- 
<!-- _class: split -->

# Split slide

Split the whole slide in two equal parts

---

# Two cols layout

Allows to add fixed columns

<div class="cols-2">
    <div>
        First column
    </div>
    <div>
        Second column
    </div>
</div>

---

# Mermaid

Preview only works in Obsidian.
For usage in VS-Code: 
- [markdown-mermaid](https://marketplace.visualstudio.com/items/?itemName=bierner.markdown-mermaid) and 
- disable security settings for preview.

<div class="mermaid">
classDiagram
    class Work
	Work --> Expression : hasExpression

		class RobinHood
		RobinHood -- Version1

	class Expression
	Expression --> Work : isExpressionOf
	Expression --> SubExpression : hasSubexpression

	class SubExpression
	SubExpression --> Expression : isSubexpressionOf
	SubExpression --> Manifestation : hasManifestation

		class Version1
		
		Version1 -- Drafts
		Version1 -- ShortNotation
		Version1 -- FullNotation
		
		class Drafts
		
		Drafts -- CueSheets
		Drafts -- Sketches
		
		class ShortNotation
		
		ShortNotation -- ShortScore
		ShortNotation -- ConductorScore
		
		class FullNotation
		
		FullNotation -- FullScore
		FullNotation -- Parts

	class Manifestation
	Manifestation --> SubExpression : isManifestationOf
	Manifestation --> Item : hastItem
		
		class CueSheets
		class Sketches
		class ShortScore
		class ConductorScore
		class FullScore
		class Parts

	class Item
	Item --> Manifestation : isItemOf
</div>

<!-- Put this script at the end of Markdown file. -->
<script type="module">
import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
mermaid.initialize({ startOnLoad: true });

window.addEventListener('vscode.markdown.updateContent', function() { mermaid.init() });
</script>