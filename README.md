## Description

Vous trouverez dans ce Git les ressources nécéssaire à la FabrikJam de l'Edulab Rennes 2.
La "clavier" qui servira de manette est simulé par une carte "arduino micro pro". Suivez les étapes suivante pour savoir comment l'utiliser.

## Câblage

Chaque bouton se branche d'une part sur une **Pin de la Arduino** (voir Mapping des touches ci-dessous) et le **GND de la Arduino**.  
Aucune résistance externe nécessaire, branche simplement d'une des broche du bouton sur le GND et l'autre sur la Pin du bouton correpondant.
Attention, il n'y a qu'un seul voir 2 GND(s) sur ardunio, tu aura donc besoin d'ajouter des GND via une [breadboard (voir le tuto)](https://www.youtube.com/shorts/zwslONicr28).

## Mapping des touches
| N° de pin sur Arduino | Touche Correspondante | Code en arduino |
|-----|--------|-------------|
| `0 (RX)` | Barre espace | ` ` |
| `1 (TX)` | Touche Entrée / Return | `KEY_RETURN` |
| `2` | Shift gauche | `KEY_LEFT_SHIFT` |
| `3` | Lettre Z | `Z` |
| `4` | Lettre Q | `Q` |
| `5` | Lettre S | `S` |
| `6` | Lettre D | `D` |
| `7` | Lettre V | `V` |
| `8` | Lettre B | `B` |
| `9` | Lettre N | `N` |
| `10` | Lettre G | `G` |
| `11` | Lettre H | `H` |
| `12` | Lettre J | `J` |
| `13` | Touche Échap | `KEY_ESC` |

## Fonctionnement

- Les touches sont **maintenues** tant que le bouton est enfoncé (cela est configurable) 
- Un **anti-rebond logiciel de 20 ms** évite les faux déclenchements (cela est configurable) 

## Notes

- Compatible avec n'importe quel OS sans installation de driver (protocole HID natif)
> ⚠️ Les pins `0` et `1` partagent les lignes RX/TX de la communication série.  
> Ne pas utiliser le moniteur série en même temps que ces boutons.

## Modifier et téléverser le code
 
1. Télécharge et installe [Arduino IDE](https://www.arduino.cc/en/software) : le logiciel qui permet d'écrire et de charger du code sur ta carte
2. Copie le contenu de [Clavier_simulateur.ino](https://github.com/EdulabRennes2/FabrikJam/blob/main/Clavier_simulateur.ino) depuis ce Github et colle-le dans un nouveau sketch (remplace le code existant)
3. Branche l'Arduino en USB sur ton ordinateur
4. Dans le menu **Outils > Type de carte**, sélectionne **Arduino Micro** ou **Arduino Leonardo**
5. puis clique sur le bouton **Téléverser** (flèche →)
