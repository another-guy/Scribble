# Morten Rand-Hendriksen: CSS Grid Changes Everything (About Web Layouts)

[📺 @ YouTube](https://www.youtube.com/watch?v=txZq7Laz7_4)

[🎞️ @ SlideShare](https://www.slideshare.net/mor10/css-grid-changes-everything-about-web-layouts-wordcamp-europe-2017)

[Building Production-Ready CSS Grid Layouts Today](https://www.smashingmagazine.com/2017/06/building-production-ready-css-grid-layout/)

## Terminology

* Grid **container** -- element containing a grid, defined by setting `display: grid;`.
* Grid **item** -- any *direct* descendant of a grid container.
* Grid **line** -- horizontal (row) or vertical (column) line separating the grid into sections. Numerated from `1` rather than `0`.
* Grid **cell** -- a cell inside the grid (intersection of single lines).
* Grid **area** -- a rectangular area between four specified grid lines; can cover one or more cells.
* Grid **track** -- the space between two or more adjacent grid lines.
* Grid **gap** -- the space between grid tracks (aka "gutters").

## In Nutshell

### 1. Define a grid.

```html
<div class="site">
</div>
```

```css
.site {
  display: grid;
}
```

### 1.1. Define rows and columns.

```css
.site {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  grid-template-rows: auto 1fr 3fr;
}
```

### 1.2. Subresult.

The grid items automatically populate frid from top left to bottom right based on HTML source order.

### 2. Apply rules to grid items.

```
<div class="site">
  <h1 class="header">My Header</h1>
  <h1 class="main-content">Main Content</h1>
  <h1 class="side-content">Side Content</h1>
</div>
```

```css
.header {
  grid-column: 1/4;
  grid-row: 1/2;
}
.main-content {
  grid-column: 1/3;
  grid-row: 2/4;
}
.side-content {
  grid-column: 3/4;
  grid-row: 2/4;
}
```

### BETTER ❗ 3.1. Define grid template areas.

```css
.site {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  grid-template-rows: auto 1fr 3fr;
  grid-template-areas:
    "header header header"
    "main main side"
    "main main side";
}
```

### BETTER ❗ 3.2. Specify what grid area the element is placed within.

```css
.header {
  grid-area: header;
}
.main-content {
  grid-area: main;
}
.side-content {
  grid-area: side;
}
```

### HACK? for IE `@supports`

Use `@support` feature query.

```css
@supports (display: grid) { ... }
```

...or better

```css
@supports (grid-area: auto) { ... }
```

### 4. CSS Grid: A Prcatical Approach for Today

1. Build accessible mobile-first layout without grid.
1. Use mobile-first layout as fallback for all browsers.
1. Use `@support` to detect grid support.
1. At the appropriate breakpoint, create layout with grid and grid-areas.
1. Explore new layouts as viewport widens.
