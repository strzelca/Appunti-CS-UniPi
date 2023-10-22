---
title: Grammatiche e Sintassi
subject: Programmazione e Algoritmica
arguments: Stringhe, Linguaggi di Programmazione, Grammatiche, Grammatiche Formali, Gerarchia di Chomsky, Sintassi Backus-Naur, Derivazione
date: 20-09-2022
---
# Stringhe

Caratteristiche delle stringhe:
- Lunghezza di una stringa $x$, denotato $|x|$
- Concatenazione due stringhe $x$ e $y$
- Esponenziale di una stringa x, definito da $x^{0} = \epsilon$ con $\epsilon = \{\emptyset\}$ quindi stringa vuota (diverso da $\emptyset$, che è l'insieme vuoto) e $x^{n}= x x^{n-1}$ 
- Prefisso di una stringa $x$ che si ottiene scartando uno o più simboli dalla coda
- Suffisso di una stringa $x$ che si ottiene scartando uno o più simboli dalla testa
- Sottostringa di una stringa $x$ che si ottiene scartando uno o più simboli da testa e coda
> $x$ = _"programmazione"_, $|x| = 14$
> Prefissi: programma, prog, ...
> Suffissi: grammazione, zione, ...
> Substring: gramma, gra, ... 

## Linguaggio di programmazione

Un **linguaggio** è un insieme di stringe formate a partire da un alfabeto

Linguaggi particolari:
- Linguaggio vuoto $\emptyset$
- Linguaggio costituito da stringa vuota $\{\epsilon\} = \{\emptyset\}$

### Chiusura di Kleene

La chiusura di Kleene $*$ di un insieme contiene tutte le stringhe di $n$ lunghezza che si possono formare concatenando i simboli di un alfabeto

> Se $A = {0,1}$
> $A^{*} = \epsilon, 0, 1, 00, 01, 10, 11, 000, ...$ 

La chiusura positiva di Kleene + di un insieme è come la chiusura di Kleene ma contiene tutte le stringe di lunghezza $n \geq 1$ 


### Linguaggio infinito

Un linguaggio infinito può essere definito in 3 modi:
- **Metodo Generativo** come le insieme delle stringhe generate da una grammatica
- **Metodo Riconoscitivo** come l'insieme delle stinge riconosciute da un automa
- **Metodo Algebrico** come l'insieme delle stringe soluzione di un sistema di equazioni algebriche

## Grammatiche

E' caratterizzata da:
- Frasi ben formate
- Produzioni ()

Prendiamo come esempio le espressioni aritmetiche con:
- $+,\times$
- $( )$
- $0,1,2,3,...,9$ 
Il linguaggio delle espressioni aritmetiche si può definire con la grammatica:
1. $(Exp, Num)$
2. $(Exp, (Exp))$
3. $(Exp, Exp + Exp)$
4. $(Exp, Exp \times Exp)$ 
5. $(Num, 0)$
6. $(Num, 1)$
7. $...$
8. $(Num, 9)$


## Grammatica Formale

Una **grammatica** è una quadrupla $G = \langle N,\Sigma,P,S \rangle$ con:
- $N \neq \emptyset$ è un insieme finito di *simboli non terminali*
- $\Sigma$ è un alfabeto di *simboli terminali*
- $P \subset (N \cup \Sigma)^{+} \times (N \cup \Sigma)^{*}$ è un insieme finito di produzioni
- $S \in N$ è il *simbolo distintivo* (o iniziale)
![[Quadrupla Grammatica.png]]

Convenzioni:
- $A, B, ... \in N$
- $a,b,... \in \Sigma$
- $\alpha, \beta, ... \in (N \cup \Sigma)^{*}$
- $x,y,... \in \Sigma^{*}$

Modi per denotare una produzione:
- $(\alpha, \beta), \alpha ::= \beta, \alpha \to \beta \in P$

Grammatica per le espressioni binarie:
- $\langle \{B\},\{0,1\},\{(B,0),(B,1),(B,0B),(B,1B)\},B \rangle$
  $0110 : B \to 0B \to 01B \to 011B \to 0100$

### Gerarchia di Хо́мський

- Grammatiche di tipo 0, $(\alpha, \beta), \alpha \in (N \cup \Sigma)^{+}, \beta \in (N \cup \Sigma)^{*}$
  *Macchina di Turing*
- Grammatiche dipendenti da contesto, $(\gamma A \delta, \gamma \sigma \delta), \gamma,\delta \in (N \cup \Sigma)^{*}, \sigma \in (N \cup \Sigma)^{+}$
  *Automi Lineari*
- Grammatiche libere da contesto, $(A,\beta),\beta \in (N \cup \Sigma)^{+}$
  *Automi a Pila*
- Grammatiche regolari o lineari destre, $(A,b),(A,bA)$
  *Automi a stati finiti*

I linguaggi di programmazione sono definiti *(fortunatamente direi)* dalle **grammatiche libere da contesto**

Le produzioni hanno quindi forma:
$$(A,\beta),\beta \in (N \cup \Sigma)^{+}$$
- Un solo simbolo non terminale nella parte sinistra
- Una stringa di lunghezza almeno 1 nella parte destra

### Sintassi Backus-Naur Form


$$\displaylines{
E ::= E + E | E - E | E * E | - E | (E) | I | V \\
V ::= x | y | z \\
I ::= 0 | 1 | 2 | ... | 9
}$$

La sintassi BNF rappresenta le grammatiche libere elencando solo le produzioni con le regole:
- Simbolo Iniziale
- Insieme dei simboli non terminali
- Simboli terminali
- Le produzioni sono elencate

Grammatica numeri binari in sintassi BNF
- $B ::= 0 | 1 | 0B | 1B$

### Linguaggi generati da grammatiche

- Stringa non vuota di caratteri terminali e non terminali $δ ∈ (Ν \cup Σ)^{+}$ 
- Stringa di caratteri terminali e non terminali $γ ∈ (Ν \cup Σ)^{*}$ 

> $δ$ **derivativo immediato** di $γ (γ \to δ)$ solo se δ *si può ottenere da* γ applicando una produzione della grammatica

> $δ$ **derivativo** di $γ (γ \to^{*} δ)$ se δ *si ottiene da* γ applicando un numero qualsiasi di produzioni

$L(G) = {w | w \in \Sigma^{*} \wedge S \to* w}$

> Il linguaggio generato da una grammatica G è l'insieme delle stringe di caratteri terminali che si possono ottenere applicando un qualsiasi numero di produzione a partire dal simbolo iniziale

<hr>
##### Esempio 1:

Verificare che $c+b*a$ appartiene al linguaggio $L(E)$ con grammatica $E ::= a | ... | z | E+E | E*E | (E)$

$E → E+E → c+E → c+E*E → c+b*E → c+b*a$

##### Esempio 2:

Verificare che `a*(b+c)` mediante le produzioni:

$$
\displaylines{
E ::= E+T | T \\
T ::= T*F | F \\
F ::= a | ... | z | (E)
}
$$

 $E → T → T*F → T*(E) → T*(E+T) → T*(E+F) → T*(E+c)$
 $→ T*(T+c) → T*(F+c) → T*(b+c) → F*(b+c) → a*(b+c)$

<hr>

#### Alberi di derivazione

Sono formati da:
- Nodi (i pallini)
- Archi (le frecce)

Definizione matematica di un albero $T = (N,A)$

> L'albero è un insieme di **Nodi** e **Alberi**

I nodi possono essere uscenti ed entranti
- Il nodo radice **non** ha archi entranti
- I nodi foglie **non** hanno archi uscenti

I figli dello stesso padre sono nodi fratelli

Proprietà: 
- La radice è simbolo iniziale
- Ogni nodo interno è non terminale
- Le foglie sono simboli terminali
- Ogni nodo interno rappresenta l'applicazione di una produzione