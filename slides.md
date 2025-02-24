---
# You can also start simply with 'default'
theme: the-unnamed
themeConfig:
  color: "#F3EFF5"
  background: "#161C2C"

  code-background: "#0F131E"
  code-border: "#242d34"

  accents-teal: "#44FFD2"
  accents-purple: "#B39DDB"
  accents-red: "#FE4A49"
  accents-lightblue: "#15C2CB"
  accents-blue: "#5EADF2"
  accents-vulcan: "#0E131F"

  header-shadow: rgba(0, 0, 0, 0.15) 1.95px 1.95px 2.6px;

  default-headingBg: var(--slidev-theme-accents-purple)
  default-headingColor: var(--slidev-theme-accents-vulcan)
  default-background: var(--slidev-theme-background)
  default-font-size: 1.1em

  center-headingBg: var(--slidev-theme-accents-blue)
  center-headingColor: var(--slidev-theme-accents-vulcan)
  center-background: var(--slidev-theme-background)
  center-font-size: 1.1em

  cover-headingBg: var(--slidev-theme-accents-teal)
  cover-headingColor: var(--slidev-theme-accents-vulcan)
  cover-background: var(--slidev-theme-background)
  cover-font-size: 1.1em

  section-headingBg: var(--slidev-theme-accents-lightblue)
  section-headingColor: var(--slidev-theme-accents-vulcan)
  section-background: var(--slidev-theme-background)
  section-font-size: 1.1em

  aboutme-background: var(--slidev-theme-background)
  aboutme-color: var(--slidev-theme-color)
  aboutme-helloBg: var(--slidev-theme-accents-lightblue)
  aboutme-helloColor: var(--slidev-theme-background)
  aboutme-nameColor: var(--slidev-theme-accents-red)
  aboutme-font-size: 1.1em

  code-color: var(--slidev-theme-code-color)
  code-font-size: 1.1em
background: ./images/tanstack.webp
# some information about your slides (markdown enabled)
title: Tanstack Start - A Fresh Take on React
info: |
  ## Tanstack Start
  A Fresh Take on React - React IL meetup 02/2025
  [@talmosko](https://github.com/talmosko)

  Learn more at [Tanstack.com](https://tanstack.com)
# apply unocss classes to the current slide
class: m-5 w-full
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# TanStack Start: 
# A Fresh Take on React

Tal Moskovich <br/>
React IL 02/2025


<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
src: ./pages/aboutme.md
---

---
src: ./pages/meet-tanstack.md
---

---
src: ./pages/demo.md
---

---
src: ./pages/data-fetching.md
---

---
src: ./pages/thanks.md
---

