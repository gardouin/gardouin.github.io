---
layout: page
title: Projects
permalink: /projects/
---

An overview of my past and ongoing projects.

## INTERNSHIP 2025 (ongoing): Confidence-based safety properties in <a href="https://www.caisar-platform.com/" target="_blank">CAISAR</a>

**CAISAR public repository:** <a href="https://git.frama-c.com/pub/caisar/" target="_blank">gitlab</a>

## INTERNSHIP 2024: Symbolic execution directed by A*

**Project repository:** <a href="https://github.com/gardouin/klee-reach" target="_blank">github</a><br>
**Documentation:** <a href="../upload/klee_reach_developer_manual.pdf" target="_blank">pdf</a><br>
**User manual:** <a href="../upload/klee_reach_user_manual.pdf" target="_blank">pdf</a>

L'exécution symbolique est une approche peu efficace sur des programmes de grande taille : c'est une conséquence de l'explosion du nombre de chemins dans l'arbre d'exécution, voire de la potentielle infinité de l'arbre d'exécution symbolique. Il est tout de même possible d'envisager de nouvelles heuristiques pour améliorer cette approche. Des <a href="https://link.springer.com/chapter/10.1007/978-3-031-47115-5_4" target="_blank">travaux réalisés par mes encadrants</a> s'intéressent à cette problématique et ont débouché sur deux nouvelles stratégies de recherche inspirées par l'algorithme A*. Ces heuristiques ont été implémentées dans <a href="https://binsec.github.io/" target="_blank">BINSEC</a>, un outil utilisant de l'exécution symbolique pour des programmes binaires. Cependant, ces approches peuvent également être implémentées dans d'autres outils, comme <a href="https://klee-se.org/" target="_blank">KLEE</a>, qui permet de faire de l'exécution symbolique sur des programmes écrits dans des langages de plus haut niveau. L'objectif de mon stage était donc d'implémenter ces heuristiques de recherche dans KLEE, ainsi que toutes les fonctionnalités nécessaires pour faire de l'analyse d'atteignabilité avec ce programme.

Mon travail a donc débouché sur la conception d'une extension de KLEE permettant d'utiliser ces nouvelles heuristiques.
J'ai notamment dû réfléchir à la problématique de rendre KLEE capable de faire de l'analyse d'atteignabilité, car cet outil n'a pas initialement été conçu pour ça.
J'ai ensuite pu m'inspirer du fonctionnement des heuristiques existantes dans KLEE afin d'implémenter les nouvelles heuristiques A\*.
La réalisation de ces heuristiques a également nécessité l'ajout de fonctionnalités comme la collecte de certaines informations lors de l'exécution symbolique.
Enfin, les heuristiques A* prenant en compte la distance entre une instruction et la cible à atteindre, j'ai également conçu un outil externe, développé en Python, afin de calculer ces distances et de les utiliser dans les nouvelles stratégies d'exploration.

## INTERNSHIP 2023: Development of a Visual Studio Code extension for <a href="https://github.com/ticktac-project/tchecker" target="_blank">TChecker</a>

**Project repository:** <a href="https://github.com/gardouin/tchecker-vscode" target="_blank">github</a><br>
**Documentation:** <a href="../upload/tchecker_vscode_documentation.pdf" target="_blank">pdf</a>

TChecker est un outil de vérification par model-checking de systèmes temps-réel, développé au LaBRI par <a href="https://www.labri.fr/perso/herbrete/" target="_blank">Frédéric Herbreteau</a> et <a href="https://www.labri.fr/profil/Point_ID1084917772" target="_blank">Gérald Point</a>. Il est également utilisé par plusieurs chercheurs, en France et en Inde notamment, pour développer et tester leurs propres algorithmes de vérification. TChecker est constitué de plusieurs outils permettant notamment la validation syntaxique des modèles, leur simulation, et la vérification formelles ce ces modèles.

Afin de faciliter l'utilisation des différents outils de TChecker, j'ai développé une extension pour Visual Studio Code, permettant principalement :
- la coloration syntaxique des modèles
- l'assistance à l'édition (auto-complétion, affichage des signatures, hover)
- l'utilisation des outils de TChecker dans l'environnement de VSCode
