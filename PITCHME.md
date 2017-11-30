---?image=https://media.giphy.com/media/xTk9ZNSEaGv7FtKY6s/giphy.gif

<h1 style class="flash">Staticerization!</h1>

---

<h1 style="color: #000">SPA<span style="font-size: 60%">s</span> are awesome! But...</h1>

<span class="fragment">...some food for thought.</span>

<!-- 
<div style="position: relative">
<p style="position: absolute" class="fragment current-visible">persistent text<p>
<p style="position: absolute" class="fragment current-visible minimized-header">persistent text<p>
</div>
-->

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

<span class="code-presenting-annotation fragment current-only" data-code-focus="9">Where's the content, yo?</span>
<span class="code-presenting-annotation fragment current-only" data-code-focus="10">Right here</span>

+++

## This is a problem because...

+++

SEO

+++

Page load times and CRP

+++

Makes curl unhappy

+++

Machine readability and scraping

---

## Not all bad

+++

Fast UI updates

+++

Easy hosting

(e.g. Github Pages, Firebase, Netlify)

+++

No need to fuss with server-side crap

+++

Every user gets a private app instance.

Globals be damned!

+++

Blithely debug everything in the browser

---

## Possible Solutions?

<ul>
  <li class="fragment">Pre-rendering</li>
  <li class="fragment">Partial pre-rendering (SWA app shell)</li>
  <li class="fragment">Universal SSR (Server Side Rendering)</li>
  <li class="fragment">Non-universal SSR and fragment loading (e.g. Turbolinks, spfjs)</li>
  <li class="fragment">Reverse proxy SSR</li>
</ul>


---

## When Should You Should Give a Heck?

+++
SEO is crucial (reverse proxy SSR might be enough)
+++
Fast perceived load time provides demonstrable benefits 

(e.g. more conversions, less bounces, more revenue)
+++
Your audience is primarily viewing the app on mobile devices
+++
Bootstrapping requires many HTTP requests 

(thwarted by max connections per domain, total max connections)
+++
Concurrent users/requests volume is very high, putting strain on your servers and potentially costing more money
+++
At least some site UI and content does not change over time
+++
You use a SPA framework or stack supporting client side “rehydration”

(e.g. React, Vue, or Angular)

---

## When pre-rendering isn't the stupidest idea...

+++
Site content doesn’t change at all over time, or you can re-deploy whenever it does
+++
Fast perceived load time provides demonstrable benefits, but SSR proves to be too expensive 

(e.g. complexity, dev hours, maintenance hours)
+++
Composing UI components into a static html loading experience (Critical Rending Path)
+++
It's acceptable for at least some site content to remain static for a reasonable TTL
+++
Crawling the site would take less than a reasonable TTL
+++
The app uses a JAM (Javascript, APIs, Markup) stack

(better for simple static hosting)

---

## When SSR won't make you sob uncontrollably...

+++
Content updates very frequently
+++
Combinatorial possibilities of content are too many
+++
You’re building Twitter
+++
Almost never
+++
You live a blessed enough life that you get to use Nuxt

---

## What's there to cry about?

+++
HTTP requests need to convey information to the server that only a browser UA can 

(e.g. IP geolocation)
+++
Third-party embeds 

(e.g. social media, comment boards, ads)
+++
Crucial vendor library code only works client side
+++
Node is single-threaded

(all your globals and singletons are belong to us)
+++
Node hosting isn’t an option

---

## Welp. You done done it now.

<p class="fragment">Might as well also...</p>

+++
Segregate CRP code and assets from the full bundle
+++
Use code splitting
+++
Remove your blocking loading view, allowing earlier navigation
+++
Embed images as data urls
+++
Embed scripts
+++
Embedd styles
+++
Inline SVGs
+++
Asynchronously load CSS and fonts
+++
Use HTTP headers to promote long-term caching
+++
Use a caching layer in tandem with static html

- client storage
- service worker cache API
- reverse proxy cache (e.g. memcached)

---

<h2>Parting thought <br/>about pre-rendering</h2>

<p class="fragment">Use a pre-rendering service, like Prerender.io to simplify builds and deployments</p>

---

<h2>Parting thought <br/>about partial pre-rendering</h2>

<p class="fragment">Architect your app in a quasi-universal way, and leverage your dev server to generate static html as part of your build process</p>

---

<h2>Parting thought <br/>about web apps</h2>

<p class="fragment">They're hard @fa[frown-o]</p>