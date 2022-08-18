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
lineNumbers: false
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

## Was und wie machen wir REST?

Stark angelehnt an die REST Talks von Dylan Beattie

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
- Herobook

---
layout: image-left
image: ./fielding.webp
---

# Roy T. Fielding
Roy Thomas Fielding (* 1965 in Laguna Beach, Kalifornien, USA) ist ein US-amerikanischer Informatiker, einer der Hauptautoren der HTTP-Spezifikation, Mitgründer und Vorsitzender der Apache Software Foundation.

Fielding erhielt im Jahr 2000 seinen Doktorgrad von der University of California, Irvine für seine Dissertation Architectural Styles and the Design of Network-based Software Architectures, die den Representational State Transfer (REST) als eine Schlüsselarchitektur für das World Wide Web beschreibt und große Anerkennung bekam.

http://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm

---
layout: quote
image: fielding.webp
---

<img style="float:left; margin: 1em" src="fielding.webp" width="100"/>

# When given a name, a coordinated set of architectural constraints becomes an architectural style

<v-click>

<br/>

## Ein koordinierter Satz von architektonischen Einschränkungen wird zu einem Architekturstil, wenn er einen Namen erhält.

</v-click>

---
layout: quote
image: fielding.webp
---

<img style="float:left; margin: 1em" src="fielding.webp" width="100"/>

# **REST** is software design on the *scale* of **decades**: every detail is intended to promote software longevity and independent evolution.

# Many of the constraints are directly opposed to short-term efficiency.

<v-click>

## REST ist Softwaredesign für Jahrzehnte: Jedes Detail ist darauf ausgerichtet, die Langlebigkeit und unabhängige Weiterentwicklung der Software zu fördern.

## Viele der Einschränkungen stehen im direkten Gegensatz zur kurzfristigen Effektivität.

</v-click>

---
layout: default
---

# Was bedeutet REST, was ist REST

## 1. Server-Client

```plantuml {scale: 1}
@startuml
node Server {

}

node "Client" as c1 {

}


Server --> c1
@enduml
```

<v-click>

```plantuml {scale: 1}
@startuml
node Server {

}

node "Client" as c1 {

}

node "Client" as c2{

}

node "Client" as c3 {

}

Server --> c1
Server --> c2
Server --> c3

@enduml
```


</v-click>

---
layout: default
---

# Was bedeutet REST, was ist REST

## 2. Stateless

```plantuml {scale: 1}
@startuml
node Server {
  object "Session" as s1
  object "Session" as s2
  object "Session" as s3
}

node "Client" as c1 {

}

node "Client" as c2{

}

node "Client" as c3 {

}

s1 <--> c1
s2 <--> c2
s3 <--> c3

@enduml
```

<v-click>

```plantuml {scale: 1}
@startuml
node Server {
  object "Session" as s1
  object "Session" as s2
  object "Session" as s3
  object "Session" as s4
  object "Session" as s5
  object "Session" as s6
  object "Session" as s7
  object "Session" as s8
  object "Session" as s9
}

node "Client" as c1 {

}

node "Client" as c2{

}

node "Client" as c3 {

}

node "Client" as c4 {

}

node "Client" as c5{

}

node "Client" as c6 {

}

node "Client" as c7 {

}

node "Client" as c8 {

}

node "Client" as c9 {

}

s1 <--> c1
s2 <--> c2
s3 <--> c3
s4 <--> c4
s5 <--> c5
s6 <--> c6
s7 <--> c7
s8 <--> c8
s9 <--> c9

@enduml
```

</v-click>

---
layout: default
---

# Was bedeutet REST, was ist REST

## 2. Stateless

```plantuml {scale: 1}
@startuml
node Server {
  object "Session" as s1
  object "Session" as s2
  object "Session" as s3
  object "Session" as s4
  object "Session" as s5
  object "Session" as s6
  object "Session" as s7
  object "Session" as s8
  object "Session" as s9
}

node server as srv2 {
  object "Session" as s10
}

node "Client" as c1 {

}

node "Client" as c2{

}

node "Client" as c3 {

}

node "Client" as c4 {

}

node "Client" as c5{

}

node "Client" as c6 {

}

node "Client" as c7 {

}

node "Client" as c8 {

}

node "Client" as c9 {

}
Server -[Hidden]> srv2
s1 <--> c1
s2 <--> c2
s3 <--> c3
s4 <--> c4
s5 <--> c5
s6 <--> c6
s7 <--> c7
s8 <--> c8
srv2 x--x c9

@enduml
```

---
layout: two-cols
---

<template v-slot:default>

# Was bedeutet REST, was ist REST

## 3. Cacheable

```plantuml {scale: 1}
@startuml

node Server {
  object "Daten" as d
}

node Client {

}

Client -> Server
d --> Client

@enduml
```

</template>

<template v-slot:right>


```plantuml {scale: 1}
@startuml

node Server {
  object "Daten" as d
}

node Client {
  object "Daten" as d2
}

Server --[hidden]> Client

@enduml
```

</template>

---
layout: default
---

# Was bedeutet REST, was ist REST

## 3. Cacheable

```plantuml {scale: 1}
@startuml

node Server {
  object "Daten" as d
}

node Client {

}

Client -> Server
d --> Client

@enduml
```

---
layout: two-cols
---

<template v-slot:default>

# Was bedeutet REST, was ist REST

## 4. Layered System

```plantuml {scale: 1}
@startuml
node Server {
  object "Daten" as ds
}

node Proxy {
 object "Daten" as dp
}

node "Client" as c1 {
  object "Daten" as dc1
}

node "Client" as c2 {

}

node "Client" as c3 {

}

ds <-- c1
ds --> dp
dp --> dc1

@enduml
```

</template>

<template v-slot:right>
<v-click>

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

```plantuml {scale: 1}
@startuml
node Server {
  object "Daten" as ds
}

node Proxy {
 object "Daten" as dp
}

node "Client" as c1 {
  object "Daten" as dc1
}

node "Client" as c2 {
  object "Daten" as dc2
}

node "Client" as c3 {
  object "Daten" as dc3
}

ds <-- c1
ds --> dp
dp --> dc1
Proxy <-- c2
dp --> dc2
Proxy <-- c3
dp --> dc3


@enduml
```

</v-click>
</template>

---
layout: default
---

# Was bedeutet REST, was ist REST

## 4. Layered System

```plantuml {scale: 0.7}
@startuml
node Server as s1 {

}

node Server as s2 {

}

node Server as s3 {

}

node Server as s4 {

}

node Server as s5 {

}

node "Caching Proxy" as proxy  {

}

node "Security Appliance" as sa{

}

node "Load Balancer" as lb {

}

node "Client" as c1 {
}

node "Client" as c2 {
}

node "Client" as c3 {
}

proxy --> c1
proxy --> c2
proxy --> c3
sa --> proxy
lb --> sa
s1 --> lb
s2 --> lb
s3 --> lb
s4 --> lb
s5 --> lb


@enduml
```

---
layout: default
---

# Was bedeutet REST, was ist REST

## 5. Uniform Interface

<br/>
<br/>

```plantuml {scale: 1.3}
@startuml

rectangle "Uniform Interface" as ui {
  rectangle "Identification\nof Resources" as ir
  rectangle "Manipulation\nthrough\nrepresentation" as mr
  rectangle "Self-\ndescriptive\nmessages" as sdm
  rectangle "Hypermedia\nas the engine\nof application\nstate" as hm
}

ir -[hidden]> mr
sdm -[hidden]> hm
ir --[hidden]> sdm
mr --[hidden]> hm

@enduml
```

---
layout: default
---

# Was bedeutet REST, was ist REST

## 6. Code on Demand (optional)

Der Client kann code übertragen, welcher auf dem Client ausgeführt wird. (bisher noch in keiner API gesehen)

---
layout: default
---

# Was bedeutet REST, was ist REST

## A Set of Architectural Contraints

1. Client Server
1. Stateless
1. Cacheable
1. Layered System
1. Uniform Interface
1. Code-on-demand (optional)

---
layout: default
---

# Herobook

```http
GET / HTTP/1.1

200 OK
Content-Type: application/json
{
  "message": "Welcome to Herobook!"
}

```

---
layout: two-cols
---

<template v-slot:default>

```http
GET /profiles HTTP/1.1

200 OK
Content-Type: application/json
[
  {
    "username": "ironman",
    "name": "Tony Stark"
  }
]
```

</template>
<template v-slot:right>

```http
POST /profiles HTTP/1.1
{
  "username": "blackwidow",
  "name": "Natalia Romanova"
}

201 Created
Location: http://api.herobook.com.local/profiles/blackwidow
{
  "username": "Blackwidow",
  "name": "Natalia Romanova"
}
```

</template>

---
layout: cover
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/539016/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
---

# Einen Tag Später

---
layout: default
---

```http
GET /profiles HTTP/1.1

200 OK
[
  { "username": "ironman", "name": "Tony Stark" },
  { "username": "Blackwidow", "name": "Natalia Romanova" },
  { "username": "spidey", "name": "Peter Parker" },
  
  { /* 2 Millionen Benutzer!!! /* },

  { "username": "Da DevOps Architect", "name": "Marc Lucks" }
]
```

---
layout: cover
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/539016/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
---

# Einen Tag Später

---



https://youtu.be/kPrTMj-BK14?t=912

https://roy.gbiv.com/untangled/2008/rest-apis-must-be-hypertext-driven

Richardson Maturity Model

https://martinfowler.com/articles/richardsonMaturityModel.html#level1

0 – exporting an API over HTTP with methods called with arguments
1 – Exporting resources instead of methods
2 – Proper use of HTTP verbs
3 – Exporting hypertext with objects that make all or part of the API discoverable.

