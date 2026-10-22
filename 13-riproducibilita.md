---
layout: default
title: Riproducibilità
nav_order: 14
---

# Riproducibilità

Il modello si costruisce con gli script della cartella `scripts/` della
libreria [feagent](https://github.com/DomenicoGaudioso/feagent):

| Script | Ruolo |
|---|---|
| `messina_ibdas_tables.py` | lettore delle appendici di PS0002 (C-1, C-2, C-3, D-1, D-2, E-1, E-3, F-1, F-2) |
| `messina_sections.py` | sezioni: cassone stradale dalla tavola PS0093, ferroviario, traversi, torri, parti secondarie |
| `messina_ibdas_parts.py` | parti secondarie da C-1, C-2, C-3, D-1 |
| `messina_ibdas_model.py` | modello completo, carichi, stato di riferimento, analisi e confronto con IBDAS, file per la GUI |
| `messina_azioni_variabili.py` | carichi mobili stradali e ferroviari (QA, QR), vento statico, riscontro con PS0005, verifica non lineare |
| `messina_figure_doc.py` | figure di questa documentazione dal file Excel della GUI |

I documenti IBDAS (testo estratto dei PDF) si cercano in
`_lavoro/varie/ponte_stretto_messina_docs/mase_modello_ibdas` accanto alla cartella
di feagent, oppure nella cartella indicata dalla variabile `MESSINA_IBDAS_DOCS`.

```bash
python scripts/messina_sections.py      # taratura delle sezioni e tavola
python scripts/messina_ibdas_model.py   # stato di riferimento, analisi, confronto, file per la GUI
python scripts/messina_azioni_variabili.py --nonlineare   # carichi mobili e vento
python scripts/messina_figure_doc.py    # figure
```

Il file per la GUI è `examples/ponte_stretto_messina/ponte_stretto_messina.xlsx`:
si apre con `feagent-gui` (File > Apri) e contiene nodi, travi a sezione variabile
con le sezioni composte (fogli `Section` e `SectionPart`), cavi e pendini con il tiro,
molle, vincoli e i casi di carico PP e PN.

## Dati principali in uscita

* `messina_out/confronto_passi.json`: confronto prima/dopo e con IBDAS;
* `messina_out/stato_riferimento.json`: controfreccia delle torri, per coordinate;
* `messina_out/azioni_variabili.json`: carichi mobili, vento, riscontro con PS0005;
* `messina_out/sezioni_tarate.json`: cache delle tarature delle sezioni;
* DXF del cassone stradale (CS1, CS2, CS8) in [assets/dxf](https://github.com/DomenicoGaudioso/feagent-Ponte-sullo-Stretto/tree/main/assets/dxf).
