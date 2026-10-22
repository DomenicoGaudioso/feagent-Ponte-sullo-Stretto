---
layout: default
title: Vincoli e parti secondarie
nav_order: 8
---

# Vincoli e parti secondarie

## Vincoli

* **Nessun vincolo sui cavi**: ancoraggi e selle sono collegamenti alle strutture.
* Basi delle gambe di torre incastrate (in IBDAS la fondazione è rigida).
* Fondazioni delle pile e delle strutture terminali con le molle di C-3
  (vincolo fisso oltre 5·10⁹ nelle unità di C-3).
* Blocchi di ancoraggio incastrati.

## Parti secondarie importate da C-1, C-2, C-3 e D-1

Strutture terminali (5001-5005, 5299-5303), viadotti di approccio, pile e
fondazioni (921-931, 4001-4011), blocchi di ancoraggio (951, 952) e pendoli delle
selle di deviazione (4-7), collegamenti impalcato-torre (5311-5347),
ammortizzatori longitudinali.

Regole di traduzione dei collegamenti di C-2:

| Caso | Traduzione in feagent |
|---|---|
| nodi coincidenti senza rilasci | nodo unico |
| nodi distanti senza rilasci | braccio rigido |
| rilasci | braccio rigido dal master e molla a lunghezza nulla sui GdL vincolati |
| coppie di elementi fittizi della stessa parte | sempre rigide |
| appoggio con molla definita fuori dalle appendici (`al_r_sp`) | fisso nelle tre traslazioni (ipotesi) |
| base dei pendoli delle selle di deviazione (riga illeggibile di C-2) | braccio rigido dal blocco di ancoraggio e **cerniera**: rotazione libera attorno all'asse trasversale, così il pendolo oscilla nel piano del cavo e il tiro passa uguale sui due lati della sella, come nei casi di validazione di PS0005 (LC7: +81,8 MN in campata laterale, +81,7 MN all'ancoraggio). Nella prima versione il pendolo era incastrato e lavorava a mensola, trattenendo un terzo della variazione di tiro |
| ammortizzatori | bloccati (sistema fisso-fisso, come per la modale e la statica IBDAS), o molla di 33 MN/m nel sistema libero-libero |

Le linee delle parti secondarie sono diradate a un nodo ogni 10 m, mantenendo i
nodi collegati o vincolati. Le sezioni sono cassoni equivalenti tarati su D-1.

## Elementi rigidi rimasti

L'impalcato sospeso e le torri non hanno elementi di collegamento. Nelle parti
secondarie restano circa 300 **travi rigide** (sezione dipendente dalla lunghezza,
E dieci volte l'acciaio): sono le parti che IBDAS stesso modella come elementi
fittizi rigidi, cioè blocchi di ancoraggio, tratti fittizi delle fondazioni e
bracci degli appoggi delle strutture terminali. Le **molle a lunghezza nulla**
servono solo dove C-2 dichiara un rilascio (appoggi, ammortizzatori).
