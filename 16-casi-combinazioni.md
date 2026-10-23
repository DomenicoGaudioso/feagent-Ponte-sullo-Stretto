---
layout: default
title: Casi di carico e combinazioni
nav_order: 10.7
---

# Casi di carico e combinazioni

Il file del modello per la GUI di feagent
(`examples/ponte_stretto_messina/ponte_stretto_messina.xlsx`) contiene **tutti i casi di
carico** (41) e **tutte le combinazioni** (441) di PG0024 cap. 6 che si
possono formare con le azioni del modello. Le combinazioni stanno nel foglio `Combination`,
si rileggono all'apertura e vanno negli esportatori: MIDAS (`*LOADCOMB`) e SAP2000
(definizioni dei casi e delle combinazioni). Gli altri formati avvisano che restano nel file
di feagent.

## Casi di carico

| Caso | Descrizione |
|---|---|
| QA uz mezzeria min | QA (PG0024 5.2.2) per min di abbassamento del ferroviario in mezzeria: carreggiata Ovest: 5 kN/m a y = +22.48, 5 kN/m a y = +18.76, 15 kN/m a y = +14.92; carreggiata Est: 5 kN/m a y = -22.48, 5 kN/m a y = -18.76, 15 kN/m a y = -14.92; binario y = +2.0: treno da s = -370 m; binario y = -2.0: treno da s = -370 m |
| QA uz mezzeria max | QA (PG0024 5.2.2) per max di sollevamento del ferroviario in mezzeria: carreggiata Ovest: 15 kN/m a y = +22.48, 5 kN/m a y = +18.76, 5 kN/m a y = +14.92; carreggiata Est: 15 kN/m a y = -22.48, 5 kN/m a y = -18.76, 5 kN/m a y = -14.92; binario y = +2.0: treno da s = -1615 m, treno da s = 865 m; binario y = -2.0: treno da s = -1615 m, treno da s = 865 m |
| QA tiro cavo max | QA (PG0024 5.2.2) per max di tiro del cavo Ovest in mezzeria: carreggiata Ovest: 15 kN/m a y = +22.48, 5 kN/m a y = +18.76, 5 kN/m a y = +14.92; carreggiata Est: 5 kN/m a y = -22.48, 5 kN/m a y = -18.76, 15 kN/m a y = -14.92; binario y = +2.0: treno da s = -1120 m, treno da s = 380 m; binario y = -2.0: treno da s = -1120 m, treno da s = 380 m |
| QA pendino max | QA (PG0024 5.2.2) per max di pendino piu' sollecitato: carreggiata Ovest: 5 kN/m a y = +22.48, 5 kN/m a y = +18.76, 15 kN/m a y = +14.92; carreggiata Est: 15 kN/m a y = -22.48, 5 kN/m a y = -18.76, 5 kN/m a y = -14.92; binario y = +2.0: treno da s = -1785 m; binario y = -2.0: treno da s = -1785 m |
| QA M ferroviario min | QA (PG0024 5.2.2) per min di momento negativo del ferroviario alla torre: carreggiata Ovest: 5 kN/m a y = +22.48, 5 kN/m a y = +18.76, 15 kN/m a y = +14.92; carreggiata Est: 5 kN/m a y = -22.48, 5 kN/m a y = -18.76, 15 kN/m a y = -14.92; binario y = +2.0: treno da s = -1785 m; binario y = -2.0: treno da s = -1785 m |
| QA M base torre max | QA (PG0024 5.2.2) per max di momento longitudinale alla base della gamba Ovest, torre Sicilia: carreggiata Ovest: 15 kN/m a y = +22.48, 5 kN/m a y = +18.76, 5 kN/m a y = +14.92; carreggiata Est: 5 kN/m a y = -22.48, 5 kN/m a y = -18.76, 15 kN/m a y = -14.92; binario y = +2.0: treno da s = -1120 m, treno da s = 380 m; binario y = -2.0: treno da s = -1115 m, treno da s = 385 m |
| QA torsione max | QA (PG0024 5.2.2) per max di rotazione torsionale del ferroviario: carreggiata Ovest: 15 kN/m a y = +22.48, 5 kN/m a y = +18.76, 5 kN/m a y = +14.92; carreggiata Est: 15 kN/m a y = -22.48, 5 kN/m a y = -18.76, 5 kN/m a y = -14.92; binario y = +2.0: treno da s = -2450 m, treno da s = 470 m; binario y = -2.0: treno da s = -1165 m |
| QR uz mezzeria min | QR (PG0024 5.2.2) per min di abbassamento del ferroviario in mezzeria: carreggiata Ovest: 1.25 kN/m a y = +18.76, 3.75 kN/m a y = +14.92; carreggiata Est: 1.25 kN/m a y = -18.76, 3.75 kN/m a y = -14.92; binario y = +2.0: treno da s = -370 m; binario y = -2.0: treno da s = -370 m |
| QR uz mezzeria max | QR (PG0024 5.2.2) per max di sollevamento del ferroviario in mezzeria: carreggiata Ovest: 3.75 kN/m a y = +22.48, 1.25 kN/m a y = +18.76; carreggiata Est: 3.75 kN/m a y = -22.48, 1.25 kN/m a y = -18.76; binario y = +2.0: treno da s = 865 m; binario y = -2.0: treno da s = 865 m |
| QR tiro cavo max | QR (PG0024 5.2.2) per max di tiro del cavo Ovest in mezzeria: carreggiata Ovest: 3.75 kN/m a y = +22.48, 1.25 kN/m a y = +18.76; carreggiata Est: 1.25 kN/m a y = -18.76, 3.75 kN/m a y = -14.92; binario y = +2.0: treno da s = -365 m; binario y = -2.0: treno da s = -365 m |
| QR pendino max | QR (PG0024 5.2.2) per max di pendino piu' sollecitato: carreggiata Ovest: 1.25 kN/m a y = +18.76, 3.75 kN/m a y = +14.92; carreggiata Est: 3.75 kN/m a y = -22.48, 1.25 kN/m a y = -18.76; binario y = +2.0: treno da s = -1785 m; binario y = -2.0: treno da s = -1785 m |
| QR M ferroviario min | QR (PG0024 5.2.2) per min di momento negativo del ferroviario alla torre: carreggiata Ovest: 1.25 kN/m a y = +18.76, 3.75 kN/m a y = +14.92; carreggiata Est: 1.25 kN/m a y = -18.76, 3.75 kN/m a y = -14.92; binario y = +2.0: treno da s = -1785 m; binario y = -2.0: treno da s = -1785 m |
| QR M base torre max | QR (PG0024 5.2.2) per max di momento longitudinale alla base della gamba Ovest, torre Sicilia: carreggiata Ovest: 3.75 kN/m a y = +22.48, 1.25 kN/m a y = +18.76; carreggiata Est: 1.25 kN/m a y = -18.76, 3.75 kN/m a y = -14.92; binario y = +2.0: treno da s = 310 m; binario y = -2.0: treno da s = 355 m |
| QR torsione max | QR (PG0024 5.2.2) per max di rotazione torsionale del ferroviario: carreggiata Ovest: 3.75 kN/m a y = +22.48, 1.25 kN/m a y = +18.76; carreggiata Est: 3.75 kN/m a y = -22.48, 1.25 kN/m a y = -18.76; binario y = +2.0: treno da s = 470 m; binario y = -2.0: treno da s = -1165 m |
| Q frenatura | 7000 kN sui binari fra s = -820 e -70 m e 2,5 kN/m sulla carreggiata Ovest, verso s+ |
| VV trasv. da Ovest | vento medio con alpha_r = 1 (u = 44 m/s a 70 m), trasv. da Ovest, senza traffico |
| VV trasv. da Ovest traffico | vento medio con alpha_r = 1, trasv. da Ovest, coefficienti con traffico |
| VV trasv. da Est | vento medio con alpha_r = 1 (u = 44 m/s a 70 m), trasv. da Est, senza traffico |
| VV trasv. da Est traffico | vento medio con alpha_r = 1, trasv. da Est, coefficienti con traffico |
| VV 45 s+ da Ovest | vento medio con alpha_r = 1 (u = 44 m/s a 70 m), 45 s+ da Ovest, senza traffico |
| VV 45 s+ da Ovest traffico | vento medio con alpha_r = 1, 45 s+ da Ovest, coefficienti con traffico |
| VV 45 s- da Ovest | vento medio con alpha_r = 1 (u = 44 m/s a 70 m), 45 s- da Ovest, senza traffico |
| VV 45 s- da Ovest traffico | vento medio con alpha_r = 1, 45 s- da Ovest, coefficienti con traffico |
| VV 45 s+ da Est | vento medio con alpha_r = 1 (u = 44 m/s a 70 m), 45 s+ da Est, senza traffico |
| VV 45 s+ da Est traffico | vento medio con alpha_r = 1, 45 s+ da Est, coefficienti con traffico |
| VV 45 s- da Est | vento medio con alpha_r = 1 (u = 44 m/s a 70 m), 45 s- da Est, senza traffico |
| VV 45 s- da Est traffico | vento medio con alpha_r = 1, 45 s- da Est, coefficienti con traffico |
| VV long. s+ | vento medio con alpha_r = 1 (u = 44 m/s a 70 m), long. s+, senza traffico |
| VV long. s- | vento medio con alpha_r = 1 (u = 44 m/s a 70 m), long. s-, senza traffico |
| LC1 | caso di validazione IBDAS di PS0005: 2 x 5000 kN verticali verso il basso in mezzeria, agli attacchi dei pendini |
| LC2 | caso di validazione IBDAS di PS0005: 2 x 5000 kN verticali verso il basso a 330 m dalla torre Sicilia, agli attacchi dei pendini |
| LC3 | caso di validazione IBDAS di PS0005: 3 x 3300 kN longitudinali all'estremita' Sicilia dell'impalcato (uno per cassone), verso la Sicilia |
| LC4 | caso di validazione IBDAS di PS0005: 2 x 10000 kN trasversali in testa a ciascuna torre (uno per gamba) |
| LC5 | caso di validazione IBDAS di PS0005: coppia attorno alla verticale in testa a ciascuna torre: 10000 kN longitudinali, opposti, sulle due gambe |
| LC6 | caso di validazione IBDAS di PS0005: 2 x 100 kN/m longitudinali su tutta l'altezza delle gambe di entrambe le torri, verso la Calabria |
| LC7 | caso di validazione IBDAS di PS0005: 25 kN/m verticali su meta' larghezza (cassone stradale Ovest), per tutta la lunghezza |
| LC8 | caso di validazione IBDAS di PS0005: 25 kN/m verticali a scacchiera: cassone Est nella meta' Sicilia, cassone Ovest nella meta' Calabria |
| LC9 | caso di validazione IBDAS di PS0005: 10 kN/m trasversali su tutta la lunghezza dell'impalcato |
| LC10 | caso di validazione IBDAS di PS0005: 3 x 25 kN/m verticali (uno per cassone) sulla meta' Sicilia dell'impalcato |
| PP | peso proprio strutturale (PS0002 par. 3.2, PG0022) |
| PN | peso proprio non strutturale (PS0002 par. 3.2, PG0022) |

I casi QA e QR sono le **disposizioni dei carichi da traffico** che portano al massimo
(o al minimo) la grandezza indicata, trovate sulle linee d'influenza (vedi
[Carichi mobili e vento](14-mobili-vento.html)); il vento è il **vento medio con
α<sub>r</sub> = 1** (44 m/s a 70 m), da scalare nelle combinazioni.

## Combinazioni (PG0024 tab. 22-25)

Coefficienti di PG0024 cap. 6; μ = 1,15 sul peso proprio se sfavorevole, 0,95 se
favorevole. Il vento entra come **raffica statica** (1,35 la pressione del vento medio) al
livello dello stato limite: coefficiente α<sub>r</sub>² · 1,35 sul caso di vento medio
(SLS1 1,35; SLS2 1,546; SLU 1,977; SLIS 2,460). Le combinazioni con traffico e vento usano
i casi di vento con i coefficienti aerodinamici con traffico.

| Gruppo | Combinazioni | Composizione |
|---|---|---|
| SLIS25-1 | 84 | μ PP + PN + QR + VV con traffico (SLIS) |
| SLS22-1 | 1 | PP + PN |
| SLS22-2 | 7 | PP + PN + QR |
| SLS22-3 | 8 | PP + PN + VV (SLS1) |
| SLS22-4 | 42 | PP + PN + QR + VV con traffico (SLS1) |
| SLS23-1 | 2 | PP + 0/1 PN |
| SLS23-2 | 16 | PP + 0/1 PN + VV (SLS2) |
| SLS23-4 | 7 | PP + PN + QA + frenatura |
| SLS23-5 | 42 | PP + PN + QA + frenatura + VV con traffico (SLS1) |
| SLU24-1 | 4 | μ PP + 0/1,5 PN |
| SLU24-2 | 32 | μ PP + 0/1,5 PN + VV (SLU) |
| SLU24-5 | 28 | μ PP + 0,9/1,5 PN + 1,5 (QA + frenatura) |
| SLU24-6 | 168 | μ PP + 0,9/1,5 PN + 1,1 (QA + frenatura) + VV con traffico (SLU) |

Non sono nel modello, e quindi nelle combinazioni, la termica (VT), il sisma (VS), le
acque meteoriche (VR) e le azioni accidentali (A).

Per un ponte sospeso la sovrapposizione degli effetti non vale: le combinazioni vanno
risolte con la statica non lineare (Newton dallo stato di riferimento), come le verifiche
non lineari della pagina dei carichi mobili. Negli esportatori sono combinazioni lineari dei
casi, utili per controlli e per programmi che le risolvono da sé.

