---
layout: default
title: Sezioni da disegno DXF
nav_order: 13
---

# Sezioni da disegno DXF in feagent

Le sezioni atipiche del ponte hanno fatto nascere uno strumento generale di
feagent: **`feagent.sezioni_dxf`**, per portare in un modello qualunque sezione
disegnata a CAD (cassoni con irrigidimenti, profili saldati, pile cave, sezioni
miste), con le proprietà e la costante di torsione.

## Come disegnare la sezione

* **Lamiere**: la linea media con lo spessore come **larghezza della polilinea**,
  oppure linee e archi su un layer che ha lo spessore nel nome (`t14`, `t=14`).
* **Sezioni piene**: polilinee chiuse, cerchi, campiture. I contorni contenuti in
  un altro sono fori; il layer dice il materiale (`cls`, `vuoto`, `armature` con
  i cerchi delle barre).
* Il disegno è la sezione **vista dal nodo iniziale verso il nodo finale** della
  trave: Y del disegno = y locale (verso l'alto), X = z locale. Assi, quote e
  testi si ignorano; le unità si leggono dal file.

## Che cosa calcola

* area, baricentro, inerzie, prodotto d'inerzia e assi principali;
* costante di Saint-Venant: per le lamiere **Bredt a più celle** sul grafo delle
  pareti (giunti a T riconosciuti), con la scelta di trascurare le celle degli
  irrigidimenti come si fa di solito; per le sezioni piene **Prandtl alle
  differenze finite**, con i fori e la stima dell'errore.

## Uso

Nella GUI di feagent: **Proprietà > Sezione da disegno DXF…** (anche dall'albero
delle sezioni), con anteprima, proprietà, J nelle due scelte sulle celle e layer
da includere. In Python:

```python
from feagent.sezioni_dxf import sezione_da_dxf

sez = sezione_da_dxf("cassone_stradale_CS1.dxf", "CS1", celle_minori=False)
print(sez.riepilogo())
sez.aggiungi_al_modello(model)
```

## Prova sul cassone stradale

Il cassone CS1 disegnato dalla tavola PS0093 a linee medie
([DXF](assets/dxf/cassone_stradale_CS1.dxf)) e reimportato dà, contro D-1 di IBDAS:

| Tipo | A | Iy | Iz | J (cella principale) |
|---|---|---|---|---|
| CS1 | −0,4 % | −2,0 % | −2,3 % | 0,9445 / 0,945 m⁴ (−0,05 %) |
| CS2 | −0,3 % | −1,8 % | −2,2 % | 1,0191 / 1,020 m⁴ (−0,08 %) |
| CS8 | −0,4 % | −1,3 % | −1,9 % | 1,2103 / 1,211 m⁴ (−0,06 %) |

Le verifiche automatiche della libreria confrontano Bredt, doppio T, cassone a due
celle, rettangolo pieno e tubo con le soluzioni note.
