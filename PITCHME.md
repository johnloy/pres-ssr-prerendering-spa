# SPAs are awesome! But...

<span class="fragment">...some food for thought.</span>

---

## This is a problem (maybe)

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Dynamic SPA. Hot Shit!</title>
    <link rel="stylesheet" href="/css/style.css">
  </head>
  <body>
    <div id="app"></div>
    <script src="/js/bundle.js"></script>
  </body>
</html>
```

@[9](Where's the content, yo?) 
@[10](Right here)

+++?video=http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4
<!-- .slide: id="slide2def" data-transition="concave" data-background="#A7C66B" -->

## This is a problem because...

SEO

+++

## This is a problem because...

Page load times and CRP

+++

## This is a problem because...

Makes curl unhappy

+++

## This is a problem because...

Machine readability and scraping

---

## Not all bad

+++

Easy hosting

+++


<div style="text-align: center">
<p>Every user gets a private app instance.</p>
<p>Globals be damned!</p>
</div>

---

<h1 style="position:fixed">Possible Solutions?</h1>

---

<h1 style="position:fixed">Possible Solutions?</h1>

## Pre-rendering