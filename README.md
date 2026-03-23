## Description

Vous trouverez dans ce Git les ressources nécéssaire à la FabrikJam de l'Edulab Rennes 2.
La "clavier" qui servira de manette est simulé par une carte "arduino micro pro". Voici comment cette dernière réagit :


## Câblage

Chaque bouton se branche entre le **pin correspondant** et le **GND**.  
Aucune résistance externe nécessaire, branche simplement d'une des broche du bouton sur le GND et l'autre sur la Pin du bouton correpondant.


## Mapping des touches

| Pin | Touche | Description |
|-----|--------|-------------|
| `0` | `Espace` | Barre espace |
| `1` | `Entrée` | Touche Entrée / Return |
| `2` | `Maj` | Shift gauche |
| `3` | `Z` | Z|
| `4` | `Q` | Q |
| `5` | `S` | S |
| `6` | `D` | D |
| `7` | `V` | V |
| `8` | `B` | B |
| `9` | `N` | N |
| `10` | `G` | G |
| `11` | `H` | H |
| `12` | `J` | J |
| `13` | `Échap` | Touche Esc |

## Fonctionnement

- Les touches sont **maintenues** tant que le bouton est enfoncé (cela est configurable) 
- Un **anti-rebond logiciel de 20 ms** évite les faux déclenchements (cela est configurable) 

## Notes

- Compatible avec n'importe quel OS sans installation de driver (protocole HID natif)
> ⚠️ Les pins `0` et `1` partagent les lignes RX/TX de la communication série.  
> Ne pas utiliser le moniteur série en même temps que ces boutons.

## Modifier et téléverser le code
 
1. Télécharge et installe l'[IDE Arduino](https://www.arduino.cc/en/software)
2. Copie le contenu de `clavier_arduino.ino` depuis ce Github et colle-le dans un nouveau sketch (le code existant peut être entièrement remplacé)
3. Dans le menu **Outils > Type de carte**, sélectionne **Arduino Micro** ou **Arduino Leonardo**
4. Branche l'Arduino en USB, puis clique sur le bouton **Téléverser** (flèche →)
