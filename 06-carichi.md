---
layout: default
title: Carichi permanenti
nav_order: 7
---

# Carichi permanenti

Casi **PP** (strutturali) e **PN** (non strutturali) di PS0002 par. 3.2, uguali
voce per voce alla colonna del modello 3.3f di PG0022. La g di D-1 è il peso del
modello geometrico (acciaio a 77 kN/m³); il resto si applica come carico, come in IBDAS.

## Voci applicate

| Elemento | Voce | Valore | Caso |
|---|---|---|---|
| Cassoni stradali | g di D-1 (acciaio + pavimentazione 1 kN/m² su 11,95 m) | da D-1 | PP |
| | diaframmi per tipo CS1-CS8 | 4,5; 4,5; 4,5; 10,7; 5,7; 4,7; 4,3; 4,5 kN/m | PP |
| | lamiere non modellate + rinforzi + saldature + pittura | 0,5 + 0,4 + 0,35 + 0,62 kN/m | PP |
| | peso proprio aggiuntivo | 1,5 kN/m | PN |
| | attrezzature (parapetti, corsia di servizio esterna, illuminazione, servizi, carroponte, passerelle, drenaggio, frangivento, rotaie del carrello) | 18,11 kN/m | PN |
| Cassone ferroviario | g di D-1 | da D-1 | PP |
| | diaframmi per tipo CF1-CF9 | 3,5; 3,5; 4,4; 5,1; 4,2; 4,2; 4,7; 6,2; 3,0 kN/m | PP |
| | lamiere non modellate + rinforzi + saldature + pittura | 0,5 + 0,08 + 0,28 + 0,59 kN/m | PP |
| | peso proprio aggiuntivo | 1,5 kN/m | PN |
| | attrezzature (binari e catenaria, passerelle di emergenza, servizi, antincendio, lavaggio, passerelle, drenaggio, pareti) | 18,08 kN/m | PN |
| Traversi dei pendini | g di D-1 lungo il traverso | da D-1 | PP |
| | calibrazione per tipo (tab. 3.2) | vedi sotto | PP |
| | articolazione | 0,6 kN/m | PN |
| Ancoraggi dei pendini | acciaio extra per tipo di cassone (tab. 3.4) | 89; 83; 86; 233; 187; 187; 233; 114 kN | PP |
| Incroci di servizio | a 315 e 1215 m dalle torri | 13,2 kN/m sulla campata, 7,4 kN/m sulle adiacenti, **per ciascuna fessura** | PP |
| Cavi principali | acciaio A·77 kN/m³ + ancoraggi 2,5 + pittura 0,2 + avvolgimento 1,0 + accesso 0,2 kN/m per cavo | | PP |
| Pendini | acciaio A·77 kN/m³ + protezione 0,05 (campata) o 0,1 kN/m (oltre le torri) | | PP |
| Gambe di torre | g di D-1 + ossature 59 + giunti 49 + pittura 0,49 kN/m | | PP |
| | 687 kN a ogni incrocio gamba-traverso | | PP |
| | accessi | 10 kN/m | PN |
| Traversi di torre | g di D-1 × 1,15 (diaframmi) + articolazione 1,5 kN/m | | PP |
| Selle di torre | passante 5300 + struttura 11 500 kN per sella | | PP |
| Selle di deviazione | 4900 kN in testa a ciascun pendolo | | PP |
| Parti secondarie | g di D-1 | | PP |

I pesi dei blocchi di ancoraggio (8343 e 7076 MN) e delle fondazioni delle torri
gravano su vincoli rigidi e non cambiano né spostamenti né sollecitazioni: non si
applicano.

## Taratura sui tiri dei pendini di IBDAS

Con tutte le voci documentate l'impalcato in campata pesa circa **277 kN/m**,
mentre i tiri E-3 dei pendini ne portano **254,5**: tutti i pendini risultano
circa l'8 % sopra IBDAS e il cavo il 2,8 %. Il confronto stazione per stazione
dice che cosa manca allo stato IBDAS:

* in campata corrente l'eccesso è uniforme, circa 310 kN per lato e per pendino,
  pari alla **calibrazione dei traversi T1** (433 kN) più l'**acciaio extra degli
  ancoraggi** (circa 85 kN per lato): 216 + 84 = 300 kN;
* agli **incroci di servizio** l'incremento E-3 è il doppio di quello del testo
  letto come 13,2 kN/m in tutto: il valore vale per ciascuna delle due fessure.

| Variante | Pendini (scarto medio) | Cavo in mezzeria | Cavo alla sella |
|---|---|---|---|
| tutte le voci documentate | +7,9 % | +2,8 % | +2,9 % |
| senza calibrazione dei traversi e ancoraggi (**adottata**) | −0,2 % | −0,2 % | −0,2 % |
| calibrazione e ancoraggi solo sui traversi speciali | +0,8 % | −0,1 % | −0,1 % |

La variante adottata riproduce lo stato IBDAS in campata entro l'1 %. Vicino
alle torri (|s| > 1560 m) restano scarti fra −11 % e +9 % a seconda della
variante: lì il carico si ripartisce fra pendini e appoggi di torre e non si
riesce a isolare la voce. Il parametro `XBEAM_EXTRA` dello script sceglie la
variante (`"nessuno"`, `"speciali"`, `"tutti"`).
