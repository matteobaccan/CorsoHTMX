---
theme: default
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
marp: true
footer: https://github.com/matteobaccan/CorsoHTMX
---

# Corso HTMX

Impariamo a usare HTMX

![bg right](img/matteo-baccan.jpg)

<!-- _paginate: false -->
<!-- _footer: "" -->

---

## Scopo del corso

Queste slide nascono dalla mia curiosità verso HTMX e dall'esperienza che ho accumulato nel corso degli anni.

La struttura base del corso ripercorre il tutorial presente sul sito [htmx.org](https://htmx.org/) arricchendoli con nuovi esempi ed una serie di slide in italiano.

---

## HTMX

HTMX è una libreria che consente di accedere direttamente alle funzionalità moderne del browser da HTML, anziché utilizzare JavaScript.

---

## HTMX - Esempio

```
<script src="https://unpkg.com/htmx.org@1.9.5"></script>
<!-- have a button POST a click via AJAX -->
<button hx-post="/clicked" hx-swap="outerHTML">
  Click Me
</button>
```

---

### Disclaimer

L'autore ha generato questo testo in parte con GPT-3, il modello di generazione del linguaggio su larga scala di OpenAI. Dopo aver generato la bozza della lingua, l'autore ha rivisto, modificato e rivisto la lingua a proprio piacimento e si assume la responsabilità  ultima del contenuto di questa pubblicazione.
