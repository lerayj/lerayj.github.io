---
layout:     post
title:      1 an avec Meteor.js
date:       2016-02-26 12:31:19
summary:    Ou le crash de la comète
categories: javascript
---

**Preface**

*J'avais la suite de Chaos.js bien au chaud en __local__.*<br> 
*__Pas besoin__ de push sur GitHub, ce n'est pas du code.*<br>
*Je me suis fais voler mon ordinateur.*<br>
*Et ma motivation avec.* <br>
*En fin de compte, j'aurai du push, __surtout__ parceque ce n'est pas du code.*<br>


<h2>Back in the Game!</h2>
Plutôt que réecrire ce good'ld Chaos.js, je vais me préter à un autre exercice pour me dérouiller les doigts.

Et pourquoi pas un petit retour sur mon experience après 1 an de travail avec Meteor.js?

Avec pour ce que ca vaux, mon analyse de la situation, et dans la langue de Molière 3.0 avec ca!

**Let's go.**


<blockquote>
  <p>
    Les idées de Meteor, c'est un peu comme celles de Marx; Belles, mais inapliccables.
  </p>
  <footer><cite title="Me">La minute politique pour rester dans le contexte de l'actualité</cite></footer>
</blockquote>

<h2>Ma vision de Meteor</h2>
<div style="text-align: center">
<img src="https://d14xs1qewsqjcd.cloudfront.net/assets/og-image-logo.png">
</div>

<h2>Un précurseur</h2>
<div style="text-align: center">
<img src="https://media.giphy.com/media/3ornjJSq2s9xznhO80/giphy.gif">
</div>

<div style="text-align: center">
<img src="https://media.giphy.com/media/l49FqlUguNsGDNCGk/giphy.gif">
</div>

L'idée étais belle, précursive. Pour rebouclé avec mon premier article, Meteor c'est positioné pile dans l'axe pour les gens déboussolé. Une stack de développement complete, en real time, user friendly et prédéfini; plus de dilemme cornélien sur le choix de techno pour chaque composant de l'application.
La solution a la js fatigue. De grandes ambitions, et non backer par les geants et leurs influences dans les technos de demain que sont Facebook ou Google, Open Source.

Avant de rentrer dans le dur, et après relecture, il m'est apparu que mon constat n'est pas très flatteur.
On retiens plus facilement les mauvais  coté que les bons; Meteor à de nombreux avantage. Faire du live est très simple; a vrai dire, on a même pas besoin d'y penser, ca ce fais tous seul! Et tous ca en écrivant du code vraiment simple!
Mais de fait, on s'arrache les ceveux sur les problèmes et c'est ce qui marque, et c'est donc ce qui va transparaitre.

<h2>La confusion par la simplicité</h2>

Faire du Meteor basique, c'est simple. tant que l'application ne grossie pas trop, les problèmes reste plutôt mineurs.

Il n'empêche que Meteor n'est pas déconcertant d'évidence comme le laisse a penser les getting started. Plusieurs notions sont vraiment requises pour pouvoir exploiter l'outil: 
* la compréhension des variables réactives (ce qu'elle peuvent contenir comme type pour pouvoir s'activer), 
* le mecanisme de cache coté front (un 2ieme "mongo" coté front, avec évidamment beaucoup moins de fonctionnalités...), 
* les principes et differences entre les pub/sub et methods (comment les utiliser, pourquoi et quand), la distinction entre le code client et serveur...

Rien de rocket science, mais cela demande de la vrai pratique car beaucoup de ces principes sont inconnus aux développeurs web old school ou peu famillier avec le monde du js.
confusion cache client base mongo
Contrairement a ce qui est (ou étais) brandé, Meteor n'est pas pour les débutants en js. Il abstrait énormément de concept, qui peuvent vite passer du ressort de la magie aux yeux de non averti. C'est alors que les choses deviennent dangereuse. Une fois qu'une mécomprehension c'est établie, ou une fausse assomption, tous peux vite devenri chaos.

<h2>Pas de pattern evident</h2>
Les prmiers problèmes arrive avec la complexité du modèle de vue. J'ai uniquement travailler avec Blaze, le moteur de templating par default. Etant très proche du fonctionnement d'un Handlebars/Mustache, il n'y a que très peu de logique composant, ce qui rend l'organisation et la réutilisation plutôt difficile. C'est a vous de tous mettre en oeuvre pour ne pas ce "piéger" dans des patern dirty.

Je pense que ce problème est réel et justifié par le passage a React par de nombreux développeur Meteor au cours de l'année 2016.

Nous en arrivons donc a une contradiction, qui, selon moi, a tuer l'intêret de Meteor.

<h2>La communauté JS, une magnifique faiblesse</h2>
A vouloir satisfaire tout le monde on ne contente personne
Relativement peu d'utilisateurs sur une même stack au final
L'explosion des framework de vues
Dans le monde du js reste et restera durant encore un certain temps selon moi (voir Chaos.js part.1). Si Meteor ce voulai être une plateforme/ stack qui unifiai et amenai tous le monde dans une direction avec les même technologies a différent niveau au début, les exigeances changeante ont tué cette possibilité.

Les fan d'Angular, React, Vue, puis [insert your front framework name here] on voulu remplacé Blaze par leur champion. Concilliant, les mainteneurs ont pris le partie d'intégrer officiellement certains d'entre eux.


<h2>S'imposer en standard ou mourir</h2>

<h3>Les packages</h3>
Il en est de même avec le systeme de package Atmosphere propre a Meteor. J'ai commencer à une époque ou ce systeme étais le seul provider de packet tiers. npm n'étais disponible que par quelques hacks peu naturel et difficilement maintenable, marchotant après des heures d'échecs d'installation.

Une fois que le mainteneur ont vu que ce systeme de package ne faisait pas l'hunanimité, et limitai énormément le déeloppement de Meteor par la difficulté d'acces aux ressources disponible ailleurs, il a donc été question d'integrer npm.

Nous nous retrouvvons donc dans une situation batarde ou cohabite npm et Atmoshère, selon moi pouir le pire. La gestion de dépendance n'est déjà pas une partie de plaisir, et elle l'est encore moins quand il marche de deux facons différentes.

<h3>La gestion d'import</h3>
Les imports, magnifique implémentation qui manquai cruellement au standart JS c'est finallement démocratisé. Si ce fonctionnement semble aujourd'hui une évidence, cela n'étais pas du tout la philosophie de Meteor. MDG à pris le parti d'imposer des règle de d'ordre de loading en fonction de l'arborescence des fichiers, de leur noms. Tous étais alors charger en global. Si cela ne pose pas de problème dans un premier temps, on ce rend vite compte du désordre qui nous accable après quelques itérations.

Encore une fois, MDG a corriger le tir en implémentant la logique d'import tel que l'on l'a connais. Mais difficile de faire des transition aussi forte sans "casser" les applications après upgrade. Il en reviens donc a 

La correction de tir permanente
Meteor n'est juste pas ce a quoi il aspirai. En ne se positionnant plu comme une stack complête, il en perd beaucoup de son intêret. Alors autant s'en passer.


Le router
Pas de router officiel. 
L'abandon de MDG et de la branche forte de la communauté
<h2>Éleve toi et tombe</h2>
Les précurseurs ne sont pas focément les gagnants. J'y ai cru. Ca aurai pu, ca n'a pas été.
Je ne vais pas vous mentir, je ne reutiliserai pas Meteor. J'ai beaucoup aimé travailler avec, comme j'ai parfois détesté.
Mais

<script type="text/javascript">
    console.log("CA marche;");
</script>
