---
layout: default
title: Geometria
nav_order: 4
---

# Geometria

La geometria viene dalle coordinate dei nodi IBDAS (C-1, corrette con E-1) e
dalle aree degli elementi cavo (D-2). Lo stato finale sotto i permanenti è la
geometria C-1 più gli spostamenti E-1.

![Prospetto: cavo, impalcato e torri](assets/img/geometria_prospetto.png)

## Cavi principali

| Grandezza | Valore |
|---|---|
| Ancoraggio Sicilia (s, z) | −2630,4 m, 40,8 m |
| Sella di torre | s = ±1650 m, quota 399,0 m |
| Mezzeria del cavo | quota 84,6 m (freccia 314,4 m) |
| Ancoraggio Calabria (s, z) | +2480,3 m, 105,3 m |
| Area metallica per cavo | 1,015 m² campata principale, 1,050 m² laterale Sicilia, 1,038 m² laterale Calabria |
| Cavi per lato | 2 gemelli, legati nodo per nodo in C-2 |

I due cavi gemelli di ciascun lato sono un unico elemento nel loro baricentro
(y = ±26 m) con l'area somma. Ogni tratto fra due nodi IBDAS è un elemento cavo
non lineare; la lunghezza a riposo viene dal tiro E-3 nella geometria finale:
`L0 = L_fin / (1 + N / EA)` (E = 200 GPa).

Le selle di deviazione agli ancoraggi stanno in testa ai pendoli (parti 4-7), che
poggiano sui blocchi di ancoraggio.

## Pendini

* 119 per lato: ogni 30 m sull'impalcato sospeso (117 stazioni, da s = −1770 a
  +1770 m, con la lacuna alle torri) più i due delle strutture terminali a s = ±1833 m;
* area da D-2 (in campata 2 × 7179 mm², verso le torri fino a 2 × 19 204 mm²);
* lunghezza a riposo dal tiro E-3, come per i cavi.

## Impalcato

**Tre travi longitudinali** (cassoni), collegate dai traversi dei pendini:

| Trave | Posizione (y IBDAS) | Sezione |
|---|---|---|
| cassone stradale Ovest | −18,55 m | stradale, 14,22 × 2,63 m, naso esterno |
| cassone ferroviario | 0 | ferroviario, 7,50 × 2,28 m |
| cassone stradale Est | +18,55 m | stradale, speculare dell'Ovest |

* lunghezza dell'impalcato sospeso 3639,5 m, giunti a s = ±1819,75 m;
* profilo verticale reale: quota 53,6 m al giunto Sicilia, 78,1 m in mezzeria,
  62,0 m al giunto Calabria;
* stazioni di calcolo: i pendini, i punti medi fra due pendini, i giunti e gli
  attacchi alle torri; travi a sezione variabile dove D-1 cambia sezione;
* nessuna trave di bordo continua: i pendini scaricano sulle teste dei traversi.

## Torri

* gambe da quota circa 19 m a 394 m, linea reale da y = ±39,2 m alla base a
  ±26,0 m in sommità;
* sezione variabile da D-1 (ottagono con pareti interne a croce);
* tre traversi di torre a quota 123,5, 249,0 e 374,5 m, in 6 segmenti a sezione variabile;
* sella collegata alla sommità della gamba, senza vincoli;
* base incastrata (in IBDAS la fondazione delle torri è rigida, C-3).

## Parti secondarie

Strutture terminali, viadotti di approccio, pile, fondazioni con le molle di C-3,
blocchi di ancoraggio, collegamenti impalcato-torre e ammortizzatori sono
importati da C-1, C-2, C-3 e D-1 (`messina_ibdas_parts.py`), con le regole
descritte in [Vincoli e parti secondarie](07-vincoli.html).
