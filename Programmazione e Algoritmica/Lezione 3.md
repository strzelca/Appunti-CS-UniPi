### Classificazione delle grammatiche
**Gerarchia di Chomsky**: basata sulla forma delle produzione
* _Grammatiche di tipo 0_ - `(α,β),α ∈ (Ν ∪ Σ)+, β ∈ (Ν ∪ Σ)*` 
	> **Macchina di Turing**
* _Grammatiche dipendenti dal contesto_ - `(γΑδ,γσδ),γ,δ ∈ (Ν ∪ Σ)+, σ ∈ (Ν ∪ Σ)*` 
	> **Automi Lineari**
* _Grammatiche libere da contesto - `(Α,β), β ∈ (Ν ∪ Σ)+` 
	> **Automi a Pila**
* _Grammatiche lineari_ - `(A,b),(A,bA)`
	> **Automi a stati finiti**

<hr>

**I linguaggi di programmazione sono definiti da grammatiche libere da contesto**
#### `(Α,β), β ∈ (Ν ∪ Σ)+`

###### Chiusura di Kleene
- `*`  - contiene tutte le stringhe di lunghezza 0,1,2,3,... che si possono formare concatenando simboli di un alfabeto, quindi contenente anche la stringa vuota `ε`
- `+` - contiene tutte le stringe di lunghezza maggiore o uguale a 1, escludendo quindi la stringa vuota `ε`, si chiama **chiusura positiva**

```
Ν = {A, B}
Σ = {a, b} 

(Ν ∪ Σ)+ senza ε
(Ν ∪ Σ)* con ε
```

### Sintassi Backus-Naur Form

```
E ::= E + E | E - E | E * E | - E | (E) | I | V
V ::= x | y | z
I ::= 0 | 1 | 2 | ... | 9
```

La sintassi BNF rappresenta le grammatiche libere elencando solo le produzioni con le regole:
- Simbolo Iniziale
- Insieme dei simboli non terminali
- Simboli terminali
- Le produzioni sono elencate

Grammatica numeri binari in sintassi BNF

```

B ::= 0 | 1 | 0B | 01
```

### Linguaggi generati da grammatiche

`δ ∈ (Ν ∪ Σ)+` - Stringa non vuota di caratteri terminali e non terminali
`γ ∈ (Ν ∪ Σ)*` - Stringa di caratteri terminali e non terminali

> δ **derivativo immediato** di γ (γ → δ) solo se δ *si può ottenere da* γ applicando una produzione della grammatica

> δ **derivativo** di γ (γ →* δ) se δ *si ottiene da* γ applicando un numero qualsiasi di produzioni

L(G) = {w | w ∈ Σ* ∧ S →* w}

- S : Simbolo Iniziale

> Il linguaggio generato da una grammatica G è l'insieme delle stringe di caratteri terminali che si possono ottenere applicando un qualsiasi numero di produzione a partire dal simbolo iniziale

<hr>
##### Esempio 1:

Verificare che `c+b*a` appartiene al linguaggio L(E) con grammatica `E ::= a | ... | z | E+E | E*E | (E)`
###### `E → E+E → c+E → c+E*E → c+b*E → c+b*a `

##### Esempio 2:

Verificare che `a*(b+c)` mediante le produzioni:

```
E ::= E+T | T
T ::= T*F | F
F ::= a | ... | z | (E)
```

###### `E → T → T*F → T*(E) → T*(E+T) → T*(E+F) → T*(E+c) → T*(T+c) → T*(F+c) → T*(b+c) → F*(b+c) → a*(b+c)`

<hr>

#### Alberi di derivazione

Sono formati da:
- Nodi (i pallini)
- Archi (le frecce)

Definizione matematica di un albero `T = (N,A)`

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