---
layout: default
title: Fonti e documenti
nav_order: 2
---

# Fonti e documenti

Tutti i dati vengono dal **Progetto Definitivo** (2011) pubblicato sul portale
delle valutazioni ambientali del Ministero (`va.mite.gov.it`). Ogni documento si
scarica da `https://va.mite.gov.it/File/Documento/<id>`.

{: .note }
Gli identificativi del portale sono progressivi nello stesso ordine del catalogo
degli elaborati: da PS0014-ITA (id 37639) a PS0252-ITA (id 37902) ci sono 263
righe di catalogo e 263 identificativi. Così si ricavano anche gli identificativi
delle tavole che il catalogo non collega; ogni identificativo è stato verificato
sul nome del file restituito dal portale.

## Modello IBDAS e relazioni

| Codice | Titolo | id | Uso nel modello |
|---|---|---|---|
| PS0002 (ITA) | Modello Globale IBDAS, descrizione, con le appendici C, D, E, F | 37623 | nodi, collegamenti, vincoli, sezioni, stato di riferimento, frequenze |
| PS0003 (ITA) | Modello semi-locale IBDAS, impalcato sospeso | 37625 | profili IBDAS dei cassoni, diaframmi del modello a gusci (Appendice A) |
| PS0004 (ITA) | Modello semi-locale IBDAS (torri) | 37627 | contesto |
| PS0005 | Validazione del modello globale | 37628 | modi propri e casi di validazione |
| PG0021 (ITA) | Modello Globale IBDAS, descrizione | 37123 | contesto |
| PG0022 (ITA) | Riassunto carichi permanenti per il modello globale | 37125 | carichi PP e PN, colonne dei modelli 3.1, 3.2, 3.3f |
| PB0030, PB0031 | Matrici di rigidezza suolo-fondazioni | 36793, 36795 | fondazioni (contesto) |
| PS0077 | Relazione di progetto, impalcato stradale, ferroviario e traversi | 37705 | contesto |
| PS0016 | Relazione di progetto, traversi | 37641 | contesto |

## Appendici di PS0002 usate

| Appendice | Contenuto | Righe lette |
|---|---|---|
| C-1 | coordinate dei nodi (parte, segmento, taglio, nodo) | 10 034 |
| C-2 | collegamenti master-slave con i rilasci | circa 3 363 |
| C-3 | vincoli e molle di fondazione | 274 |
| D-1 | sezioni delle travi per punto di Gauss: A, Ay, Az, Iy, Iz, Iyz, Iv, g, ingombri, E, G | 6 638 |
| D-2 | aree degli elementi cavo (cavi e pendini) | 742 |
| E-1 | spostamenti dello stato di riferimento | 10 034 |
| E-3 | tiri di cavi e pendini nello stato di riferimento | 918 |
| F-1, F-2 | frequenze e masse partecipanti | |

Le tabelle sono lette dal testo estratto dal PDF, con controlli sui numeri
spezzati e fusi (`messina_ibdas_tables.py`). C-1 perde alcuni zeri interni: le
coordinate si prendono da E-1, che le riporta intere.

## Tavole dell'impalcato

| Codice | Titolo | id | Contenuto usato |
|---|---|---|---|
| PS0093 | Cassoni stradali, campata principale e laterali, sezione | 37721 | sezione quotata 1:20, spessori CS1, CS2, CS3, CS6, CS8 |
| PS0094 | Cassoni stradali, campata principale e laterali, diaframmi | 37722 | contesto |
| PS0097 | Cassoni stradali, campata di torre, sezione e prospetto | 37725 | spessori CS4 e CS5, diaframmi longitudinali |
| PS0100 | Cassoni stradali, parte terminale, sezione | 37728 | spessori CS7 |
| PS0102 | Cassone ferroviario, campata principale, sezione | 37730 | sezione quotata, spessori CF1, CF2 |
| PS0103 | Cassone ferroviario, campata principale, diaframmi | 37731 | contesto |
| PS0085, PS0087 | Campata principale e campata di torre, pianta e sezioni | 37713, 37715 | contesto |
| PS0115, PS0116 | Traversi principali, campata principale, sezioni 1 e 2 | 37743, 37744 | prospetto e spessori dei traversi T1 e T3 |
| PS0121 a PS0123 | Traversi, campata di torre, sezioni 1-3 | 37749 a 37751 | contesto |
| PS0128, PS0129 | Traversi, campata laterale, sezioni 1-2 | 37756, 37757 | contesto |
| PS0132, PS0133 | Traversi, campata terminale, sezioni 1-2 | 37760, 37761 | contesto |
| PS0200 | Supporti dell'impalcato sospeso e delle strutture terminali | 37839 | contesto |

{: .warning }
Le figure di questa documentazione riportano solo gli estratti necessari (sezioni,
tabelle degli spessori), con la fonte. Per i documenti completi si rimanda al
portale.
