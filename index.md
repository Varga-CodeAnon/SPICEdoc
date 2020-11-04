# Séance de TP1 - Spice, installation et prise en main

## Sommaire

- [Séance de TP1 - Spice, installation et prise en main](#séance-de-tp1---spice-installation-et-prise-en-main)
  - [Sommaire](#sommaire)
  - [Installation](#installation)
  - [Initialisation de l'espace de travail](#initialisation-de-lespace-de-travail)
  - [Structure de l'espace de travail](#structure-de-lespace-de-travail)
  - [Découverte des composants](#découverte-des-composants)
  - [Entrainement](#entrainement)
    - [Recopiez le schéma suivant](#recopiez-le-schéma-suivant)
    - [Simulation](#simulation)
    - [Bonus : Manipulations d'analyse et de comparaisons de courbes](#bonus--manipulations-danalyse-et-de-comparaisons-de-courbes)

## Installation

1. Désactivez tous les anti-virus, Windows Defender compris
2. Double-cliquez sur le fichier `Setup.exe`
3. Pendant l'installation, vous aurez le choix concernant les différents paquets à installer. Sélectionnez :
   - [x] Capture
   - [x] PSpice
   - [x] Layout
4. Une fois l'installation terminée, pensez à réactiver vos anti-virus

## Initialisation de l'espace de travail

1. Ouvrez le logiciel *Capture Lite Edition* en tapant `capture` dans la barre de recherche Cortana pour vous aider
2. Cliquez sur *File* > *New* > *Project...*
3. Choisissez un nom cours, cochez *Analog or Mixed A/D*, et sélectionnez une *Location*
   > La professeur a demandé de créer un dossier dédié projet spice sur notre bureau
4. Cochez *Create a blank project*

Une fenêtre blanche quadrillée par des points apparait alors.

## Structure de l'espace de travail

1. Cliquez sur *Project manager*, il s'agit de l'icone dessinant une arborescence, situé sur la première rangée, au bout à droite, juste avant le bouton point d'interrogation.
   
   L'arborescence du fichier s'affiche alors, vous pouvez appuyer sur le `+` situé juste à côté du nom de votre projet pour le développer

   > Notez qu'il est interdit (par la professeure) de faire plusieurs pages dans un même dossier `SCHEMATIC`

2. Créez une seconde schématique nommée TP1 à l'aide d'un clic droit sur votre dossier `.<projet>.dsn`
3. A l'aide d'un clic droit sur la shématique créée, ajoutez-y une page
4. Sauvegardez votre document
5. A l'aide d'un clic droit sur votre schématique TP1, cliquez sur *Make root* pour basculer cette schématique en haut de la hiérarchie
6. Double cliquez sur la page de votre schématique TP1 : vous retournez sur l'affichage d'accueil, une fenêtre blanche quadrillée par des points, avec comme nom de fenêtre **[/ - (TP1 : PAGE1)]**

## Découverte des composants

> Selon les configurations et les résolutiuon d'écran, l'organisation des barres d'outils du logiciel peuvent changer. Ici, sera désignée par l'appelation *"barre d'outils de droite"* la barre d'icones commençant par un pointeur de souris noir, et finissant par un A en majuscule

1. Sur la barre d'outils de droite, cliquez sur le deuxième icone qui ressemble à une prise et/ou a un composant ET logique
2. Dans la nouvelle fenêtre, cliquez sur *Add Library*
3. Faites un `CTRL+A` pour sélectionner l'intégralité des librairies (fichier `.olb`), et cliquez sur *Ouvrir*
Sur le bandeau de droite, cliqué sur l'icone qui ressemble à une prise (le second)
4. Dans la partie *Part List*, sélectionnez un composant au choix.
   
   Vous pouvez alors déposer un ou plusieurs exemplaires de ces composants sur la feuille. Appuyez sur `Echap` pour relacher le composant en main.
   
   > Notez qu'on peut tout changer dans le composant, en cliquant sur les différentes parties de ce dernier. On peut aussi changer son orientation à l'aide d'un clic droit.

   > Double-cliquer sur le composant permet d'afficher les informations du composant (pour fermer cette sous-fenêtre, cliquez sur la croix **sous** la croix principale)
5. Placez deux composants sur la feuille (exemple : deux résistances R)
6. Pour connecter ces deux résistances, cliquer sur l'icone "fil fin" de la barre d'outils de droite (**attention pas l'icone fil épais qui correspond à un bus, l'icone fil fin**), puis cliquez sur les deux bouts à relier.
   
   > Notez qu'une fois relié, si de gros points roses apparaissent, c'est que les composants ont été mal relié (circuit ouvert)
7. Le *ground* n'apparait pas par défaut. Pour le configurer, cliquez sur l'icone *GND* de la barre d'outils de droite > *Add Library* > *Dossier PSpice* > `source.olb` > *Ouvrir*
8. Sélectionnez ensuite dans la fenêtre *Libraries* la lib `source.old`, puis sélectionnez `0`
   
   Vous pouvez désormais placer des masses sur votre feuille.

## Entrainement 
### Recopiez le schéma suivant

![Schéma du TP1](https://github.com/Varga-CodeAnon/SPICEdoc/blob/main/src/schema.png)

L'idée est de recréer ce schéma. Pour se faire :
1. Dans un premier temps, placez les composants comme vu précédemment sans vous soucier de leur valeur (les composants sont `VAC/SOURCE`, `R`, `C` et `0` dans le menu *ground*).
   > Pensez à les orienter correctement
2. Reliez les composants
3. En double cliquant sur les composants, éditez les noms et les valeurs pour les faire correspondre scrupuleusement au schéma
4. Ajouter deux *alias* IN et OUT sur la ligne de par et d'autre de la résistance
   
   Pour se faire, cliquez sur le bouton `N1` de la barre d'outils de droite, nommez l'alias *IN*, puis placez le sur la ligne. Relachez l'alias avec la touche échap, puis recommencez pour l'alias *OUT*

> Pensez à sauvegarder régulièrement

### Simulation

Pour réaliser une simulation :

1. Dans la seconde barre d'outils supérieure, juste a côté de la barre de menu de sélection grisée, cliquez sur l'icone représentant une fenêtre a bandeau bleu avec une petite étoile dans le coin supérieur gauche, et intitulé *New Simulation*
2. Donnez un nom court, laissez *none* dans *Inherit*, puis cliquez sur *Create*
   
   A ce moment là, le texte `TP1-<nom choisi>` apparait à gauche de l'icone *New Simulation* dans le menu déroulant *Active Profile*
3. Éditez les propriétés de la simulation dans la fenêtre pop-up qui vient de s'ouvrir (ou en cliquant sur le bouton *Edit Simulation Settings* directement à droite du bouton *New Simulatiuon*)
   
   Une fenêtre pop-up s'ouvre alors
4. Dans cette fenêtre
   - Sélectionnez *AC/sweep noise*
   - [x] Cochez *General Settings*
   - [x] *Logarithmic*
   - `10` dans *Start Frequency*
   - `100k` dans *End Frequency*
   - `1000` dans *Points/Decade*
   - Enfin, cliquez sur *OK*

5. Dans la barre d'état, cliquez sur le menu *PSpice* > *Create Netlist*. Si **tout est bon**, alors **rien ne va s'afficher**. C'est normal
6. De la même manière, cliquez sur *View Netlist*. La sortie devrait être la même que celle-ci (l'ordre des lignes importe peu):

   ```
   * source STRI
   R_R1         IN OUT  10K  
   C_C1         0 OUT  10n  
   V_V1         IN 0 DC 0Vdc AC 1Vac 
   ```
7. Fermez cette sous-fenêtre, puis cliquez sur le bouton *Run PSpice* désigné par un icone "Play"

   Une fenêtre pop-up s'ouvre alors, nous affichant un graphe de fréquence vide.
8. Pour remplir ce graphe, cliquez sur le bouton *Add Trace* (désigné par une courbe en dent de scie)
9. Dans la nouvelle fenêtre, section *Trace Expression*, copiez l'expression suivante, puis cliquez sur *OK*
    ```
    db(V(OUT)/V(IN))
    ```

On obtient alors le résultat final suivant :

![Courbe finale](https://github.com/Varga-CodeAnon/SPICEdoc/blob/main/src/courbe.png)

### Bonus : Manipulations d'analyse et de comparaisons de courbes

- L'icone *Toggle cursor* représenté par un curseur sur une courbe permet, en laissant le clic gauche de la souris enfoncé, de faire apparaitre une fenêtre caractérisant les différents points survolés de notre courbe
- Il est possible de double cliquer sur les axes pour les éditer
- Dans le menu *Plot*, on peut rajouter un axe
  - Rajoutons par exemple un axe Y
  - Deux chevrons `>>` désignent alors l'axe sélectionné
  - Sélectionnez donc l'axe nouvellement créé, ajoutez une trace de la courbe `V(out)` comme vu précédemment, vous pouvez alors comparer ces deux courbes
