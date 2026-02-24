# slidev-theme-whulug

[![NPM version](https://img.shields.io/npm/v/slidev-theme-whulug?color=3AB9D4&label=)](https://www.npmjs.com/package/slidev-theme-whulug)

A WHULUG standard presentation theme for [Slidev](https://github.com/slidevjs/slidev).

<!--
  Learn more about how to write a theme:
  https://sli.dev/guide/write-theme.html
--->

<!--
  run `npm run dev` to check out the slides for more details of how to start writing a theme
-->

<!--
  Put some screenshots here to demonstrate your theme

  Live demo: [...]
-->

## Install

Add the following frontmatter to your `slides.md`. Start Slidev then it will prompt you to install the theme automatically.

<pre><code>---
theme: <b>WHULUG</b>
---</code></pre>

Learn more about [how to use a theme](https://sli.dev/guide/theme-addon#use-theme).

## Layouts

This theme provides the following layouts:

| Layout | Description | Usage |
|--------|-------------|-------|
| `cover` | Cover page with background image support | `layout: cover` |
| `disclaimer` | Disclaimer/attribution page | `layout: disclaimer` |
| `toc` | Table of contents with auto-numbering | `layout: toc` |
| `page` | Standard content page | `layout: page` |
| `section` | Chapter/section divider with PART letter | `layout: section` |
| `two-cols` | Two-column layout | `layout: two-cols` |
| `center` | Centered content layout | `layout: center` |

### Cover Layout

```yaml
---
layout: cover
background: https://example.com/image.jpg
---

# Title

:: subtitle ::
Subtitle text
```

### TOC Layout

```yaml
---
layout: toc
start: 0  # Start numbering from 0 (optional, default: 1)
---

- Chapter 1: Introduction
- Chapter 2: Main Content
- Chapter 3: Conclusion
```

### Section Layout

```yaml
---
layout: section
number: '01'
---

# Chapter Title

:: subtitle ::
Chapter Subtitle
```

Configure PART letter mapping in frontmatter:
```yaml
---
sectionOffset: 1  # 01->A (default), set to 0 for 00->A
---
```

### Two-Cols Layout

```yaml
---
layout: two-cols
---

:: left ::

Left column content

:: right ::

Right column content

:: header ::
Page Header
```

### Page Layout

```yaml
---
layout: page
---

# Page Title

Content here...

:: header ::
Header Text
```

### Center Layout

```yaml
---
layout: center
---

# Centered Title

## Subtitle

Centered content...

:: header ::
Header Text
```

## Components

This theme provides the following components:

### BottomBar

A fixed bottom bar that appears on all pages showing:
- Current mode/status
- Logo/brand
- File path
- Current date

The BottomBar is automatically included in all layouts.

## Configuration

### Global Settings

Add these to your `slides.md` frontmatter:

```yaml
---
# Theme settings
theme: whulug
canvasWidth: 980

# Fonts
fonts:
  sans: 'Noto Sans SC'
  mono: 'Fira Code'

# Section numbering offset
# 1: 01->A, 02->B (default)
# 0: 00->A, 01->B
sectionOffset: 1
---
```

### Cover Background

```yaml
---
layout: cover
background: https://your-image-url.com/image.jpg
---
```

## Contributing

- `npm install`
- `npm run dev` to start theme preview of `example.md`
- Edit the `example.md` and style to see the changes
- `npm run export` to generate the preview PDF
- `npm run screenshot` to generate the preview PNG