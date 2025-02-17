# HTML

HTML (**HyperText Markup Language**) is the most basic building block of the Web. It defines the meaning and structure of web content. Other technologies besides HTML are generally used to describe a web page's appearance/presentation (CSS) or functionality/behavior (JavaScript).

"Hypertext" refers to links that connect web pages to one another, either within a single website or between websites. Links are a fundamental aspect of the Web. By uploading content to the Internet and linking it to pages created by other people, you become an active participant in the World Wide Web.

---

## Structural Elements

### `<html>`
Root container for all HTML content.  
**Use**: Required as the outer wrapper for every HTML document.

### `<head>`
Contains metadata and linked resources.  
**Use**: For title, stylesheets, scripts, and SEO tags.

### `<body>`
Holds visible page content.  
**Use**: All user-facing content goes here.

---

## Semantic Elements

### `<header>`
Introductory content (titles/navigation).  
**Use**: Top section of the page or articles.

### `<nav>`
Navigation links.  
**Use**: Primary menus or table of contents.

### `<main>`
Primary content area.  
**Use**: Wrap the page's unique content.

### `<article>`
Self-contained composition.  
**Use**: Blog posts, news stories, forum posts.

### `<footer>`
Closing content section.  
**Use**: Page footers or article endings.

---

## Text Elements

### `<h1>` - `<h6>`
Headings (`h1` = most important).  
**Use**: Content hierarchy and SEO structure.

### `<p>`
Paragraph text.  
**Use**: Standard text blocks.

### `<a href="">`
Hyperlink.  
**Use**: Navigation between pages/resources.

### `<strong>`
Important text (bold).  
**Use**: Critical warnings/key points.

### `<em>`
Emphasized text (italic).  
**Use**: Verbal stress in sentences.

---

## Form Elements

### `<form>`
Input container.  
**Use**: User data collection/processing.

### `<input>`
Data field (text/email/file).  
**Use**: Capture user input.

### `<button>`
Clickable action trigger.  
**Use**: Form submission or JavaScript interactions.

### `<select>`
Dropdown selection.  
**Use**: Predefined option lists.

---

## Media Elements

### `<img src="" alt="">`
Embedded image.  
**Use**: Visual content display.

### `<video>`
Video player.  
**Use**: MP4/WebM video playback.

### `<audio>`
Sound player.  
**Use**: MP3/WAV audio playback.

---

## Lists & Tables

### `<ul>` `<ol>` | `<li>`
Unordered/ordered lists.  
**Use**: Item collections (bullet/numbered).

### `<table>` | `<thead>`, `<tbody>` | `<tr>`, `<td>`
Data rows/columns.  
**Use**: Structured information display.

---

## Utility Elements

### `<div>`
Generic container.  
**Use**: Layout organization/styling hooks.

### `<span>`
Inline text container.  
**Use**: Targeted text styling/scripting.

---

## Best Practices

1. Use semantic elements for accessibility.
2. Always include `alt` text for images.
3. Maintain heading hierarchy (`h1` → `h2` → `h3`).
4. Separate structure (HTML), presentation (CSS), and behavior (JS).