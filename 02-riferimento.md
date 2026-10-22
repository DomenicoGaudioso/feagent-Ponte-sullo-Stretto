---
layout: default
title: Sistema di riferimento
nav_order: 3
---

# Sistema di riferimento

## IBDAS

IBDAS usa un sistema **sinistrorso** `(s, y, z)` (PS0002 App. B, PS0003 fig. 2.9):

* `s` lungo l'asse del ponte, positivo verso la Calabria (`s = 0` in mezzeria,
  torri a `s = ±1650 m`);
* `z` verticale verso l'alto (quote sul livello del mare);
* `y` trasversale, con il cassone stradale **Ovest** a `y = −18,55 m`.

Gli assi locali delle travi `(Se, Ye, Ze)` sono dello stesso tipo: per i cassoni
`Ye` segue `y`, quindi in D-1 l'ingombro `ye−` del cassone Ovest è il lato esterno.

## feagent

Nel modello feagent il sistema è destrorso con **Z verso l'alto**:

| feagent | IBDAS |
|---|---|
| x | s |
| y | −y |
| z | z |

L'Ovest IBDAS (`y < 0`) è quindi `y > 0` in feagent. Le travi orizzontali hanno
`ref_vector = (0, 0, 1)` (asse y locale verso l'alto), quelle verticali
`(1, 0, 0)`. Per i cassoni stradali, che non sono simmetrici, il vettore di
riferimento è ruotato dell'angolo degli assi principali (circa 1,5°), così il
prodotto d'inerzia di D-1 resta nel modello.

## Convenzioni delle grandezze di D-1

* `Iy = ∫ z² dA` (flessione nel piano verticale), `Iz = ∫ y² dA`;
* `Iyz = + ∫ y z dA` (convenzione a prodotto): con la sezione della tavola e il
  naso sul lato esterno il valore torna su tutti i tipi di concio (+0,216 contro
  +0,214 m⁴ per CS1); la convenzione a tensore darebbe il segno opposto;
* `Iv` è la costante di torsione di Saint-Venant;
* `g` è il peso per metro del modello geometrico (acciaio a 77 kN/m³; per i
  cassoni stradali comprende la pavimentazione, 1 kN/m² su 11,95 m).
