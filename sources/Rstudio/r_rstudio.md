---
title: Statistique avec R - Premiers pas
subtitle: R et R studio
author: Mathieu Emily, Marie-Pierre Etienne, Magalie Houée-Bigot, Fran\c{c}ois Husson 
institute: "https://github.com/MarieEtienne/FormationContinueR"
date: "Mars 2021"
csl: "../resources/apa-no-doi-no-issue.csl"
output:
   xaringan::moon_reader:
    css: [  'metropolis',  '../../courses_tools/resources/mpe_pres.css']
    lib_dir: libs
    nature:
      ratio: 16:10
      highlightStyle: github
      highlightLines: true
      countIncrementalSlides: false
      beforeInit: '../../courses_tools/resources/collapseoutput.js'
    includes:
      after_body: '../../courses_tools/resources/insert-logo.html'
fontsize: 11pt
params:
  child_path: ''
---









# Préambule

Ce cours s'inspire grandement de 


- *R for Data science*, Wickham and Grolemund [WG16], [https://r4ds.had.co.nz/](https://r4ds.had.co.nz/)

- *R pour la statistique et la science des données*,  Cornillon, Guyader, Husson, et al. [Cor+18], [https://r-stat-sc-donnees.github.io/](https://r-stat-sc-donnees.github.io/)

- *Cours de Julien Chiquet*
[https://github.com/jchiquet/CourseAdvancedR](https://github.com/jchiquet/CourseAdvancedR)




<img src="../../resources/figs/r4ds_cover.jpg" title="plot of chunk r4ds" alt="plot of chunk r4ds" width="10%" /><img src="../../resources/figs/R_stat_sc_donnees.png" title="plot of chunk r4ds" alt="plot of chunk r4ds" width="10%" />







---
name: ecosys
# L'écosystème R


---
template: ecosys
## Qu'appelle-t-on R?

R est à la fois un **logiciel**, un **langage** et un **environnement** informatique dédié au calcul et à l'analyse statistique.

R est un projet open source (projet GNU)

R est un logiciel multi-plateforme (Linux, Mac, Windows)


---
template: ecosys

## La structure R

R est composé d'un socle (base) et de bibliothèques de fonctions thématiques regroupées sous le nom de **package**

Il est possible de connecter R avec d'autres langages : C, Fortran, Java, Javascript, Python...

Il est possible d'appeler des fonctions R depuis Matlab, Excel, SAS, SPSS...

Des connectiques pour tous les types de bases de données : RODBC, RMySQL,ROracle, RJDBC, RMongo...


---
template: ecosys

## Les packages 

R a été pensé comme un **langage ouvert et modulaire**.  

L'ensemble des fonctionnalités de R est inclus dans des **packages**.

A l'installation de R, les packages de base sont déjà installés dans votre environnement 

R permet à n'importe qui de proposer et déposer son package sur le serveur du **CRAN**. De nombreux chercheurs utilisent R donc les nouvelles méthodes sont implémentées. 

Aujourd'hui, $13903$ packages sont disponibles [https://cran.r-project.org/web/packages/](https://cran.r-project.org/web/packages/) 

Si vous avez besoin d'une fonctionnalité spécifique, vous pouvez avoir besoin d'installer un package!



---
template: ecosys

## R histoire

L'ère pré-R

- 1970's développement de S au Bell labs
- 1980's développement de S-PLUS au AT\&T. Lab

Les débuts

- 1993 développement de R sur le modèle de S par Robert Gentleman et Ross Ihaka au département de statistique de l'université d'Auckland.
- 1995 dépôts des codes sources sous licence GNU/GPL

Le succès

- 1997 élargissement du groupe
- 2002 la fondation R dépose ses statuts sous la présidence de Gentleman et Ihaka

Développement entièrement bénévole

- "R development core team" (12aine de personnes)
- Participation de nombreux chercheurs ($\approx$ 13900 packages)

---
template: ecosys

## La communauté R

La page web de la **fondation** R

- les statuts, des liens, des références.
- [http://www.r-project.org/](http://www.r-project.org/)

La page web du **CRAN** (Comprehensive R Arxiv Network)

- binaires d'installation, packages, documentations, . . .
- [http://cran.r-project.org/](http://cran.r-project.org/)

La **conférence** annuelle des utilisateurs de R :

- l'édition 2019 se déroule début juillet en France (Toulouse)
- l'édition 2009 s'est déroulée à Agrocampus Ouest 

Depuis 2012, il existe une version française : "les rencontres R".

- l'édition 2018 s'est déroulée à Agrocampus Ouest 

The **R journal** propose des articles sur :

- de nouvelles extensions, des applications, des actualités.
- [http://journal.r-project.org/](http://journal.r-project.org/)



---
name: user
# Utiliser R 

---
template: user
## Installer R

Allez sur [http://cran.r-project.org/](http://cran.r-project.org/) et choisissez votre système d'exploitation


<img src="../../resources/figs/cran.png" title="plot of chunk cran_img" alt="plot of chunk cran_img" width="60%" style="display: block; margin: auto;" />
---
template: user
##  Lancement de R

Cliquer sur l'icône <img src =../../courses_tools/resources/common_figs/R.ico alt = "R logo" width = "32" height = "32"> pour lancer R, une fenêtre, appelée **Console** s'ouvre : 

--

<img src="../../resources/figs/Start_consoleR.jpg" title="plot of chunk start_r" alt="plot of chunk start_r" width="40%" style="display: block; margin: auto;" />

--

R attend une instruction : ceci est indiqué par > en début de ligne. Cette instruction doit être validée par **Entrée** pour être exécutée.

- instruction correcte, R exécute et redonne la main >
- instruction incomplète, R retourne $+$, il faut alors compléter l'instruction ou sortir avec **Echap**


---
template: user
## R et RStudio

### R 

- Element de base : c'est le coeur de l'outil 
- Utilisation "bas niveau"
- Convivialité réduite 

### RStudio

RStudio est un IDE (integrated development environment) pour R.

Principaux avantages de convivialité:

- Editeur de code intégré
- Débogage
- Outil de visualisation de l'environnement de travail



---
name: userstudio
# Utiliser R dans l'IDE RStudio

---
template: userstudio
## Installer RStudio

Allez sur [https://www.rstudio.com/products/RStudio/](https://www.rstudio.com/products/RStudio/)

<img src="../../resources/figs/RStudio.png" title="plot of chunk rstudio_img" alt="plot of chunk rstudio_img" width="60%" style="display: block; margin: auto;" />

---
template: userstudio
## Lancement de RStudio 

Cliquer sur l'icône <img src =../../courses_tools/resources/common_figs/RStudioLogo.png alt = "RStudio logo" width = "32" height = "32">  pour lancer RStudio

<img src="../../resources/figs/RStudioStart.png" title="plot of chunk rstudio_start" alt="plot of chunk rstudio_start" width="60%" style="display: block; margin: auto;" />

---
template: userstudio
## Premier contact avec RStudio 

RStudio est divisé en 3 (4) quadrants : 

- Console
- Espace de travail, historique, importation, ...
- Visualisation (graphiques), aide, ...
- Editeur de texte, de codes, ... (4ème quadrant à insérer <img src =../../resources/figs/insertEditor.png alt = "insert script" width = "40" height ="20" > ).

--
### Console 

La console  permet de faire des calculs


```r
1+1
```

```
## [1] 2
```

--
Le résultat est affiché sauf si il est stocké dans une variable


```r
a <- 1+1
```


```r
a + 3
```

```
## [1] 5
```


---
template: userstudio

### Environnement de travail 


- L'environnement liste résultats des calculs stockés dans des **variables** ou **objets** 


```r
c<-154*36
c
```

```
## [1] 5544
```


<img src="../../resources/figs/RStudio_Environ2.png" title="plot of chunk rstudio_env" alt="plot of chunk rstudio_env" width="60%" style="display: block; margin: auto;" />

---
template: userstudio
## Bonnes pratiques

### Faire un script

<img src="../../resources/figs/RStudio_Script1.png" title="plot of chunk rstudio_script1" alt="plot of chunk rstudio_script1" width="60%" style="display: block; margin: auto;" />

--

Le code se tape dans la fenêtre de script et s’exécute directement.  

- \# pour insérer des commentaires 
- **Shift+Alt+k** pour les raccourcis clavier

---
template: userstudio
## Bonnes pratiques

### Faire un script


<img src="../../resources/figs/RStudio_Script2.png" title="plot of chunk rstudio_script2" alt="plot of chunk rstudio_script2" width="60%" style="display: block; margin: auto;" />

--

- Possibilité de sauvegarder le script (.R), 
- Possibilité de sauvegarder l'environnement de travail (.RData).


---
template: userstudio
## Bonnes pratiques
### Les Projets dans RStudio

RStudio dispose d'une fonctionnalité très pratique pour organiser son travail en différents projets.

L’idée est de réunir tous les fichiers, documents (données, scripts, ...) relatifs à un même projet dans un répertoire dédié.

--

#### Les avantages

- Facilite l'accès aux fichiers de données à importer : le répertoire de travail de R est défini comme étant le répertoire du projet
- L'onglet Files de l'interface permet de naviguer dans les fichiers du projet
- Les objets créés (et sauvegardés dans le fichier .Rdata) lors d’une précédente séance de travail sont chargés en mémoire
- Les scripts ouverts lors d’une précédente séance de travail sont automatiquement ouverts


Lorsque l’on ouvre un projet RStudio, on revient à l’état de notre projet tel qu’il était la dernière fois que l’on a travaillé dessus. 

---
template: userstudio
## Bonnes pratiques
### Créer un projet dans Rstudio

Pour créer un projet, File --> New Project 



<img src="../../resources/figs/CreateProject.png" title="plot of chunk rstudio_projet1" alt="plot of chunk rstudio_projet1" width="50%" style="display: block; margin: auto;" />



Choisir *Existing directory* ou *New directory* selon l'existence ou non du dossier du projet. Créer ou sélectionner le dossier, puis cliquer sur *Create project*

Une fois le projet créé, son nom est affiché dans un petit menu déroulant en haut à droite de l’interface de RStudio ![](../resources/common_figs/MenuProjet_reduit){width=50px}(menu qui permet de passer facilement d’un projet à un autre).

---
template: userstudio
## Tirer profit de la communauté 

### Installer un package 

Le but de l'installation est de télécharger et placer au bon endroit les codes \texttt{R} contenus dans le package

<img src="../../resources/figs/RStudioInstallPackage.png" title="plot of chunk rstudio_install_package" alt="plot of chunk rstudio_install_package" width="40%" style="display: block; margin: auto;" />


- En mode ligne de commande


```r
install.packages('ggplot2')
```

- Vérifier si le package est disponible et l'installer uniquement si besoin


```r
if ( ! require('FactoMineR')) install.packages('FactoMineR)
```


---
template: userstudio
## Tirer profit de la communauté 

### Charger le package

Il  ensuite charger le package dans votre environnement lorsque l'on souhaite l'utiliser.


- En mode interactif 

en cochant la case du package dans le menu Packages de RStudio 

- dans la console : fonction library ou require 


```r
library('ggplot2')
```

Le mode console est le mode compatible avec la production de documents. 





---
template: userstudio
### Exercice

- Installer le package \texttt{dplyr}
- Charger le package \texttt{dplyr}



### L'aide

Pour obtenir de l'aide :  

- en ligne de code dans la console


```r
help(dplyr) # lance l'aide associée à la commande dplyr
help.start()  # lande l'aide HTML 
```


- en mode interactif


\bcenter
![](../resources/common_figs/help_package){width="260px"}\
\ecenter


### L'aide 

La plupart des packages propose une documentation intitulée **vignettes**, décrivant l'utilisation du package

Pour accéder à la (aux) vignette(s) d'un package, taper dans la console : 


```r
browseVignettes("dplyr")
```

Il y a toujours des exemples que l'on peut exécuter directement.



## Utilisation de Rstudio 

### Rapports automatisés : R Markdown

L’extension **rmarkdown** permet de générer des documents de manière dynamique en mélangeant texte mis en forme et résultats produits par du code R. 

Les documents générés peuvent être au format HTML, PDF, Word, ...

Créer un R Markdown : 

- New File --> R Markdown...
- Préciser le nom du document et le format de sortie souhaité

Le fichier créé a une extension .rmd

### Création du document

\bcenter
![](../resources/common_figs/creation_rmd){width="260px"}\
\ecenter


### Eléments d'un document R Markdown

- en-tête délimité par 3 tirets
- texte du document 
- blocs de code R

\bcenter
![](../resources/common_figs/capture_rmd){width="200px"}\
\ecenter


### Compiler un document 

On peut à tout moment compiler, ou plutôt "tricoter" (Knit), un document R Markdown pour obtenir et visualiser le document généré. 

Pour cela, il suffit de cliquer sur le bouton Knit et de choisir le format de sortie voulu :

\bcenter
![](../resources/common_figs/knit_rmd){width="100px"}\
\ecenter


*Pour la génération du format PDF, vous devez avoir une installation fonctionnelle de LaTeX sur votre système.*

### Exercice 

- Créer votre R Markdown pour la formation

---

# Les objets R 



### Les objets

Principaux types de données :

- booléen ("logical") : TRUE, FALSE
- numeric : integer ou double
- caractères (character) : "bonjour"
- vide (null) : NULL
- complexe (complex) : 2+0i,2i
- binaires (raw)

Structuration des données :

- tous les éléments sont de même type (vecteur, matrice, tableaux)
- de types différents : liste, data.frame

*Le tableau individus/variable est la structure en statistique: chaque colonne représente une variable. Tous les éléments d'une colonne sont donc de même mode mais les colonnes peuvent être de modes différents (variables qualitatives, quantitatives)*
 

### Les objets 

Tout objet de R possède : 

\begin{itemize}
 \item un \textbf{mode} par exemple "logical", "numeric", "character", "list", "function"
 \item une \textbf{classe} :
  \begin{itemize}
    \item vecteurs (vector), 
    \item facteurs (factor),
    \item matrice (matrix), 
    \item liste (list), 
    \item fonction (function), 
    \item tableau de données (data frame)
  \end{itemize}
\end{itemize}



```r
X<-c(1:5,10,12) # création d'un vecteur intitulé X
X # affichage de X
```

```
## [1]  1  2  3  4  5 10 12
```

```r
is.vector(X) # X est-il un vecteur?
```

```
## [1] TRUE
```

```r
class(X) # quelle est la classe de l'objet?
```

```
## [1] "numeric"
```

### Les opérateurs logiques dans R


```r
?Comparison
# et
?base::Logic
```

| Opérateurs |      | Opérateurs |        |
|------------|------|------------|--------|
| $<$   | inférieur strictement à | $!=$   | différent de |
| $>$   | supérieur strictement à | %in%   | appartient à |
| $==$  | égal à                  | is.na  | est manquant |
| $<=$  | inférieur ou égal à     | !is.na | n'est pas manquant |







# Des ressources utiles

### Les anti sèches de RStudio

[R base](https://www.rstudio.com/wp-content/uploads/2016/10/r-cheat-sheet-3.pdf)

[RStudio](https://thinkr.fr/pdf/rstudio-french-cheatsheet.pdf)

[RMarkdown](https://www.rstudio.com/wp-content/uploads/2016/03/rmarkdown-cheatsheet-2.0.pdf)

[Importation](https://github.com/rstudio/cheatsheets/raw/master/data-import.pdf)

[Manipulation](https://github.com/rstudio/cheatsheets/raw/master/data-transformation.pdf)

[Visualisation](https://thinkr.fr/pdf/ggplot2-french-cheatsheet.pdf)

### Des livres

- A Language and Environment for Statistical Computing  [@Rbase], [https://www.R-project.org/](https://www.R-project.org/)

![](../resources/common_figs/cover_Rbase.png){width="40px"}\

- R for Data science [@r4ds], [https://r4ds.had.co.nz/](https://r4ds.had.co.nz/)

![](../resources/common_figs/r4ds_cover){width="40px"}\


- R pour la statistique et la science des données [@husson2018r], [https://r-stat-sc-donnees.github.io/](https://r-stat-sc-donnees.github.io/)

![](../resources/common_figs/R_stat_sc_donnees.png){width="40px"}\


### Références

<!-- ## Prerequisites -->

<!-- ### Data Structures in base R -->
<!--   1. Atomic vector (integer, double, logical, character) -->
<!--   2. Recursive vector (list) -->
<!--   3. Factor -->
<!--   4. Matrix and array -->
<!--   5. Data Frame -->

<!-- &nbsp; -->

<!-- \rsa Creation, Basic Operation, Manipulation, Representation -->

<!-- ### Resources -->
<!--   - Advanced R, chapters I.2, I.3 [@advr, [http://adv-r.had.co.nz/](http://adv-r.had.co.nz/)] -->
<!--   - An introduction to R programming [http://julien.cremeriefamily.info/teachings_L3BI_ISV51.html](http://julien.cremeriefamily.info/teachings_L3BI_ISV51.html) -->

<!-- ## Developement environment {.allowframebreaks} -->

<!-- ### The Rstudio API -->

<!-- - A full API with code, interpreter, workspace and plots -->
<!-- - Package developement and external code integration are easier -->
<!-- - Notebooks integration with Rmarkdown -->
<!-- - Interface with github -->

<!-- &nbsp; -->

<!-- \rsa Rstudio is a state-of-the-art tool for efficent development in `R` -->

<!-- ### My favorites shortcuts -->

<!-- - `ctrl + return`: execute current selection in console -->
<!-- - `ctrl + 1/2/3/4`: navigate between panels -->
<!-- - `ctrl + down/up`: navigate between tabs -->
<!-- - `ctrl + shift + k`: knit current doccument -->

<!-- ###  -->

<!-- ![Screenshot of the Rstudio API](figures/rstudio) -->

<!-- # Control Statements -->
<!-- ```{r control_statements, child = paste0('control_statements/', c("grouped_expressions.Rmd", "conditional_statements.Rmd", "loop_statements.Rmd")), cache = FALSE} -->
<!-- ``` -->
