---
title: Lezione 2
subject: Sistemi Operativi
date: 22-09-2022
arguments: Modularità, Rappresentazione Binaria Modulo-Segno e Complemento a Due
---

# Modularità

Per indirizzare una memoria di *1GB* sono necessari `30bit` e verrà restituito un valore di 8bit, per indirizzare *2GB* (1GB + 1GB moduli) sono necessari `31bit`, 30bit per l'indirizzamento e 1bit (bit più significativo) per informare un **Multiplexer** a quale memoria vogliamo accedere.


# Rappresentazione di numeri binari relativi

1. Rappresentazione Modulo e Segno
	Il MSB indica il segno, il restante indica il modulo
	**Esempio** `n = 4bit`
	```
	0000 = 0
	0001 = 1
	0010 = 2
	0011 = 3
	0100 = 4
	0101 = 5
	0110 = 6
	0111 = 7
	---------
	1000 = 0
	1001 = -1
	1010 = -2
	1011 = -3
	1100 = -4
	1101 = -5
	1110 = -6
	1111 = -7
	+---+---+---+---+
	| S |  Va. Ass. |
	+---+---+---+---+
	```
	**Problemi**:
	- Lo 0 è ripetuto due volte
	- Si usa un bit per il segno, quindi si può rappresentare max $[-2^{n-1}+1, 2^{n-1}-1]$

2. Complemento a 2
	**Esempio** `7 = 0111`
	`0111 -> 1000 + 1 -> 1001 = -7`
	**Somma**
	```
	5 + (-7) = - 2
	0101 +
	1001 =
	1110
	-
	2 = 0010 -> 1101 + 1 -> 1110 = -2
	```
	**Vantaggi**:
	- A differenza del sistema a Modulo e Segno possiamo rappresentare un numero negativo in più $[-2^{n-1}, 2^{n-1}-1]$
