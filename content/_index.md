
+++

title = "Guide for writing markdown slides"
description = "A Hugo theme for creating Reveal.js presentations"
outputs = ["Reveal"]
aliases = [
    "/guide/"
]

+++

Traccia **#01**

# **Rilevazione** e **gestione** degli **errori** nel codice: <br>le **eccezioni**
#### P.F. 60 CFU · Abilitazione all'insegnamento - esame orale
c.d.c. B016 - Laboratorio di Scienze e Tecnologie Informatiche

<br>

{{% multicol %}}
{{% col %}}
<small><strong>Candidato</strong>: Nicholas Magi</small>
{{% /col %}}
{{% col %}}
<small><strong>Matricola</strong>: `0001253846` </small>
{{% /col %}}
{{% /multicol %}}

{{% pdf %}} 

---

## Contesto classe

- Classe: **terza**
- Scuola: **Istituto Tecnico**
  - Settore: **Tecnologico**
    - Indirizzo: **Informatica e Telecomunicazioni**
      - Articolazione: **Informatica**
- Disciplina: **Informatica**
- Alunni: **25**
  - di cui *due* **Bisogni Educativi Speciali (BES) con ADHD**

<br>
<br>

> Classe coesa e collaborativa, si riesce a lavorare in un clima disteso ma si rileva una bassa soglia dell'attenzione e frequente necessità di uscire dall'aula.

---

## Contestualizzazione nei <br> documenti ministeriali

<small>

Dal documento: 

**'ISTITUTI TECNICI - LINEE GUIDA PER IL PASSAGGIO AL NUOVO ORDINAMENTO - Secondo biennio e quinto anno - indirizzo "Informatica e Telecomunicazioni"'** 
<br>
allegato alla DIRETTIVA n. 4 del 16/01/2012, applicazione dell'articolo 8, comma 3, del d.P.R. 15 marzo 2010, n. 88. [1]

</small>

<br class="my-5">

{{% multicol class="gap-4" %}}
{{% col class="px-5 pb-5 border rounded-3" %}}
#### **Conoscenze**
- Linguaggi e macchine a vari livelli di astrazione.
{{% /col %}}
{{% col class="px-5 pb-5 border rounded-3" %}}
#### **Abilità**
- Scegliere il tipo di organizzazione dei dati più adatto a gestire le
informazioni in una situazione data.
{{% /col %}}
{{% /multicol %}}

---

```mermaid
timeline
    title COLLOCAZIONE DELLA LEZIONE / 1 - Programmazione di massima del terzo anno
    section MODULO 1 - Programmazione procedurale in Python (3/4 dell'anno - primo quadrimestre, pausa didattica, prima parte del secondo quadrimestre)
        UD1.0X ...
        UD1.06 Le funzioni
            : Introduzione
            : Scope delle variabili
            : Funzioni e procedure, tipi di return
            : ...
        UD1.07 Robustezza del software
            : Tipologie di errore (runtime, compilazione, logica), utilizzo di codici di errore e loro limitazioni
            : Rilevazione e gestione - il sistema delle eccezioni
            : Propagazione dell'errore e stacktrace
            : Attività su un caso reale
            : ...
    section MODULO 2 - Introduzione alla programmazione Web (1/4 dell'anno - seconda parte secondo quadrimestre, fino a fine anno)
        UD2.01 Introduzione HTML/CSS
            : ...
        UD2.0Y ...
```

---

```mermaid
timeline
    title COLLOCAZIONE DELLA LEZIONE / 1 - Programmazione di massima del terzo anno
    section MODULO 1 - Programmazione procedurale in Python (3/4 dell'anno - primo quadrimestre, pausa didattica, prima parte del secondo quadrimestre)
        UD1.01 Introduzione a Python
            : Algoritmo, programma e processo  
            : Livelli di astrazione 
            : Interpreti e compilatori 
            : Flusso di un programma
            : Configurazione IDE Thonny
            : ...
        UD1.02 Variabili, operazioni I/O 
            : Concetto di variabile, tipi di dato 
            : Sintassi dichiarazioni e assegnazione variabile, utilizzo nel codice 
            : Operatori base
            : Esempi di I/O, conversione dei dati
            : ...
        UD1.03 Controllo del flusso
            : Necessità di biforcazione del flusso, il costrutto selezione "if"
            : Varianti "if...else", "if...elif...else"
            : Necessità di ripetizione, iterazione determinata - casi d'uso del "for"
            : Iterazione indeterminata, casi d'uso del "while"
            : ...
        UD1.04 Liste monodimensionali
            : Necessità, esempi da Notional Machine
            : Iterazione e modifica di una lista
            : ...
        UD1.05 Algoritmi base
            : Algoritmi notevoli sulle liste (ricerca del min/max/media/target su liste numeriche, ordinamento di una lista...)
            : Cenni di complessità computazionale
            : ...
        UD1.06 Le funzioni
            : Introduzione
            : Scope delle variabili
            : Funzioni e procedure, tipi di return
            : ...
        UD1.07 Robustezza del software
            : Tipologie di errore (runtime, compilazione, logica), utilizzo di codici di errore e loro limitazioni
            : Rilevazione e gestione - il sistema delle eccezioni
            : Propagazione dell'errore e stacktrace
            : Attività su un caso reale
            : ...
    section MODULO 2 - Introduzione alla programmazione Web (1/4 dell'anno - seconda parte secondo quadrimestre, fino a fine anno)
        UD2.01 Introduzione HTML/CSS
            : ...
        UD2.02 Cenni di JavaScript
            : ...
```

---

## Collocazione della lezione / 2

{{% callout type="note" title="Big Ideas of Computer Science [2]" src="Tim Bell, University of Canterbury, NZ; Paul Tymann, Rochester Institute of Technology, New York, USA; Amiram Yehudai, Tel Aviv University, Israel" %}}

**#6 - Digital systems are designed by humans to serve human needs.**

<small>*+ possibile correlazione con*</small>

**#5 - Programs express algorithms and data in a form that can be implemented on a
computer.**

{{% /callout %}}

---

## Prerequisiti

- Sintassi del linguaggio di programmazione **Python**
- Concetto di algoritmo
  - saper implementare alcuni *algoritmi notevoli* (ricerca di min/max/elemento all'interno di una lista, determinare se un numero $n$ è primo...)
- Principali costrutti della programmazione strutturata:
  - costrutto selezione: `if`, `elif`, `else`;
  - costrutto iterazione: `for`, `while`;
- Concetto di **funzione**

---

## Obiettivi specifici di apprendimento in forma operativa

*Al termine dell'attività, lo studente è in grado di:*

<div class="d-flex flex-column gap-1">

<span class="border border-3 rounded-3 px-5 bg-warning-subtle">

#01) **Identificare**, dato un breve programma Python con costrutti dedicati alla rilevazione (`raise`) e quelli dedicati alla gestione (`try/except`) degli errori, tali costrutti e associare ciascun costrutto al rispettivo ruolo (funzione chiamata vs programma chiamante) in tutti i casi proposti.

</span>

<span class="border border-3 rounded-3 px-5 bg-danger-subtle">

#02) **Prevedere** l'output e il flusso di esecuzione di un breve programma Python che utilizza `raise` e `try/except` a fronte di input validi e non validi, indicando correttamente se l'eccezione viene intercettata o se provoca la terminazione del programma in almeno 3 casi di test su 4.

</span>

<span class="border border-3 rounded-3 px-5 bg-warning-subtle">

#03) **Usare** i costrutti `raise ValueError` e `try/except`, dato un breve programma Python guidato (con checklist operativa), per sostituirli ai controlli realizzati con `print` e valori sentinella in modo che il codice separi rilevazione e gestione e superi tutti i casi di test dati senza terminazioni anomale.

</span>

</div>


---

## Micro-planning dell'attività

La lezione si svolge in compresenza con il collega di classe A041.

| Fase 	| Docente 	| Studenti 	| Tempi 	|
|------	|---------	|----------	|-------	|
| 1.     	|         	|          	|       	|
| 2.     	|         	|          	|       	|
| 3.     	|         	|          	|       	|
| 4.     	|         	|          	|       	|

---

## Metodologie <br> didattiche

<br>

{{% multicol %}}
{{% col %}}
#### 1. Pair <br> Programming
{{% /col %}}
{{% col %}}
#### 2. Necessity Learning Design
{{% /col %}}
{{% col %}}
#### 3. Unplugged
{{% /col %}}
{{% /multicol %}}

---

## Valutazione formativa

{{% multicol %}}
{{% col %}}
#### Docenti

{{% /col %}}
{{% col %}}
#### Studenti

{{% /col %}}
{{% /multicol %}}

---

## Piano B: riadattamento dell'attività
Nel caso la valutazione formativa rilevasse **diffuse situazioni di fragilità**.

---

## Inclusione "by design"

{{% multicol %}}
{{% col %}}
#### Strategie

{{% /col %}}
{{% col %}}
#### Strumenti

{{% /col %}}
{{% /multicol %}}

---

## Risorse didattiche, attrezzature, spazi

---

## Bibliografia

---

## Micro-planning dell'attività

La lezione si svolge in compresenza con il collega di classe A041.

| Fase 	| Docente 	| Studenti 	| Tempi 	|
|------	|---------	|----------	|-------	|
| 1.     	|         	|          	|       	|
| 2.     	|         	|          	|       	|
| 3.     	|         	|          	|       	|
| 4.     	|         	|          	|       	|

---

{{< slide template="student" >}}

Istituto Tecnico Tecnologico "..." @ Cesena (FC)
# Gestione e rilevazione dell'errore in Python

{{% pdf %}}
<br>
<small>

A cura di Nicholas Magi - `nicholas.magi[at]...[dot]com`

</small>

---

{{< slide template="student" >}}
