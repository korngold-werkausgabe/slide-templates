# slide-templates
This repository contains templates for different presentation tools

## Marp

### Obsidian

1. Install Marp Slides Plugin.
1. Clone repository to vault or link to templates folder: `ln -s /path/to/repo /path/in/vault`.
1. Add (relative) `path/in/vault/` in Marp Slides Config: `Preferences` > `Marp Slides` > `Theme Path`

### VS-Code
1. Install [Marp plugin](https://marketplace.visualstudio.com/items/?itemName=marp-team.marp-vscode).
1. Add marp settings from `settings.json.template` to local `.vscode/settings.json`.
1. For an example of the common and custom functions use the `index.md` as a starting point.

### Custom CSS

#### Smaller font for descriptions/bibliographic information etc.

```html
<p class="small">Description</p>
```

#### Audio Integration

```html
<audio controls>
  <source src="./audio/music.mp3" type="audio/mpeg">
Your browser does not support the audio element.
</audio>
```

#### Video Integration
```html
<video controls>
  <source src="./video/video.mp4" type="video/mp4">
</video>
```

#### Split slides

The first option adds a class attribute to the section and splits the whole slide in to columns.

```html
<!-- _class: split -->
```

The second option defines two columns within a div.

<div class="cols-2">
    <div>
        First column
    </div>
    <div>
        Second column
    </div>
</div>

#### For Mermeid Support

- Add [markdown-mermaid](https://marketplace.visualstudio.com/items/?itemName=bierner.markdown-mermaid) plugin and 
- disable security settings for preview.

```html
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
``` 

```html
<!-- Put this script at the end of Markdown file. -->
<script type="module">
import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
mermaid.initialize({ startOnLoad: true });

window.addEventListener('vscode.markdown.updateContent', function() { mermaid.init() });
</script>
```