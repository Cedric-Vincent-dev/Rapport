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





**3. Algèbre de Boole**

L’algèbre de Boole est un système mathématique qui manipule uniquement deux valeurs :  
**0 (faux)** et **1 (vrai)**.  
Elle est utilisée pour décrire le fonctionnement des circuits logiques, des processeurs et de tous les systèmes numériques.

Elle repose sur trois opérations fondamentales :

- **NON (¬A)**  
- **ET (A ∧ B)**  
- **OU (A ∨ B)**  

À partir de ces opérations, on peut définir toutes les autres (XOR, NAND, NOR…).





**3.1. Lois fondamentales**

Les lois fondamentales de l’algèbre de Boole décrivent le comportement de base des opérations logiques.  
Elles permettent de simplifier des expressions et de comprendre comment réagissent les circuits.

**Identité**
- \( A ∧ 1 = A \)  
  → Multiplier par 1 ne change rien : si on “exige vrai”, on ne modifie pas la condition.  
- \( A ∨ 0 = A \)  
  → Ajouter un faux ne change rien : un OU avec 0 laisse A intact.

**Nul**
- \( A ∧ 0 = 0 \)  
  → Une condition ET avec faux donne toujours faux.  
- \( A ∨ 1 = 1 \)  
  → Un OU avec vrai donne toujours vrai.

**Idempotence**
- \( A ∧ A = A \)  
  → Dire “A ET A” ne renforce pas la condition.  
- \( A ∨ A = A \)  
  → Dire “A OU A” ne change rien non plus.

**Complémentarité**
- \( A ∧ ¬A = 0 \)  
  → Une valeur et son contraire ne peuvent jamais être vraies en même temps.  
- \( A ∨ ¬A = 1 \)  
  → Une valeur ou son contraire est toujours vrai.

**Double négation**
- \( ¬(¬A) = A \)  
  → Inverser deux fois revient à la valeur initiale.




**3.2. Lois de commutation**

- \( A ∧ B = B ∧ A \)  
- \( A ∨ B = B ∨ A \)

Ces lois montrent que l’ordre des entrées n’a pas d’importance.



**3.3. Lois d’association**

- \( (A ∧ B) ∧ C = A ∧ (B ∧ C) \)  
- \( (A ∨ B) ∨ C = A ∨ (B ∨ C) \)

Elles permettent de regrouper les termes comme on veut.



**3.4. Lois de distribution**

- \( A ∧ (B ∨ C) = (A ∧ B) ∨ (A ∧ C) \)  
- \( A ∨ (B ∧ C) = (A ∨ B) ∧ (A ∨ C) \)

Ce sont les lois les plus importantes pour simplifier des expressions.



**3.5. Lois de De Morgan**

Elles permettent de transformer une expression en inversant les opérateurs :

- \( ¬(A ∧ B) = ¬A ∨ ¬B \)  
- \( ¬(A ∨ B) = ¬A ∧ ¬B \)

Ces lois sont essentielles en électronique, car elles permettent de remplacer des portes par d’autres (ex : remplacer un OU par un NAND).



**3.6. Simplification d’expressions logiques**

Quelques exemples classiques :

- \( A ∨ (A ∧ B) = A \)  
- \( A ∧ (A ∨ B) = A \)  
- \( A ∨ ¬A = 1 \)  
- \( A ∧ ¬A = 0 \)  
- \( (A ∧ B) ∨ (A ∧ ¬B) = A \)

Ces simplifications permettent de réduire le nombre de portes dans un circuit.



**3.7. Pourquoi l’algèbre de Boole est essentielle**

Elle permet de :

- simplifier des circuits logiques  
- réduire le nombre de portes (donc la consommation et le coût)  
- comprendre le fonctionnement interne des processeurs  
- analyser et concevoir des systèmes numériques  

C’est la base de toute l’électronique moderne.






**4. Conversions entre bases**

Les systèmes numériques utilisent différentes bases pour représenter les nombres :

- **binaire (base 2)** : utilisé par les circuits électroniques  
- **octal (base 8)** : utilisé historiquement pour compacter le binaire  
- **décimal (base 10)** : utilisé par les humains  
- **hexadécimal (base 16)** : utilisé pour représenter efficacement le binaire  

Comprendre les conversions entre ces bases est essentiel pour lire des adresses mémoire, analyser des instructions machines, ou interpréter des données binaires.



**4.1. Conversion binaire → décimal**

Méthode :  
Chaque bit représente une puissance de 2.

Exemple :  
\( 1011_2 \)

\[
1\cdot2^3 + 0\cdot2^2 + 1\cdot2^1 + 1\cdot2^0
= 8 + 0 + 2 + 1 = 11_{10}
\]



**4.2. Conversion décimal → binaire**

Méthode : divisions successives par 2.

Exemple :  
\( 25_{10} \)

- 25 ÷ 2 = 12 reste 1  
- 12 ÷ 2 = 6 reste 0  
- 6 ÷ 2 = 3 reste 0  
- 3 ÷ 2 = 1 reste 1  
- 1 ÷ 2 = 0 reste 1  

On lit les restes **de bas en haut** :

\[
25_{10} = 11001_2
\]



**4.3. Conversion binaire → hexadécimal**

Méthode :  
On regroupe les bits **par 4**, en partant de la droite.

Exemple :  
\( 11010110_2 \)

Groupes :  
1101 | 0110

- 1101 = D  
- 0110 = 6  

\[
11010110_2 = D6_{16}
\]



**4.4. Conversion hexadécimal → binaire**

Méthode :  
Chaque chiffre hexadécimal correspond à 4 bits.

Exemple :  
\( A3_{16} \)

- A = 10 = 1010  
- 3 = 3 = 0011  

\[
A3_{16} = 10100011_2
\]



**4.5. Conversion binaire → octal**

Méthode :  
On regroupe les bits **par 3**, en partant de la droite.

Exemple :  
\( 110101_2 \)

Groupes :  
110 | 101

- 110 = 6  
- 101 = 5  

\[
110101_2 = 65_8
\]



**4.6. Conversion octal → binaire**

Méthode :  
Chaque chiffre octal correspond à 3 bits.

Exemple :  
\( 57_8 \)

- 5 = 101  
- 7 = 111  

\[
57_8 = 101111_2
\]



**4.7. Conversion décimal → hexadécimal**

Méthode : divisions successives par 16.

Exemple :  
\( 254_{10} \)

- 254 ÷ 16 = 15 reste 14  
- 15 ÷ 16 = 0 reste 15  

Rappels :  
- 14 = E  
- 15 = F  

Lecture de bas en haut :

\[
254_{10} = FE_{16}
\]



**4.8. Conversion hexadécimal → décimal**

Méthode :  
Chaque chiffre hexadécimal représente une puissance de 16.

Exemple :  
\( 3B_{16} \)

\[
3\cdot16^1 + 11\cdot16^0 = 48 + 11 = 59_{10}
\]



**4.9. Travail manuscrit**
Insertion photos...







