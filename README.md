# 🧩 ScrollFX.css  
**Lightweight, class-based scroll-animation micro-framework using native CSS View Timelines**

ScrollFX.css lets you build scroll-linked animations (fade, slide, fly-in, scale, rotate, blur, parallax, stagger, pin, spin, …) **without JavaScript**.  
It uses modern CSS features such as `view-timeline` and `animation-timeline`, so all effects play smoothly forward when you scroll down and reverse automatically when you scroll back up.

---

## ✨ Features

- ✅ **Pure CSS** (no JS dependency)
- 🔄 **Reversible on scroll direction**
- 🎞️ **Adjustable start / end / easing / strength**
- 🪶 **Fly-in, fade, slide, blur, rotate, scale**
- 🌫️ **Parallax & pinned sections**
- 🎚️ **Staggered reveal via container timeline**
- 🧩 **Composable utility classes**
- 🧠 **Accessibility aware** (`prefers-reduced-motion` support)

---

## 🚀 Quick Start

### 1️⃣ Add the framework
```html
<link rel="stylesheet" href="scrollfx.css">
````

or copy the `<style>` block from `scrollfx.css` into your project.

### 2️⃣ Use the classes

```html
<section class="sfx sfx-up">Slide up as you scroll</section>
<section class="sfx sfx-fade">Fade in on view</section>
<section class="sfx sfx-fly-left">Fly in from right edge</section>
<section class="sfx sfx-parallax">Parallax motion</section>
```

---

## ⚙️ Configuration Variables

All animations are controlled by **CSS custom properties**.
You can override these per element via `style` or utility classes.

| Variable         | Description                              | Example                                       |
| ---------------- | ---------------------------------------- | --------------------------------------------- |
| `--sfx-start`    | Scroll progress where animation starts   | `10%`                                         |
| `--sfx-end`      | Scroll progress where animation ends     | `80%`                                         |
| `--sfx-ease`     | Animation timing function                | `ease`, `ease-out`, `cubic-bezier(.3,0,.7,1)` |
| `--sfx-distance` | Travel distance for slides               | `32px`                                        |
| `--sfx-scale`    | Start scale factor                       | `.85`                                         |
| `--sfx-rotate`   | Start rotation                           | `8deg`                                        |
| `--sfx-blur`     | Start blur                               | `10px`                                        |
| `--sfx-parallax` | Parallax travel distance                 | `25vh`                                        |
| `--sfx-duration` | Logical animation duration (for stagger) | `1s`                                          |
| `--sfx-step`     | Delay between staggered children         | `120ms`                                       |

---

## 🎬 Available Classes

| Class                              | Effect                                |
| ---------------------------------- | ------------------------------------- |
| `.sfx-fade`                        | Fade in/out                           |
| `.sfx-up` / `.sfx-down`            | Slide vertically                      |
| `.sfx-left` / `.sfx-right`         | Slide horizontally                    |
| `.sfx-fly-left` / `.sfx-fly-right` | Fly in from screen edge               |
| `.sfx-scale`                       | Scale up                              |
| `.sfx-rotate`                      | Rotate to rest                        |
| `.sfx-blur`                        | Deblur effect                         |
| `.sfx-parallax`                    | Slow parallax translation             |
| `.sfx-spin`                        | Rotate continuously with scroll       |
| `.sfx-pin`                         | Sticky element (like pinned headline) |

---

## 🪄 Staggered Animations (Container Timeline)

Wrap multiple items in a timeline container:

```html
<div class="sfx-timeline" style="--sfx-step: 120ms; --sfx-duration: 1s;">
  <div class="sfx-child sfx sfx-up">Item 1</div>
  <div class="sfx-child sfx sfx-up">Item 2</div>
  <div class="sfx-child sfx sfx-up">Item 3</div>
</div>
```

Each child will animate sequentially as you scroll —
and reverse order when scrolling back up.

---

## 🖼️ Parallax Example

```html
<header class="sfx sfx-parallax" style="--sfx-parallax: 30vh">
  <h1 class="sfx sfx-fade">Parallax Hero</h1>
</header>
```

---

## 📌 Pinning Example

```html
<section class="pin-wrap">
  <h2 class="sfx-pin" style="--sfx-pin-top: 1rem">Pinned Title</h2>
  <div style="height:150vh"></div>
</section>
```

---

## 🧩 Debugging

Enable outlines for all scroll-animated elements:

```js
document.body.classList.toggle('sfx-debug')
```

Or use the provided button in the demo (`Toggle debug`).

---

## 🌐 Browser Support

* Chromium 115+
* Safari 17+
* Firefox (behind `layout.css.scroll-driven-animations.enabled` flag)
* Graceful fallback: elements stay visible with no animation

---

## 🧱 Folder Structure Example

```
project/
├─ css/
│  ├─ scrollfx.css   ← framework
│  └─ demo.css       ← demo styling
├─ index.html        ← demo / docs page
└─ README.md         ← this file
```

---

## 🧠 Notes

* ScrollFX.css uses the native **View Timeline API** (`view-timeline` / `animation-timeline`).
* Effects play both forward and backward automatically — no JS listeners.
* Combine classes freely, e.g.:

  ```html
  <div class="sfx sfx-up sfx-rotate"></div>
  ```

---

## 📜 License

MIT © ulrischa
Created with ❤️ using native CSS scroll animations.

---

## 🔗 Demo

👉 [Live Demo (CodePen)](https://codepen.io/ulrischa/pen/WbrprPL)
