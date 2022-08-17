---
# theme id or package name
# Learn more: https://sli.dev/themes/use.html
theme: seriph
# title of your slide, will auto infer from the first header if not specified
title: 'REST API Architektur'
# titleTemplate for the webpage, `%s` will be replaced by the page's title
titleTemplate: '%s - Slidev'
# information for your slides, can be a markdown string
info: false

# enabled pdf downloading in SPA build, can also be a custom url
download: false
# filename of the export file
exportFilename: 'slidev-exported'
# syntax highlighter, can be 'prism' or 'shiki'
highlighter: 'prism'
# show line numbers in code blocks
lineNumbers: true
# enable monaco editor, can be boolean, 'dev' or 'build'
monaco: 'dev'
# download remote assets in local using vite-plugin-remote-assets, can be boolean, 'dev' or 'build'
remoteAssets: false
# controls whether texts in slides are selectable
selectable: true
# enable slide recording, can be boolean, 'dev' or 'build'
record: 'dev'

# force color schema for the slides, can be 'auto', 'light', or 'dark'
colorSchema: 'auto'
# router mode for vue-router, can be "history" or "hash"
routerMode: 'history'
# aspect ratio for the slides
aspectRatio: '16/9'
# real width of the canvas, unit in px
canvasWidth: 980
# used for theme customization, will inject root styles as `--slidev-theme-x` for attribute `x`
themeConfig:
  primary: '#5d8392'

# favicon, can be a local file path or URL
favicon: 'https://cdn.jsdelivr.net/gh/slidevjs/slidev/assets/favicon.png'
# URL of PlantUML server used to render diagrams
plantUmlServer: 'https://www.plantuml.com/plantuml'
# fonts will be auto imported from Google fonts
# Learn more: https://sli.dev/custom/fonts
fonts:
  sans: 'Roboto'
  serif: 'Roboto Slab'
  mono: 'Fira Code'

# default frontmatter applies to all slides
defaults:
  layout: 'default'
  # ...

# drawing options
# Learn more: https://sli.dev/guide/drawing.html
drawings:
  enabled: true
  persist: false
  presenterOnly: false
  syncAll: true

layout: cover
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
---

# REST API Architektur

Was und wie machen wir REST?

---
layout: full
---

<Youtube src="https://youtube.com/embed/kPrTMj-BK14?t=19" width="100%" height="100%"/>

---
class: text-center
---

# Slides & Code

## github.com/n1LWeb/REST-API-Architecture

---

# Agenda

- Was bedeutet REST, was ist REST

---
layout: image-left
---



# Roy T. Fielding
Roy Thomas Fielding (* 1965 in Laguna Beach, Kalifornien, USA) ist ein US-amerikanischer Informatiker, einer der Hauptautoren der HTTP-Spezifikation, Mitgründer und Vorsitzender der Apache Software Foundation.

Fielding erhielt im Jahr 2000 seinen Doktorgrad von der University of California, Irvine für seine Dissertation Architectural Styles and the Design of Network-based Software Architectures, die den Representational State Transfer (REST) als eine Schlüsselarchitektur für das World Wide Web beschreibt und große Anerkennung bekam.

http://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm


