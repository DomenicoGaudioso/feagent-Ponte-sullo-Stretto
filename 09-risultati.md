---
layout: default
title: Risultati e confronto con IBDAS
nav_order: 10
---

# Risultati e confronto con IBDAS

Modello completo: 3971 nodi, 3980 travi, 578 cavi e pendini, tutto a elementi
trave. Stato di riferimento sotto i permanenti PP + PN, con la controfreccia delle
torri trovata per iterazione (vedi [Stato di riferimento](08-stato-di-riferimento.html)).

## Tiri dei cavi sotto i permanenti (per lato)

| Punto | feagent [MN] | IBDAS E-3 [MN] | Scarto |
|---|---|---|---|
| mezzeria | 1291 | 1289 | +0,1 % |
| sella, campata centrale | 1384 | 1383 | +0,1 % |
| sella, campata laterale | 1407 | 1417 | −0,7 % |
| ancoraggio Sicilia | 1328 | 1341 | −0,9 % |

## Pendini

Scarto dai tiri E-3 di IBDAS sull'impalcato sospeso: **1,6 % in media**, 10 % al
massimo, sui pendini più vicini alle torri (vedi [Punti aperti](11-punti-aperti.html)).

## Modi propri

| Modo | feagent [Hz] | IBDAS 3.3f [Hz] | Scarto |
|---|---|---|---|
| 1° trasversale | 0,0296 | 0,030 | −1,3 % |
| 1° verticale antisimmetrico | 0,0504 | 0,055 | −8,3 % |
| longitudinale | 0,0647 | 0,065 | −0,5 % |
| 1° verticale simmetrico | 0,0804 | 0,081 | −0,7 % |

La modale si fa sulla rigidezza tangente dello stato di riferimento, con il
solutore sparso di feagent esteso ai cavi.

## Pesi applicati (PS0002 par. 3.2)

| Gruppo | PP [MN] | PN [MN] |
|---|---|---|
| cassoni | 599,5 | 214,0 |
| traversi | 158,7 | 3,7 |
| torri | 1179,9 | 15,1 |
| parti secondarie | 1751,1 | 0,0 |
| pendoli | 19,6 | 0,0 |
| cavi | 1753,2 | 0,0 |
| pendini | 44,9 | 0,0 |

Carico medio dell'impalcato sospeso: 268,1 kN/m, contro 270,5 kN/m della somma
dei tiri E-3 dei pendini divisa per la lunghezza.

## Casi statici di validazione di PS0005

La risposta alle azioni variabili si confronta con cinque dei casi statici di
validazione IBDAS: vedi [Carichi mobili e vento](14-mobili-vento.html). In sintesi
i tiri dei cavi tornano entro il 2-4 %, gli spostamenti trasversali entro il 6 %,
gli abbassamenti verticali del cavo sono il 10-12 % più piccoli di IBDAS.
