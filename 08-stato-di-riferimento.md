---
layout: default
title: Stato di riferimento
nav_order: 9
---

# Stato di riferimento (ricerca della forma)

Nella **condizione di riferimento** IBDAS (PS0002 cap. 5) il ponte è finito e
aperto al traffico, sotto i soli permanenti, e la sua geometria è quella del
disegno di allineamento: C-1 più gli spostamenti E-1, piccoli (selle spostate di
1,62 m verso le campate laterali, impalcato in mezzeria −0,03 m).

Il modello feagent la ricostruisce così:

1. **Cavi e pendini**: lunghezza a riposo dal tiro E-3 nella geometria finale,
   `L0 = L_fin / (1 + N / EA)`.
2. **Impalcato**: geometria senza tensioni uguale a C-1 (allineamento di progetto).
3. **Torri**: controfreccia trovata per iterazione con rilassamento,
   `o(k+1) = o(k) + 0,6 (d_E1 − (o(k) + u(k)))`, con la statica non lineare
   (Newton) che parte dalla posizione raggiunta al passo precedente.
4. La controfreccia si salva per coordinate del nodo (non per numero), così
   resta valida se la numerazione del modello cambia.

La statica sotto i permanenti è non lineare (cavi e pendini), con i casi PP + PN.
