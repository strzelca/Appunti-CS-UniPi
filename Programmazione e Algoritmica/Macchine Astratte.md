---
title: Macchine Astratte
subject: Programmazione e Algoritmica
arguments: Architettura di Von Neumann, Ciclo Fetch-Decode-Execute, Identificatori, Ambiente, Memoria e Dichiarazioni
date: 25-09-2023
---

## Architettura di Von Neumann

Una **Macchina Astratta** è una astrazione di una generica architettura, in particolare descrive la **memoria**, il **controllo del flusso** e la **CPU**

Abbiamo quindi:
- La **CPU**
- I **BUS** che si dividono in *control*, *data*, *address* bus
- La **Memoria**

![[Von Neumann Arch.png]]

In una macchina le istruzioni vengono eseguite secondo il ciclo **fetch-(decode)-execute**, dove abbiamo quindi degli step:
- **fetch**: l'istruzione viene recuperata dalla memoria
- **decode**: una componente hardware chiamata *decoder* decodifica l'istruzione, quindi comprende il suo significato per la macchina
- **execute**: l'istruzione viene eseguita

### Memoria

La **memoria astratta** è un insieme di celle contigue caratterizzate da un **indirizzo** e da un **dato**

![[Abstract Memory.png]]

Sulla memoria possiamo eseguire due operazioni:
- Lettura *(read)*
- Scrittura *(write)*
In una cella di memoria può contenere:
- Nulla (la cella non contiene niente)
- Un valore *null* 
- Un valore numerico (questo può rappresentare un intero, un float, un carattere in formato ASCII, un altro indirizzo di memoria)

## Identificatori

Un **identificatore** è una sequenza di caratteri che contiene *lettere*, *cifre* e _ e che non inizia con una cifra, molti linguaggi sono *case sensitive*

I nomi devono essere **significativi**, usare quindi nomi che rappresentano il significato di ciò che contengono, non usare quindi $a = 3.14$, ma $\text{pi} = 3.14$

### Ambiente Formale

Un **ambiente** è una funzione che associa nomi mnemonici a locazioni di memoria
$$\text{ambiente } \rho : \text{Id} \to \text{Loc}$$
se quindi abbiamo una variabile $\text{pi}$ all'indirizzo $\text{0x1A2B}$, usando la funzione ambiente avremo che $\rho(\text{pi}) = \text{0x1A2B}$ 

### Memoria Formale

Analogamente, la **memoria** sarà una funzione che associa una locazione di memoria ad il valore associato
$$
\text{memoria } \sigma : \text{Loc} \to \text{Val}
$$
se quindi abbiamo che la variabile $\text{pi} = 3.14$ sempre all'indirizzo $\text{0x1A2B}$, possiamo usare la funzione memoria integrandola con la funzione ambiente $\rho$, avremo quindi che:
$$
\sigma(\rho(\text{pi})) = \sigma(\text{0X1A2B}) = 3.14
$$

se $\text{pi}$ invece fosse una costante, si può velocizzare l'accesso al valore evitando il ricorso alla funzione memoria usando una funzione ambiente
$$
\displaylines{
\text{ambiente } \rho : \text{Id} \to \text{Loc } \cup \text{ Val} \\
\rho(\text{pi}) = 3.14
}
$$

## Dichiarazioni

Le **Dichiarazioni** definiscono gli identificatori la prima volta che vengono introdotti venendo associati ad una memoria libera con un nuovo ambiente, ex. $\text{var } x = 4 \to \sigma(\text{new } \rho(x)) = 4$