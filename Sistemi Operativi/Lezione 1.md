### Τα γενεσις
* Architetture degli Elaboratori
* Sistemi Operativi

Il ciclo di clock deve tenere conto dei ritardi delle varie operazioni, per cui il tempo di clock deve essere maggiore del tempo di ritardo massimo.

**Single-Cycle**
- Ogni ciclo di Fetch-Decode-Execute deve essere completato in un singolo ciclo di clock.
  Tc = 
  N
  Tc
  t_sc: _ciclo di clock_
  CPI_sc: _Clock Per Instruction_


**Pipeline Arch**
- Ogni ciclo di Fetch-Decode-Execute è diviso in più cicli di clock.
>Il ciclo di clock di una architettura pipeline è minore del ciclo di clock di una architettura single-cycle. *t_pipe < t_sc_*

**Superscalar Arch**
- Ogni ciclo di clock può eseguire più di un'istruzione in base al numero di unità di esecuzione.
>In una architettura superscalar il ciclo di clock è minore del ciclo di clock di una architettura pipeline perché ogni ciclo di clock può eseguire più di un'istruzione in base al numero di unità di esecuzione. *CPI_ss < CPI_sc*


**Multithreading**: è una tecnica che permette di eseguire più thread contemporaneamente su un singolo processore.