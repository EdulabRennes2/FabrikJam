## Description

Vous trouverez dans ce Git les ressources nécéssaire à la FabrikJam de l'Edulab Rennes 2.
La "clavier" qui servira de manette est simulé par une carte "arduino micro pro". Suivez les étapes suivante pour savoir comment l'utiliser.

## Câblage

Chaque bouton se branche entre le **pin correspondant** et le **GND**.  
Aucune résistance externe nécessaire, branche simplement d'une des broche du bouton sur le GND et l'autre sur la Pin du bouton correpondant.

## Mapping des touches
| Pin de la Arduino | Touche Correspondante | Code en arduino |
|-----|--------|-------------|
| `pin n°0 (RX)` | Barre espace | ` ` |
| `pin n°1 (TX)` | Touche Entrée / Return | `KEY_RETURN` |
| `pin n°2` | Shift gauche | `KEY_LEFT_SHIFT` |
| `pin n°3` | Lettre Z | `Z` |
| `pin n°4` | Lettre Q | `Q` |
| `pin n°5` | Lettre S | `S` |
| `pin n°6` | Lettre D | `D` |
| `pin n°7` | Lettre V | `V` |
| `pin n°8` | Lettre B | `B` |
| `pin n°9` | Lettre N | `N` |
| `pin n°10` | Lettre G | `G` |
| `pin n°11` | Lettre H | `H` |
| `pin n°12` | Lettre J | `J` |
| `pin n°13` | Touche Échap | `KEY_ESC` |

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
