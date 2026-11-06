---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: HTML - The Foundation of the Web
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable Comark Syntax: https://comark.dev/syntax/markdown
comark: true
# duration of the presentation
duration: 35min
hideInToc: true
---

# HTML: The Foundation of the Web

<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Press Space for next page <carbon:arrow-right />
</div>

<div class="abs-br m-6 text-xl">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="slidev-icon-btn">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
hideInToc: true
---

# Table of contents

<Toc maxDepth="1" />

---

# What is HTML?

Fully known as HyperText Markup Language, it's a markup language(not a programming language), which serves as the skeleton/foundation of the web. It's upon it and in it that other languages of the web are built.

<v-clicks>

# Brief History

**1989 to 1991:** HTML was developed by Tim Berners-Lee, who was working at CERN when he proposed a system for sharing documents between researchers. He created the first web broswer, the first web server, and the first description of HTML(which was about 18 tags).

**1993:** The Mosaic browser makes the web popular by supporting images online.

**1995:** HTML 2.0 was published as the first official standard(IETF).

**1997:** HTML 3.2 and then HTML 4.0 arrive under the W3C, adding tables, forms, and the push to seperate structure (HTML) from style (CSS).

**2008 to 2014:** HTML5 is developed, adding semantic elements, native audio and video, canvas, and better forms. It becomes W3C Recommendation in 2014.

</v-clicks>

---
transition: slide-up
---

**2019 till now:** The W3C and WHATWG agree that the WHATWG's HTML Living Standard is the single official specification. There are no more numbered versions;HTML now evolves continuously. This is why newer features like <code>dialog</code> and <code> popover</code> keep arrriving.

---
transition: slide-up
layout: two-cols
title: Anatomy of an HTML Document
---

# Anatomy of an HTML document

- `<!DOCTYPE html>`: tells the browser to use modern HTML rules. It isn't a tag, and it must be the first line.
- `<html>`: the root element that wraps the whole page. Add `lang="en"` to help screen readers and search engines.
- `<head>`: information _about_ the page that isn't displayed, such as the title, character encoding, and links to CSS or JavaScript.
- `<body>`: everything the user actually sees, such as headings, text, images, links, and forms.

::right::

```html {1|2,12|3-7|8-11|all}
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>My First Page</title>
  </head>
  <body>
    <h1>Hello, web!</h1>
    <p>This is my first page.</p>
  </body>
</html>
```

---

title: Elements, Tags, and Attributes
---

# Elements, Tags, and Attributes

HTML is built from **elements**.

```html {1|2|3|all}
<p>HTML is the skeleton of the web.</p>
```

<v-clicks>

- **Opening tag**: `<p>` marks where the element starts
- **Content**: the text or other elements inside
- **Closing tag**: `</p>` marks where it ends (note the `/`)
- **Element** = opening tag + content + closing tag

</v-clicks>
---
hideInToc: true
---

# Elements Without Closing Tags

Some elements have no content, so they have **no closing tag**. These are called _void elements_.

```html
<img src="cat.jpg" alt="A sleeping cat" />
<br />
<hr />
<input type="text" />
```

<v-clicks>

- `<img>`: an image
- `<br>`: a line break
- `<hr>`: a horizontal line
- `<input>`: a form field

</v-clicks>
---
layout: two-cols
hideInToc: true
---

# Nesting

Elements go **inside** other elements. The inner one must close **before** the outer one.

<v-clicks>

- The `<ul>` is the **parent**
- The `<li>` elements are its **children**
- Indentation shows the structure

</v-clicks>

::right::

### Correct ✅

```html
<ul>
  <li>
    <strong>HTML</strong>
  </li>
</ul>
```

### Incorrect ❌

```html
<p>
  <strong>Hello
</p>
</strong>
```

---
hideInToc: true
---

# Attributes

Attributes give an element **extra information**. They go in the **opening tag** as `name="value"`.

```html {1|1,2|all}
<a href="https://developer.mozilla.org" class="link"> Visit MDN </a>
```

<v-clicks>

- **Name**: what you are setting (`href`, `class`)
- **Value**: always in quotes (`"https://..."`)
- Several attributes are separated by spaces
- They never go in the closing tag

</v-clicks>

---

hideInToc: true
---

# Key Attributes

<v-clicks>

- **`href`**: the destination of a link. `<a href="about.html">`
- **`src`**: the source file of an image, video, or script. `<img src="logo.png">`
- **`alt`**: a text description of an image, for accessibility and broken images
- **`class`**: a reusable label so many elements can share the same style
- **`id`**: a unique name for **one** element on the page

</v-clicks>

---
hideInToc: true
---

# `class` vs. `id`

```html
<p class="note">First note</p>
<p class="note">Second note</p>

<h2 id="contact">Contact Us</h2>
```

<v-clicks>

- **`class`** can be reused on many elements
- **`id`** must be **unique** on the page
- Jump to an `id` with a link: `<a href="#contact">Contact</a>`

</v-clicks>

---

title: Common Elements
layout: two-cols
---

# Common Elements: Text

<v-clicks>

- **Headings**: `<h1>` to `<h6>`, one `<h1>` per page, in order
- **Paragraphs**: `<p>` for blocks of text
- **Lists**: `<ul>` bullets, `<ol>` numbers, `<li>` for each item

</v-clicks>

::right::

```html
<h1>Web Basics</h1>
<p>HTML structures a page.</p>

<ul>
  <li>HTML</li>
  <li>CSS</li>
</ul>

<ol>
  <li>Write</li>
  <li>Save</li>
</ol>
```

---
hideInToc: true
layout: two-cols
---

# Common Elements: Content

<v-clicks>

- **Links**: `<a href>` points to a page, file, or `#id`
- **Images**: `<img src alt>`, a void element, and `alt` is required
- **Tables**: `<table>`, `<tr>` rows, `<th>` headers, `<td>` data cells. Use for data, not layout

</v-clicks>

::right::

```html
<a href="about.html">About</a>

<img src="cat.jpg" alt="A cat" />

<table>
  <tr>
    <th>Version</th>
    <th>Year</th>
  </tr>
  <tr>
    <td>HTML5</td>
    <td>2014</td>
  </tr>
</table>
```

---
title: Semantic HTML
layout: two-cols
---

# Semantic HTML

Elements whose **name describes their meaning**, not just their looks.

<v-clicks>

- `<div>` and `<span>` say **nothing** about their content
- `<nav>`, `<main>`, `<footer>` say **what the content is**
- Browsers, screen readers, and search engines can all read that meaning

</v-clicks>

::right::

### Non-semantic ❌

```html
<div class="header">
  <div class="menu">...</div>
</div>
<div class="content">...</div>
<div class="footer">...</div>
```

### Semantic ✅

```html
<header>
  <nav>...</nav>
</header>
<main>...</main>
<footer>...</footer>
```

<!--
Both look the same once CSS is applied. The difference is in the accessibility.
-->

---
hideInToc: true
layout: two-cols
---

# Page Structure Elements

<v-clicks>

- **`<header>`**: introductory content, such as a logo, title, or intro
- **`<nav>`**: a block of main navigation links
- **`<main>`**: the central content of the page. Use it **once** per page
- **`<article>`**: self-contained content that makes sense on its own, such as a blog post or news story
- **`<footer>`**: closing content, such as copyright, contacts, or links

</v-clicks>

::right::

```html {1|2-4|5-10|11|all}
<body>
  <header>
    <h1>My Blog</h1>
  </header>
  <nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
  </nav>
  <main>
    <article>
      <h2>Why HTML matters</h2>
      <p>Post content...</p>
    </article>
  </main>
  <footer>
    <p>&copy; 2026 My Blog</p>
  </footer>
</body>
```

<!--
Header and footer can also be used inside an article or section, not only for the whole page.
-->

---
hideInToc: true
layout: two-cols
---

# Why Semantics Matter

### Accessibility

<v-clicks>

- Screen readers treat `<nav>`, `<main>`, `<header>`, and `<footer>` as **landmarks**
- Users can **jump** straight to the main content or the menu
- Keyboard and assistive tools get a clear structure

</v-clicks>

::right::

### SEO

<v-clicks>

- Search engines can tell the **main content** from menus and footers
- Clear structure helps them understand and index the page
- Good structure supports, but doesn't guarantee, better ranking

</v-clicks>

### Also

<v-clicks>

- Code is **easier to read and maintain**
- Less need for extra `class` names
- Works well when styles fail to load

</v-clicks>

---
title: Forms and Input
---

# Forms and Input

Forms are how users **send data** to a website.

<v-clicks>

- Logging in, signing up, searching, checkout, contact pages
- The main way a web page **receives** information, not just displays it
- Built with four core elements:
  - `<form>`: the container that sends the data
  - `<input>`: a field the user fills in
  - `<label>`: the text that describes a field
  - `<button>`: submits the form

</v-clicks>

<!--
Without forms, the web would be read-only.
-->

---
hideInToc: true
layout: two-cols
---

# A Simple Form

<v-clicks>

- **`<form>`**: `action` is where the data goes, `method` is how (`get` or `post`)
- **`<label>`**: describes the field, linked by `for` and `id`
- **`<input>`**: `type` decides what kind of field it is, and `name` is the key sent with the data
- **`<button>`**: `type="submit"` sends the form

</v-clicks>

::right::

```html {1,9|2-3|4-5|7-8|all}
<form action="/signup" method="post">
  <label for="email">Email</label>
  <input type="email" id="email" name="email" required />

  <label for="pw">Password</label>
  <input type="password" id="pw" name="password" minlength="8" required />

  <button type="submit">Sign up</button>
</form>
```

---
title: Details and Summary
layout: two-cols
---

# `<details>` and `<summary>`

A **native collapsible section**, with no JavaScript.

<v-clicks>

- **`<details>`**: the container that opens and closes
- **`<summary>`**: the always-visible label the user clicks
- Everything else inside `<details>` is **hidden until opened**
- `<summary>` should be the **first child** of `<details>`

</v-clicks>

::right::

```html
<details>
  <summary>What is HTML?</summary>
  <p>HTML is the language that structures web pages.</p>
</details>
```

<details>
  <summary>What is HTML? </summary>
  <p>HTML is the language that structures web pages.</p>
</details>

---
hideInToc: true
layout: two-cols
---

# The `open` Attribute

<v-clicks>

- By default, `<details>` starts **closed**
- Add `open` to start it **expanded**
- `open` is a **boolean attribute**: present means true, no value needed
- The browser adds and removes it automatically as the user toggles
- You can read it in JavaScript with `element.open`

</v-clicks>

::right::

```html
<!-- Closed by default -->
<details>
  <summary>FAQ 1</summary>
  <p>Hidden at first.</p>
</details>

<!-- Open by default -->
<details open>
  <summary>FAQ 2</summary>
  <p>Visible at first.</p>
</details>
```

---
hideInToc: true
layout: two-cols
---

# Building an Accordion

An **accordion** is a group of collapsible sections.

<v-clicks>

- Put several `<details>` one after another
- Give them the **same `name`** so only **one stays open** at a time
- Opening one automatically closes the others
- `name` is supported in current versions of the major browsers. In an older browser, they simply work as independent sections

</v-clicks>

::right::

```html
<details name="faq" open>
  <summary>What is HTML?</summary>
  <p>The structure of a web page.</p>
</details>

<details name="faq">
  <summary>What is CSS?</summary>
  <p>The style of a web page.</p>
</details>

<details name="faq">
  <summary>What is JavaScript?</summary>
  <p>The behavior of a web page.</p>
</details>
```

<!--
Without the name attribute, each details toggles independently. That is also useful.
-->

---
hideInToc: true
---

# Why Use `<details>`?

<v-clicks>

- **No JavaScript**: less code and less to break
- **Accessible by default**: keyboard (Tab, Enter, Space) and screen readers work out of the box
- **Great for**: FAQs, long notes, optional help text, "show more" content
- **Avoid for**: content users must see, or critical navigation

</v-clicks>

---
title: The Dialog Element
layout: two-cols
---

# `<dialog>`

A native **pop-up window** built into HTML.

<v-clicks>

- A **modal** dialog blocks the rest of the page until the user responds.
- The browser handles the **backdrop**, the **Esc key**, and **focus** for you.
- It appears in the **top layer**, so no `z-index` battles.
- Great for confirmations, alerts, and small forms.

</v-clicks>


::right::


```html
<button id="open">Open dialog</button>

<dialog id="myDialog">
  <h2> Delete this file? </h2>
  <p>This cannot be undone </p>
  <button id="close"> Close</button>
  </dialog>
  ```


<button class="demo-btn" @click="$event.target.nextElementSibling.showModal()">
Open dialog
</button>
<dialog class="demo-dialog">
<h2>Delete this file?</h2>
<p>This cannot be undone</p>
<button class="demo-btn" @click="$event.target.closest('dialog').close()">
Close
</button>
</dialog>


---
title:The Popover Attribute
---

# Popover

A **lightweight overlay**, with **no JavaScript** needed.

<v-clicks>

- Add the **`popover`** attribute to any element to make it a popover.
- It's **hidden** until triggered.
- Add **`popovertarget="id"`** to a `<button>` to toggle it.
- Appears in the **top layer**, like a dialog
- But unlike a modal dialog, the page behind **stays usable**

</v-clicks>




<style>
  .demo-btn{
    padding:0.4rem 1rem;
    border:1px solid black;
    border-radius:8px;
    cursor:pointer;
  }
  .demo-dialog{
    border:none;
    border-radius:12px;
    padding:1.5rem;
    background:white;
    color:#222;
  }
  .demo-dialog::backdrop{
    background:rgba(0 0 0 0.6)

  }
  </style>

  