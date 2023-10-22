---
title: Linguaggio L
subject: Programmazione e Algoritmica
arguments: Linguaggio L, Tipi, Operatorio, Ambiente Statico
date: 27-09-2023
---

# Tipi

I tipi del linguaggio L sono:
- Int $n \in \mathbb{Z}$
- Double $d \in \mathbb{R}$
- Bool $b \in \{\text{true, false}\}$
- String $s \text{ | } S ::= A|B|...|Z|a|b|...|z|AS|BS|...|ZS|aS|bS|...|zS|(S)$

# Operatori
- Binari $+,-,*,/$
- Binari Relazionali $<,>,=$
- Binari Logici $\text{AND, OR, NOT oppure }\&\&,||,!$

# Ambiente Statico

L'ambiente statico $\Delta$ si usa per analizzare **staticamente** il programma, valutandone i tipi e verificandone la **coerenza**. Si differenzia con l'ambiente $\rho$ per il fatto che quest'ultimo è *dinamico* e quindi simula l'esecuzione.

Per definire $\Delta$ partiamo dal vedere che tipo di valori possiamo avere: **costanti** e **variabili**.
$$
\text{ambiente statico } \Delta : \text{Id} \cup \text{Val} \to \text{T} \cup \text{TLoc}
$$
Associa un tipo $\text{T}$ o $\text{TLoc}$ ad ogni valore o identificatore che compare nel programma, $\text{TLoc} = \{\text{IntLoc, DoubleLoc, BoolLoc, StringLoc}\}$ rappresenta una locazione di memoria in cui possiamo **leggere** e **scrivere** un valore di tipo $\text{T}$

```kotlin
const costante:Int = 2;
costante = costante + 1;
```

abbiamo quindi che $\Delta = \{(\text{Int}, 2); (\text{costante},\text{Int})\}$, e non essendo il tipo di *costante* seguito dalla keyword **Loc** allora non è una variabile e non può essere riassegnata.

se invece avessimo il codice
```kotlin
var prezzoDiesel:Int = 2;
var litri:Double = 0.5;
var rifornimento = prezzoDiesel * litri;
```

avremo un ambiente $\Delta = \{\text{(Int,2);(Double,0.5);(prezzoDiesel,IntLoc);(litri,DoubleLoc)}\}$, e che quindi rifornimento non sarà una variabile valida, siccome operazione tra tipi differenti.