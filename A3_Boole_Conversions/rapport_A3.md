**Annexe 3 – Algèbre de Boole, tables de vérité et conversions de bases**

1. **Introduction**

Cette annexe a pour objectif de présenter les notions fondamentales liées à l’algèbre de Boole, aux portes logiques et aux conversions entre différentes bases numériques (binaire, octal, décimal, hexadécimal).

Ces notions sont centrales en informatique et en électronique numérique, car elles permettent de :
- modéliser le fonctionnement des circuits logiques (portes ET, OU, NON, XOR, NAND, etc.) ;
- comprendre le comportement des processeurs au niveau binaire ;
- manipuler et interpréter les données représentées dans différentes bases ;
- poser des bases solides pour la conception de systèmes numériques plus complexes.

Dans ce rapport, je présente :
- les principales portes logiques, leurs symboles, leurs tables de vérité et leur interprétation ;
- les règles de base de l’algèbre de Boole ;
- la méthode de conversion entre les bases binaire, octale, décimale et hexadécimale ;
- des exemples de conversions réalisés à la main, dont les photos seront ajoutées en annexe.




2. **Portes logiques et tables de vérité**

Les portes logiques sont les blocs fondamentaux des circuits numériques.  
Elles manipulent des valeurs binaires (0 ou 1) et permettent de construire des systèmes plus complexes : additionneurs, multiplexeurs, processeurs, etc.

Chaque porte possède :

- un **symbole** utilisé en électronique  
- une **fonction logique**  
- une **table de vérité**  
- une **interprétation** (comment elle réagit aux entrées)



**2.1. Porte NON (NOT)**

La porte NON inverse la valeur d’entrée.

| Entrée A | Sortie ¬A |
|---------|-----------|
| 0       | 1         |
| 1       | 0         |

**Interprétation :**  
Si A vaut 0, la sortie vaut 1.  
Si A vaut 1, la sortie vaut 0.



**2.2. Porte ET (AND)**

La sortie vaut 1 **uniquement si toutes les entrées valent 1**.

| A | B | A ∧ B |
|---|---|--------|
| 0 | 0 | 0      |
| 0 | 1 | 0      |
| 1 | 0 | 0      |
| 1 | 1 | 1      |

**Interprétation :**  
C’est une condition stricte : les deux doivent être vrais.



**2.3. Porte OU (OR)**

La sortie vaut 1 si **au moins une entrée vaut 1**.

| A | B | A ∨ B |
|---|---|--------|
| 0 | 0 | 0      |
| 0 | 1 | 1      |
| 1 | 0 | 1      |
| 1 | 1 | 1      |

**Interprétation :**  
C’est une condition permissive : il suffit qu’un seul soit vrai.


**2.4. Porte OU Exclusif (XOR)**

La sortie vaut 1 **si les entrées sont différentes**.

| A | B | A ⊕ B |
|---|---|--------|
| 0 | 0 | 0      |
| 0 | 1 | 1      |
| 1 | 0 | 1      |
| 1 | 1 | 0      |

**Interprétation :**  
C’est le test “A différent de B”.


**2.5. Porte NAND**

C’est l’inverse de la porte ET.

| A | B | NAND |
|---|---|--------|
| 0 | 0 | 1      |
| 0 | 1 | 1      |
| 1 | 0 | 1      |
| 1 | 1 | 0      |

**Interprétation :**  
Elle vaut 0 uniquement si A = 1 et B = 1.


**2.6. Porte NOR**

C’est l’inverse de la porte OU.

| A | B | NOR |
|---|---|-------|
| 0 | 0 | 1     |
| 0 | 1 | 0     |
| 1 | 0 | 0     |
| 1 | 1 | 0     |

**Interprétation :**  
Elle vaut 1 uniquement si aucune entrée n’est vraie.



**2.7. Remarque importante**

Les portes **NAND** et **NOR** sont dites *fonctionnellement complètes* :  
on peut construire **toutes les autres portes** uniquement avec NAND ou uniquement avec NOR.
C’est un concept fondamental en électronique numérique.

