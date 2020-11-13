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
- [Séance de TP2 & 3 - Impédence & analyse de courbe](#séance-de-tp2--3---impédence--analyse-de-courbe)
  - [Initialisation](#initialisation)
  - [Réalisation du schéma du circuit](#réalisation-du-schéma-du-circuit)
  - [Simulation](#simulation-1)
  - [Étude de courbe et autres calculs](#étude-de-courbe-et-autres-calculs)
    - [S'éviter le curseur pour les calculs graphique](#séviter-le-curseur-pour-les-calculs-graphique)
  - [Variation des composants](#variation-des-composants)

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

![Schéma du TP1](https://raw.githubusercontent.com/Varga-CodeAnon/SPICEdoc/main/src/schema.png)

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

![Courbe finale](https://raw.githubusercontent.com/Varga-CodeAnon/SPICEdoc/main/src/courbe.png)

### Bonus : Manipulations d'analyse et de comparaisons de courbes

- L'icone *Toggle cursor* représenté par un curseur sur une courbe permet, en laissant le clic gauche de la souris enfoncé, de faire apparaitre une fenêtre caractérisant les différents points survolés de notre courbe
- Il est possible de double cliquer sur les axes pour les éditer
- Dans le menu *Plot*, on peut rajouter un axe
  - Rajoutons par exemple un axe Y
  - Deux chevrons `>>` désignent alors l'axe sélectionné
  - Sélectionnez donc l'axe nouvellement créé, ajoutez une trace de la courbe `V(out)` comme vu précédemment, vous pouvez alors comparer ces deux courbes

# Séance de TP2 & 3 - Impédence & analyse de courbe

## Initialisation
1. Ouvrez le *Project Manager* pour afficher l'arborescence du projet
2. Créez une shématique TP2, contenant une unique page. Vous placerez la schématique en *root* après avoir sauvegardé. Enfin, double cliquez sur la page pour commencer à travailler

## Réalisation du schéma du circuit

De la même manière que dans le chapitre précédent, réalisez le schéma suivant :

![Schéma n°2](https://raw.githubusercontent.com/Varga-CodeAnon/SPICEdoc/main/src/exo2.png)

> Encore une fois, faites en sortes que votre schéma soit identique, y compris alias, noms de composants et valeurs !

> Note : Tous les composants (sauf les masses) sont issues de la librairie *ANALOG*

## Simulation
De la même manière que dans le chapitre précédent, réalisez la simulation du schéma précédent avec comme options :
   - Sélectionnez *AC/sweep noise*
   - [x] Cochez *General Settings*
   - [x] *Linear*
   - `10` dans *Start Frequency*
   - `500` dans *End Frequency*
   - `1000` dans *Points/Decade*
   - Enfin, cliquez sur *OK*

On obtient la *View List* suivante :
   ```
   * source STRI
   V_V1         IN 0 DC 0Vdc AC 5Vac
   L_L1         N000670 OUT 1
   C_C1         0 OUT  470n 
   R_R1         IN N000670  470  
   ```

Tracez alors la courbe suivante modélisant l'intensité du courant de notre schéma :

Ce sera cette courbe que nous étudierons par la suite.
![Courbe d'intensité](https://raw.githubusercontent.com/Varga-CodeAnon/SPICEdoc/main/src/intensité.png)


## Étude de courbe et autres calculs 

![Schéma](https://raw.githubusercontent.com/Varga-CodeAnon/SPICEdoc/main/src/courbe2.png)

1. Calculez la fréquence f0
   > Objectif : Déterminer la fréquence à laquelle nous avons un maximum d'intensité

   *Manière algébrique :*
   - On sait que le nombre complexe Z vaut R + j(Lw-1/Cw)
   
     Ici, on simplifiera l'impédence des composants en les nommant XL et XC.
   - Le module de Z, ou l'impédence Z, vaut alors sqrt(R^2+(XL-XC)^2)
   - A la résonnance, Z ne dépend plus de la fréquence, I et V sont en phase. On a alors Z qui devient résistive : Z = R, ce qui implique XL=XC
   - Or jLw0=1/(jCw0) => w0^2 = 1/LC => w0 = 1/(sqrt(LC))
   - Or w0 = 2pif0
   - Donc f0 = 1/(2pi*sqrt(LC))
   
   En intégrant les valeurs numériques, on obtient alors environ 232Hz

   *Manière graphique :* 
   - Avec l'option *Toggle cursor* et un clic driot maintenu, parcourez la courbe jusqu'à son maximum, et vérifiez alors la valeur de la fréquence f0 pour l'intensité maximale, soit 10mA

2. Calculez le coefficient de qualité (appelé aussi coefficient de surintensité)
   > Objectif : Déterminer le maximum de la courbe. Ces données nous permettront de calculer la puissance

   *Manière algébrique :*
   - Le coefficient de qualité Q vaut f0/delta(f0) 
     > Il peut aussi valoir Lw0/R ; 1/Rcw0 ; ou encore (1/R)*(sqrt(L/C)), pratique pour éliminer le w0
   - Or par définition, delta(f0) représente la bande de fréquence qui correspond à -3dB du max de la courbe (rappel : -3dB correspond à 0,707, soit 1/sqrt(2))
   - Autrement dit, il s'agit de la différence d'abscisses entre les deux points de la courbe aux coordonnées Imax/sqrt(2) (cela correspond à la double flèche violette du schéma ci-dessus)
   - Une fois le delta calculé, il suffit alors de diviser la valeur de f(0) déterminée précédemment pour obtenir la valeur de Q

   > Q pouvait aussi se calculer 
   En intégrant les valeurs numérique, on trouve que pour la fréquence f(0), Q = 3,1

   *Manière graphique pour le delta(f0):*
   - 10mA/sqrt(2) = 7,52
   - Relevez les valeurs de fréquences aux deux points d'intensité 7,52mA et soustrayez-les, ce qui revient à trouver aux alentours de 75Hz

### S'éviter le curseur pour les calculs graphique
1. Allez dans le menu *Trace*, *Eval-Functions*
2. Pour trouver f(0), cliquez sur la troisième ligne de la colonne de droite : *Center frequency*
   1. Ensuite, dans la colonne de gauche, cliquez sur I(R1). 
   2. Rajoutez `,1` dans la paranthèse de sortes à ce que vous ayez la fonction suivante : `CenterFreq(I(R1),1)`, puis appuyez sur Ok
   3. On obtient alors la valeur dans une fenêtre pop-up
3. Pour trouver le delta(f0), même procédé de manière à obtenir l'équation suivante : `BPBW(I(R1),3)`

## Variation des composants

Dans le schéma, tout est stable : on appelle cela le cas nominal.Cependant, en conditions réelles, il y a un écart à l’idéalité.  Par exemple, j’envoie un satellite dans l'espace. Une face du satellite vers le soleil, l’autre à l’ombre. La température varie. Donc il faut observer les conséquences de ces éléments sur le composant. 

C’est pour cela que l’on va modifier la valeur des élements, notamment R et L (et donc Q)

1. Pour R, modifiez la valeur `470` en `{Rvar}`
   > Note : les accolades sont importantes !
2. Allez dans le menu permettant d'ajouter un nouveau composant, cliquez sur *SPECIAL* dans les librairies, puis sur *PARAM* dans le menu déroulant *Part List*
3. En double-cliquant sur le composant *PARAM* placé, on arrive sur une nouvelle sous-fenêtre. Pour créer une nouvelle variable, cliquez sur *New Column*, et nommez la Rvar
4. Inscrivez-y la valeur 470
5. Faites un clic droit sur la colonne > *Display* > *Name and value*
6. Revenuez sur la valeur principale, on voit alors s'afficher *Rvar = 470* dans le composant paramètre
7. Pour faire varier la courbe associé à ce circuit, allez dans le menu *PSpice* > *Edit Simulation Profile*
8. [x] Cochez *Parametric Sweep*
9. Dans la fenêtre *Sweep type*, rentrez les valeurs suivantes
   - [x] Value list : `47 100 470`
   - Start value : 100
   - End value : 600
   - Increment : 100
   - [x] Global parameter : Rvar
10. Appuyez sur *Ok*, puis lancez la simulation
11. Une fenêtre pop-up s'affiche donc, désignant 3 courbes
    
    Vous devriez alors voir les courbes suivantes :

    ![3 courbes](https://raw.githubusercontent.com/Varga-CodeAnon/SPICEdoc/main/src/3courbes.png)

    > N'hésitez pas à changer les valeurs des axes pour zoomer/dézoomer les courbes (par exemple 150Hz-300Hz sur l'axe des abscisses)

    > Pour connaitre les paramètres que représentent la courbe, faites un clic droit dessus > *Information*. Le paramètre est alors donné par la ligne *Step param Rvar = 47*

    > Supposons vous ne voulez tracer que la courbe 47 Ohm, alors écrivez dans la fenêtre Trace Plot la formule suivante `I(R1)@1`, ou 1 représente la première valeur spécifiée dans les options de simulation (donc ici 47)

12. Refaites la même opération, en rajoutant cette fois le paramètre `{Lvar}`, de sortes à obtenir les paramètres suivants :
    ```
    PARAMETERS :
    Rvar = 470
    Lvar = 1
    ```
13. Dans la *Value List*, mettez les valeurs `1 2 3`
14. Lancez la simulation

    Vous obtenez alors les courbes suivantes :

    ![3 courbes numero 2](https://raw.githubusercontent.com/Varga-CodeAnon/SPICEdoc/main/src/3courbes2.png)