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

## HTMX - Cos'è?

HTMX è una libreria che consente di accedere direttamente alle funzionalità moderne del browser da HTML, anziché utilizzare JavaScript.

Questo tipo di approccio è interessante per tutte i contesti in cui si vogliono scrivere siti dinamici, delegando molto della programmazione ad una corretta sintassi HTML.

HTMX consente di creare applicazioni web interattive senza dover ricaricare la pagina. Si basa sul concetto di "single-page application" (SPA), in cui l'intera applicazione viene caricata in una sola volta e le interazioni con l'utente vengono gestite tramite JavaScript. HTMX semplifica la creazione di SPA fornendo una serie di funzioni predefinite per la gestione di richieste HTTP, la modifica del DOM e l'animazione.

---

## HTMX - Esempio

Vediamo di come sia facile effettuare una chiamata HTTP/GET, utilizzando la coppia di attributi: **hx-get** e **hx-swap**

```html
<!DOCTYPE html>
<html lang="it">
<head>
    <title>HTMX Hello World</title>
    <script src="https://unpkg.com/htmx.org@1.9.5"></script>
</head>
<body>
    <!-- have a button GET a click via AJAX -->
    <button hx-get="/esercizi/01-helloworld-clickme.html" hx-swap="outerHTML">
        Cliccami
    </button>
</body>
</html>
```

---

## HTMX - installazione

HTMX si può installare utilizando una CDN

```html
<script src="https://unpkg.com/htmx.org@1.9.5" 
        integrity="sha384-xcuj3WpfgjlKF+FXhSQFQ0ZNr39ln+hwjN3npfM9VBnUskLolQAcN80McRIVOPuO" 
        crossorigin="anonymous"></script>
```

o semplicemente scaricandola o installandola con **NPM**

```bash
npm install htmx.org
```

---

## HTMX - Ajax

HTMX è un modo semplice per aggiungere comportamenti AJAX a un sito web.

AJAX è un acronimo per Asynchronous JavaScript and XML. AJAX è un modo per inviare e ricevere dati da un server senza dover ricaricare la pagina. È un modo per aggiornare dinamicamente le pagine web, utilizzato nelle applicazioni SPA.

HTMX permette di usate tutti i comandi HTTP e non solo le classiche GET e POST

---

## HTMX - Ajax - attributi

Di seguito gli attributi utilizzabili per effettuare delle chiamate HTTP

| Attributo | Descrizione |
|-----------|-------------|
| hx-get | Emette una richiesta GET all'URL specificato |
| hx-post | Emette una richiesta POST all'URL specificato |
| hx-put | Emette una richiesta PUT all'URL specificato |
| hx-patch| Emette una richiesta PATCH all'URL specificato |
| hx-delete | Emette una richiesta DELETE all'URL specificato |

---

## HTMX - Ajax - trigger

Le richieste AJAX vengono attivate dall'evento "naturale" di un elemento, per esempio

* **input**, **textarea** e **select** vengono attivati all'evento di **change**
* **form** vengono attivati al **submit**
* tutto il resto viene attivato al **click**

---

## HTMX - Ajax - cambio di trigger

È possibile cambiare il trigger di un elemento utilizzando l'attributo **hx-trigger**

```html
<button hx-get="/esercizi/01-helloworld-clickme.html" hx-trigger="mouseover">
    Cliccami
</button>
```

---

## HTMX - trigger modificatori

È possibile modificare il trigger di un elemento utilizzando i seguenti modificatori

| Modificatore | Descrizione |
|--------------|-------------|
| once | Emette la richiesta solo una volta |
| changed  | Emette la richiesta solo se il valore dell'elemento è cambiato |

---

## HTMX - trigger modificatori 2

| Modificatore | Descrizione |
|--------------|-------------|
| delay:&lt;intervallo di tempo&gt; | attendere l'intervallo di tempo (ad esempio 1s) prima di inviare la richiesta. Se l'evento si ripete, il conto alla rovescia viene azzerato |
| throttle:&lt;intervallo di tempo&gt; | attendere l'intervallo di tempo (ad esempio 1s) prima di inviare la richiesta. A differenza di delay, se un nuovo evento si verifica prima che il limite di tempo venga raggiunto, l'evento verrà scartato, quindi la richiesta verrà attivata alla fine del periodo di tempo|
| from:&lt;selettore CSS&gt; | ascolta l'evento su un elemento diverso. Ciò può essere utilizzato per cose come scorciatoie da tastiera.|

---

## HTMX - esempio di active search

Questi trigger permettono di implementare una serie di patter largamente utilizzati nella programmazione web, come l'active search

```html
<input type="text" 
       name="q" 
       hx-get="02-activesearch-get.html" 
       hx-trigger="keyup changed delay:500ms"
       hx-target="#risultato" 
       placeholder="Scrivi cosa cerchi ...">

<div id="risultato"> ** NULLA ** </div>
```

In questo caso si attendono 500 millisecondi prima di effettuare una chiamata in GET verso il server e passare il parametro q, visualizzando poi il risultato nel **DIV** con **ID** = **risultato**

---

## DA REVISIONARE ##

---

## HTMX - Trigger Filters

Multiple triggers can be specified in the hx-trigger attribute, separated by commas.

---

* Introduzione a HTMX
* Creazione di una SPA con HTMX
* Gestione delle richieste HTTP con HTMX
* Modifica del DOM con HTMX
* Animazione con HTMX
* Creazione di effetti di transizione con HTMX
* Creazione di modali con HTMX
* Creazione di menu a discesa con HTMX
* Creazione di applicazioni web dinamiche e interattive con HTMX

---

### Disclaimer

L'autore ha generato questo testo in parte con GPT-3, il modello di generazione del linguaggio su larga scala di OpenAI. Dopo aver generato la bozza della lingua, l'autore ha rivisto, modificato e rivisto la lingua a proprio piacimento e si assume la responsabilità  ultima del contenuto di questa pubblicazione.
