---
layout: default
title: Sezioni
nav_order: 5
---

# Sezioni

Ogni trave del modello ha una **sezione composta con il contorno reale**: le
lamiere e gli irrigidimenti sono poligoni (foglio `SectionPart` del file Excel di
feagent), così la vista estrusa mostra la sezione vera e le proprietà vengono
dalla geometria.

## Cassone stradale: dalla tavola PS0093

![PS0093, sezione trasversale del cassone stradale (estratto)](assets/img/tav_ps0093_sezione_cassone_stradale.png)
*Fonte: PS0093, Progetto Definitivo 2011, estratto della sezione trasversale.*

La sezione è costruita **dalle quote della tavola, senza tarature**
(`road_section` in `messina_sections.py`). Coordinate in mm, x dalla punta del
naso, z dal punto più basso:

| Elemento | Geometria |
|---|---|
| Ingombro | 14 219 × 2635 mm (D-1: 14,219 × 2,634 m) |
| Naso (lato esterno) | lamiera inclinata t4 dalla punta (0, 1373) allo spigolo (1014, 2371), lamiera di chiusura della punta a 375 mm |
| Piastra superiore | pendenza 2 %, più alta sul bordo interno (14 219, 2635): t4 per 705 mm, t1 corsia di emergenza 3600, t2 corsie di marcia 7680, t3 interna 1220 |
| Fondo (t5) | retta dalla punta a (6489, 176), arco R 10 605 con il punto più basso in x = 8413 (sviluppo 1924, freccia 176), arco fino a x = 12 789, arco R 2581 fino allo spigolo interno |
| Trapezi superiori | 23 a passo 510 dal primo in x = 2072: RS1 (7) e RS2 (16), 230 alla lamiera, 130 al fondo, alti 317 |
| Trapezi del fondo | 13 RS3, 500 alla lamiera, 170 in cima, alti 240 |
| Piatti | P1 152 × 14 sul naso, P2 174 × 16 sulla piastra, P3 140 × 14 sul fondo |

![Irrigidimenti RS1, RS2, RS3 e piatti (estratto)](assets/img/tav_ps0093_irrigidimenti.png)
*Fonte: PS0093.*

**Il naso sta sul lato esterno**, verso i pendini: accanto c'è la lamiera della
corsia di emergenza. Il bordo arrotondato è verso la fessura con il cassone
ferroviario.

### Spessori per tipo di concio [mm]

| | CS1 | CS2 | CS3 | CS4 | CS5 | CS6 | CS7 | CS8 |
|---|---|---|---|---|---|---|---|---|
| t1 corsia di emergenza | 14 | 14 | 14 | 14 | 14 | 14 | 14 | 14 |
| t2 corsie di marcia | 17 | 17 | 17 | 17 | 17 | 17 | 17 | 17 |
| t3 lamiera interna | 14 | 14 | 14 | 14 | 14 | 14 | 14 | 14 |
| t4 bordo e naso | 12 | 12 | 12 | 12 | 15 | 12 | 12 | 12 |
| t5 fondo | 8 | 9 | 9 | 12 | 14 | 10 | 13 | 12 |
| RS1 | 7 | 7 | 7 | 7 | 9 | 7 | 7 | 7 |
| RS2 | 9 | 9 | 9 | 9 | 9 | 9 | 9 | 9 |
| RS3 | 5 | 5 | 5 | 6 | 8 | 6 | 6 | 6 |
| acciaio | S355 | S420 | S460 | S460 | S460 | S460 | S460 | S460 |

Fonti: PS0093 (CS1, CS2, CS3, CS6, CS8), PS0097 (CS4, CS5), PS0100 (CS7). Il
tipo di concio di ogni trave si riconosce dalla g di D-1 meno la pavimentazione
(11,95 kN/m), confrontata con i pesi di PS0002 tab. 3.1.

![PS0093, tabella degli spessori (estratto)](assets/img/tav_ps0093_tabella_spessori.png)

### Confronto con D-1 di IBDAS

| Tipo | A | Iy (verticale) | Iz (laterale) | Iyz [m⁴] | baricentro |
|---|---|---|---|---|---|
| CS1 | +1,2 % | +0,8 % | +1,9 % | +0,216 / +0,214 | 1 cm |
| CS2, CS3 | +1,2 % | +0,7 % | +1,8 % | +0,219 / +0,217 | 1 cm |
| CS4 | +1,2 % | +0,6 % | +2,5 % | +0,230 / +0,214 | 1 cm |
| CS5 | +5,2 % | +2,9 % | +8,4 % | +0,205 / +0,219 | 12 cm |
| CS6 | +1,0 % | +0,4 % | +1,7 % | +0,224 / +0,220 | 1 cm |
| CS7 | +1,2 % | +0,7 % | +2,5 % | +0,233 / +0,217 | 1 cm |
| CS8 | +0,9 % | +0,4 % | +1,7 % | +0,230 / +0,226 | 1 cm |

La sezione presa solo dalla tavola riproduce D-1 entro l'1-2 %. Il piccolo
eccesso viene dai raccordi non modellati. Due eccezioni:

* **CS5**: la tavola ha lamiere più spesse di quelle usate in IBDAS 3.3f
  (area +5 %); vale la tavola;
* **diaframmi longitudinali** di CS4, CS5 e CS7 (due pareti verticali da 16 mm,
  PS0097 e PS0100): sono locali, vicino a giunti e appoggi, e D-1 non li conta
  (con loro l'area sarebbe +10 %). Non si modellano.

Il contorno coincide con quello del **modello a gusci IBDAS** (diaframmi della
fila 3, PS0003 Appendice A):

![Sezioni del modello sovrapposte al contorno IBDAS dei diaframmi](assets/img/confronto_diaframmi.png)

![PS0003 App. A pag. 35: diaframmi del modello a gusci, i tre cassoni affiancati](assets/img/ibdas_ps0003_diaframmi.png)
*Fonte: PS0003, Appendice A (uscita IBDAS, vista ortogonale): i nasi stanno ai due bordi esterni.*

{: .warning }
Le figure in prospettiva di PS0002 (fig. 2.3) e PS0003 (fig. 2.6) **non dicono da
che parte stia il naso**: una prima lettura lo metteva verso la fessura. Le
quote della tavola e il diaframma IBDAS lo mettono sul lato esterno, e solo così
il prodotto d'inerzia e il baricentro tornano con D-1.

### Costante di torsione

La costante di Saint-Venant di D-1 (Iv) è quella di **Bredt della sola cella
principale**: con la sezione della tavola la cella principale dà 0,9445 m⁴
contro 0,945 (CS1), 1,0191 contro 1,020 (CS2), 1,2103 contro 1,211 (CS8).
IBDAS trascura le celle chiuse dei trapezi, come si fa di solito per la torsione
globale dei cassoni; la teoria completa delle pareti sottili, che le include,
darebbe circa il 6-7 % in più. Nel modello si usa Iv di D-1.

## Cassone ferroviario

![PS0102, sezione trasversale del cassone ferroviario (estratto)](assets/img/tav_ps0102_sezione_cassone_ferroviario.png)
*Fonte: PS0102.*

Larghezza 7500 mm, altezza 2275 mm in asse, piastra superiore al 2 % verso i due
lati, anime verticali per 1000 mm poi inclinate, fondo largo con trapezi RF1,
quattro travi a T profonde sotto i binari (765 mm, anima 14, piattabanda 300 × 22).
Nel modello il contorno segue il diaframma IBDAS (colmo in mezzeria, anime
verticali fino al 47 % dell'altezza, fondo largo l'84 %) con le quattro travi a T
a 0,13, 0,33, 0,67 e 0,87 della larghezza; gli spessori sono tarati su D-1, che
riproduce entro lo 0,1 % (0,5 % sul concio CF4).

## Traversi dei pendini

Vedi [Traversi e collegamenti](05-traversi.html): cassone rettangolare largo 3,77 m
(lungo l'asse del ponte), alto da 1,5 a 4,7 m, con le sezioni di D-1 interpolate
nei nodi.

## Torri

Gamba: ottagono di circa 12 × 20 m con smussi da 2 m e pareti interne a croce,
irrigidimenti a piatto; traversi di torre: cassoni alti fino a 20,5 m con spigoli
rinforzati. Spessori e altezze degli irrigidimenti sono tarati sulle righe di D-1
(errori sotto lo 0,1 %).

![Sezioni del modello: cassone stradale, ferroviario, traverso, gamba e traverso di torre](assets/img/sezioni_modello.png)
