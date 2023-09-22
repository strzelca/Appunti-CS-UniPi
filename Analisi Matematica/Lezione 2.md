#### Funzioni Monotone


> $A,B \subseteq \mathbb{R}, f : A \to B$ , con $x_1, x_2 \in A$ e $x_1 < x_2$
> 
> se $\forall x_1,x_2$ come sopra succede:


###### Strettamente Crescente
- $f(x_1) < f(x_2)$
###### Debolmente Crescente
- $f(x_1) \leq f(x_2)$
###### Strettamente Decrescente
- $f(x_1) > f(x_2)$
###### Debolmente Decrescente
- $f(x_1) \geq f(x_2)$

> _f_ è strettamente crescente solo se il rapporto incrementale $$\frac{f(x_2) - f(x_1)}{x_2 - x_1}$$ è sempre una quantità positiva, (cioè $f(x_2) - f(x_1)$ e  $x_2 - x_1$ hanno lo stesso segno) e $f$ è strettamente decrescente quando il rapporto incrementale è sempre negativo.


> se $f$ è strettamente crescente, allora è anche debolmente crescente, il viceversa **non** è vero.


<hr>

###### Esempio

$$f(x) = \frac{1}{x}, f : \mathbb{R} \setminus\{0\} \to \mathbb{R} \setminus\{0\}$$

![[Funzione Potenza Negativa.png]]

La funzione $f(x) = \frac{1}{x}$ **non** è decrescente su tutto il dominio, è però decrescente su $(-\infty, 0)$ e su $(0, +\infty)$ separatamente.

<hr>
##### Composizione di funzioni monotone

$$
A,B,C \subseteq \mathbb{R}, f : A \to B, g : B \to C
$$
$$
g•f : A \to C, (g•f)(a) = g(f(a))
$$

Allora
1. se *f* e *g* sono (strettamente o debolmente) crescenti, allora *g*•*f* è pure (strettamente o debolmente) crescente
2. se *f* è crescente e g è decrescente (o viceversa), allora *g•f* è decrescente.
   ($x_1 < x_2 \to f(x_1) < f(x_2) \to g(f(x_1)) > g(f(x_2))$) 
3. se *f* e *g* sono decrescenti, allora g•f è crescente

<hr>

###### Esempio di composizione di funzioni

$h(x) = (e^x)^3$

è composizione di:
- $f(x) = x^3$
- $g(t) = e^t$
- $h(x) = g(f(x))$

Visto che *f* e *g* sono strettamente crescenti, segue che anche h è strettamente crescente

> se *f* è strettamente monotona, allora è iniettiva
> (se $x_1 \neq x_2$ e diciamo che $x_1 < x_2$, e diciamo *f* crescente, allora $f(x_2) < f(x_2)$, e segue che $f(x_1) \neq f(x_2)$)


> **Attenzione** : non è vero che una funzione iniettiva è monotona

###### Esempio

$$f(x) = \frac{1}{x}, f : \mathbb{R} \setminus\{0\} \to \mathbb{R} \setminus\{0\}$$
$$y = b$$(è iniettiva e non è monotona)

![[Esempio Composizione Funzioni.png]]

<hr>

##### Funzioni pari e dispari 

Una $f$ si dice pari se $f(x) = f(-x), \forall x \in Dom(f)$

Una $f$ si dice dispari se $f(-x) = -f(x), \forall x \to Dom(f)$

> Queste proprietà hanno senso solo se $Dom(f)$ è simmetrica rispetto a 0, nel senso che $x \to Dom(f) \leftrightarrow -x \to Dom(f)$

<hr>

###### Esempio

- $f(x) = x^2$ è pari: $f(-x) = (-x)^2 = x^2 = f(x)$ (anche per $f(x) = x^{2n}, n \to \mathbb{N}$)
- $f(x) = x^3$ è dispari: $f(-x) = (-x)^3 = -x^3 = -f(x)$ (anche per $f(x) = x^{2n+1}, n \to \mathbb{N}$)
- 
![[Funzioni Pari o Dispari.png]]

<hr>

Una *f* si dice **periodica** di periodo $p \in \mathbb{R}$ se $\forall x \in Dom(f)$ vale $f(x+p) = f(x)$

> Il dominio di *f* deve essere pure "periodo di periodo di $p$" nel senso che $x \in (f) \to x+p \in Dom(f)$


<hr>

###### Esempio

$f(x) = sin(x), f : \mathbb{R} \to \mathbb{R}$ è periodica di periodo $2π$, cioè $sin(x + 2\pi) = sin(x)$

![[Funzioni Periodiche.png]]

<hr>


##### Funzioni elementari

- Funzioni lineari: $f(x) = ax + b$ con $a,b \in \mathbb{R}$
  ![[Funzioni Lineari.png]]
- Funzioni potenza: 
  1. $f(x) = x^n, n \in \mathbb{N}, D: \mathbb{R}$
  2. $f(x) = x^k, k \in \mathbb{Z}, k < 0$
     ![[Funzioni Potenza.png]]
 3. $f(x) = x^1$ con $q = \frac{m}{n}$, $m,n \in \mathbb{N}$, $D:  [0, +\infty)$ se $n$ è pari, se $n$ è dispari è $\mathbb{R}$`
    ![[Funzioni Potenza Frazionaria.png]]
    > $\sqrt[n]{x}$ è inversa della funzione $x^n$,
    
4. $f(x) = x^1$ con $q = \frac{m}{n}$ e $q < 0$, si definisce come $f(x) = \frac{1}{x^{-q}}, D: \mathbb{R} \setminus\{0\}$`
	![[Funzioni Potenza Frazionaria Negativa.png]]
- Funzione esponenziale
  1. $f(x) = a^x, a \in \mathbb{R}, a > 0$ e $a \neq 1, D: \mathbb{R}$
     ![[Funzioni Esponenziali.png]]
 2.  $f(x) = a^x, a \in \mathbb{R}, a < 1, D: \mathbb{R}$
    ![[Funzioni Esponenziali Base<1.png]]
> La funzione è strettamente crescente se $a > 1$ e strettamente decrescente se $0 < a < 1$
> 
> Se prendo come codominio l'insieme $(0, +\infty)$, la funzione $a^x$ è biunivoca, la sua inversa è $f^{-1}(x) = log_a(x)$, l'esponente che devo dare ad $a$ per ottenere $x$
	![[Pasted image 20230922104137.png]]
3. `f(x) = e^x`, l'inversa della funzione è il logaritmo naturale
	![[Logaritmo Naturale.png]]
4. $f(x) = x^\alpha, \alpha \in \mathbb{R}$
   > $x^\alpha  = e^{\alpha*log(x)}$
   >$D: [0, +\infty)$ se $\alpha$ è irrazionale oppure $\alpha > 0, (0, +\infty)$ se $\alpha < 0$ 
- Funzioni trigonometriche (e inverse)
  1. $f(x) = sin(x)$
  2. $f(x) = cos(x)$ 
> $cos(x) = sin(x+\pi/2)$
	![[Pasted image 20230922104800.png]]
	Queste funzioni non sono invertibili come $f : \mathbb{R} \to \mathbb{R}$ ($-1 \leq cos(x) \leq 1, -1 \leq sin(x) \leq 1$)
	Si possono invertire dopo aver ristretto dominio e codominio.
	$sin(x)$ è biunivoca se la vedo come funzione $[\frac{\pi}{2},\frac{\pi}{2}] \to [-1,1]$
	La sua inversa si indica con $arcsin(x)$ e si chiama arcoseno di $x$
	Uguale per il *coseno* vedendolo come una funzione $[0,\pi] \to [-1,1]$, l'inversa si chiama *arcoseno* e si denota con $arccos(x) : [-1,1] \to [0,\pi]$
	![[Pasted image 20230922105541.png]]
3. $f(x) = tan(x) = \frac{sin(x)}{cos(x)}, D: \mathbb{R} \setminus\{\frac{\pi}{2}+k\pi\}, k \in \mathbb{R}$
   > è periodica di periodo $\pi$
   > ![[Funzioni Trigonometriche (Co)Tangente.png]]
   > Se vedo $tan(x)$ come funzione $(-\frac{\pi}{2},\frac{\pi}{2}) \to \mathbb{R}$ questa è invertibile, l'inversa è l'*arcotangente* e si denota come $arctan(x)$
   > ![[Funzioni Trigonometriche (Co)Tangente Inversa.png]]