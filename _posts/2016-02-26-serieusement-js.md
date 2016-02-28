---
layout:     post
title:      Chaos.Js (Part 1)
date:       2016-02-26 12:31:19
summary:    Passer au Web mode js, analyse de l'environnement et impressions.
categories: javascript
---

<h2>Intro</h2>
Nous sommes dans une forte période de transition dans le web.

Les __SPA__ (Single Page Application) sont à la mode, et c'est vrai que c'est cool.
Mais j'ai depuis l'impression de voir deux clans; ou tout du moins deux types de developpeurs Web:

Ce que nous appellerons les *"hipsters"* du code, qui utilisent toutes les dernières technologies. Vous en connaissez forcément un, celui qui fait planer ce léger malaise quand il vous parle de sa dernière implémentation de WebComponent Polymer dans React qui marche comme sur des roulettes.

Opposés aux devs Web *"à l'ancienne"*, avec tous les frameworks MVC classiques que ce soit en Php (Symfony2, CakePHP,...) ou Ruby (RoR), qui sont à l'aise avec leurs acquis et ne souhaitent pas forcément se lancer dans autre chose.

<h2>Welcome back to the WebDev!</h2>

![desk](http://i.imgur.com/KyK6HUj.gif){:style="float: left; height:160px;margin-top: 10px;margin-right: 20px;"}

Je suis revenu dans le développement Web il y a quelques mois. 
J'avais déjà travaillé 2 ou 3 ans auparavant avec Symfony2 et CakePhp, du très classique.

Je vais dans ce billet vous parler de la transition jusqu'à aujourd'hui sur du dev <b>Js FullStack</b>.


<h2>Un jour je serai le plus grand <del>dresseur</del> hipster</h2>

Depuis *Node*, tout le monde parle js, c'est à la mode, mais je n'ai absolument rien suivi. 

Moi aussi je veux être **cool**!

Téléchargement, Installation, setup de node.js, swipe sur Chrome, on va Googler un peu comment ca marche.

<h3>L'écosystème. Such Wow.</h3>

Les technos sont jeunes, des noms de libs/packages rigolos à gogo sur *npm*, des projets sortent super souvent sur *GitHub*,...

**Hacker News** regorge d'articles annoncant la sortie de ces tools/librairies/frameworks.
Il y en a tous les jours en Front Page: *Chips.js*, *Espelette.js*, *Hammer.js*,... 

(ne cherchez pas j'ai mis les premiers mots qui me passaient par la tête, mais c'est bien possible qu'ils existent !)


<h3>Le langage</h3>

Avant de passer au coeur du problème, parlons rapidement du *js*. 

Pour ceux qui, comme moi, l'utilisaient uniquement avec *jQuery* pour des animations et/ou validations, sans jamais vraiment s'interesser ou comprendre le langage, il y a de quoi être surpris.

Le fonctionnement du langage en lui même est à part; on ne peut pas vraiment parler de  paradigme *Objet*  ni d'orientation strictement *procédural*. 

Les *scopes* sont étranges, le principe de *closure* wtf, les contextes *"this"* ont l'air d'être random, des *callbacks* dans tous les sens...

Non, définitivement le *js* ne ressemble pas vraiment aux autres languages.

<div style="text-align: center">
<img src="http://i.giphy.com/HwmV5U348FdKM.gif">
</div>
*(Si ça en intéresse je pourrai faire un billet sur les principales bizarreries/différences du js qui m'ont fait galérer au début)*

Il va falloir un peu de temps pour s'adapter.

Vous trouverez énormement de batailles sur le Web à son propos. *Pros* / *Cons* Js. Certains le trouve trop verbeux, d'autres trop broken, d'autres trop libre, d'autres génial... 

Au final on aime ou on n'aime pas. A chacun son avis, pour ma part, *j'adhère*. Mais le sujet n'est pas la.

J'ai abordé le Js comme je l'ai fait avec tous les autres languages; par de plus ou moins longues recherches sur Google des best practices ainsi que les outils indispensables qui font l'unanimité dans la communauté.

Et c'est là que le **cauchemar commence**. 



 <blockquote>
  <p>
 La marche des vertueux est semée d’obstacles qui sont les entreprises égoïstes que fait sans fin surgir l’œuvre du Malin.Béni soit-il l’homme de bonne volonté qui, au nom de la charité, se fait le berger des faibles qu’il guide dans la vallée d’ombre de la mort et des larmes… [...]
  </p>
  <footer><cite title="Un noob anonyme en js">Un noob anonyme en js</cite></footer>
</blockquote>

<h2>Fuck it. Just Fuck it.</h2>

Des outils dans l'univers js, ils y en a des *milliers*, voir *millions*. Beaucoup. Beaucoup trop ?

>"Et alors? C'est bien non? Ca laisse du choix!" 

Comme on dit un peu oui, mais pas trop.

Ils font la même chose avec des approches différentes, se livre souvent une guerre à grands coups de fanboys interposés.

Et il en sort de nouveaux souvent. Très souvent. Trop souvent.

Passer du temps, s'impliquer dans une techno pour que 2 mois après une nouvelle vienne lui voler la vedette et la remplacer...

**Fatigant non ?**

Je ne dénigre pas l'évolution, souvent que le language se porte bien et qui se produit de toute façon dans tout environnement.
Non; mais plutôt la vitesse à laquel les tendances changent.

Cela ne nous permet pas de maîtriser *réellement* un outil tout en restant *up-to-date*.

Bref, ne nous dispersons pas. Voilà en 2 minutes de recherche ce que j'ai trouvé sur Internet à propos des outils de DevWeb en js:

* Webpack
* RequireJs
* Browserify
* Gulp
* Grunt
* Broccoli
* AMD
* CommonJs
* Asm
* Babel
* Typescript
* CoffeeScript
* ...

<div style="text-align: center">
	<img src="http://i.imgur.com/lSt1P.gif" />
	<img src="https://media.giphy.com/media/Lcn0yF1RcLANG/giphy.gif" style="height: 173px;"/>
	<img src="https://media.giphy.com/media/StdULHPSni728/giphy.gif" style="height: 173px;" />
</div>

<h4>C'est le chaos.</h4> 

À l'époque, j'avais appris Symfony2, Twig et Doctrine; et <b>Boum</b>, le projet était "au top".

<h4>Que s'est t-il passé ?!</h4>

Maintenant je dois apprendre à utiliser des dizaines d'outils, dont je ne comprends ni le but, ni l'utilité.
Mais ça il ne faut pas le dire au risque de passer pour un *has-been*.

Tout le Web vante leurs mérites de par le gain de *productivité / performances* qu'ils apportent. 
Si vous voulez avoir une belle stack; *vous devez les utiliser*.

**FAUX.**

Dans la deuxième partie de ce sujet, j'exposerai mon point de vu sur cette idée ainsi le rôle de chaque composant, ce qu'ils peuvent vous apporter (ou non) histoire de clarifier et démystifier tout cela.

De plus, il est assez difficile de trouver des *ressources "passerelles"*  sur le web expliquant comment se lancer dans ce monde (le Web 2.0 ou 3.0 ou n'importe quel autre terme de marketeux) quand on est ni un Js guy depuis 3 ans, ni un débutant total dans la programmation !


Pour les vieux de la vieille du js, qui ont suivi l'évolution de l'écosysteme, tout cela peut sûrement paraître idiot, mais je vous assure que quand on arrive dans le développement Web du moment, il y a de quoi être perdu. 

Car **rien**, je dis bien **RIEN** n'est évident. 

Je soupçonne beaucoup de développeurs d'être des soldats au service de la hype.
Faire le *getting started* d'une techno sans jamais l'avoir vraiment exploité en profondeur, et déclarer que c'est une "révolution" ne me semble pas être quelque chose de sain. 

Je peut me tromper. Peux-être que cette pensée émane de ma jalousie envers celui qui connait, benchmark et sait utiliser de A à Z un outil avant même que j'en ai entendu parler.

<h2>Bob does Hype Web Programming. Bob is smart.</h2>

Je vais vous raconter une petite histoire, celle de Bob:

Bob découvre une nouvelle techno montante, *PiouPiou.js*, 1000 stars sur GitHub en 3 jours, qui vient d'être publiée sur la Front Page de Hacker News. 

> Cool !

Bob ne sait pas ce que c'est, mais ça lui paraît sexy. Le logo est cool, le website aussi. 

> Il faut que je teste ! Il me le faut absolument !

Bob est super excité, a déjà installé le nouveau Graal, c'est bon, il n'y a plus qu'à.  

> Wait, c'est quoi exactement ? Ça ressemble pas à *Patchouli.js*, le tool que j'ai implémenté la semaine dernière ? 

C'est vrai que c'est la même chose que *Patchouli.js* mais ca fonctionne très différemment ! Bob va encore devoir bouquiner pas mal de documentation...

Mais Bob veut être cool. Tout le monde dit que *PiouPiou.js* c'est mieux, la théorie des masses ne peut pas se tromper.

*3 heures plus tard passées dans la souffrance, Bob a fini.*

C'est bon ! C'est implémenté, fonctionnel, Bob ne comprend pas tout mais bon, ça viendra avec le temps. Maintenant son *dev flow* est de nouveau hype !

Bob est heureux.

Bob retourne sur Hacker News et... 

<b>Wait; c'est quoi ce nouveau tool *Milou.js* ?! 1000 stars sur GitHub en 3 jours, ... </b>

<div style="text-align: center;">
	<img src="https://media.giphy.com/media/b1ys7yyXBDG0w/giphy.gif">
	<p>	Et bien <b>Bob</b>, c'était, c'est et ce sera (jusqu'à ce que je me soigne complètement) <b>moi</b>.</p>

</div>

**Dat Twist!**

Et peut-être vous aussi!
Ne le prenez pas mal. J'espère juste ne pas être seul dans cette misère et que certains se reconnaitront!

Dans l'histoire de Bob (ou moi du coup) je connais au moins le but du tool.
Je ne vous raconte pas le nombre de fois ou je n'avais même pas bien saisi le but de l'outil mais dont j'ai tout de même essayé de l'implémenter!
*(brainless over 9000)*

Parce que oui, la nouveauté, c'est excitant. Mais dans le dev ça peut vite devenir **chronophage**.

Le temps que nous sommes censé gagner grâce à un nouveau système n'arrive que après avoir passé un **certain point** de la **courbe d'apprentissage**.

Et cela peut être plus ou moins long.

Quand l'évolution est *plus rapide* que le temps nécessaire à atteindre ce *fameux capital de compétence*, il y a un **problème**.

Ou quand la *complexité* d'utilisation d'éléments ayant pour but de **faciliter** une réalisation devient *supérieur* à la réalisation elle même.

<blockquote>
  <p>
    - [...] du coup je me suis setup un petit Gulp qui transpile mon CoffeeScript et mon SASS avant de bundle avec Webpack mon app. Easy.
    <br />
     - Ha... Ouais, ouais je vois... C'est quoi ton projet?
     <br />
     - Une todo list.
  </p>
  <footer><cite title="Un WebDev Hypster à un old school">Un WebDev Hypster à un Old School Dev</cite></footer>
</blockquote>

<h2>Next</h2>

On commence à s'étirer en longeur.
Premier post très subjectif, orienté coup de geule / état des lieux.  

C'est donc dans une deuxieme partie que je dévoilerai comment "contrôler" cet enfer paradisiaque qu'est la *Hype*, les solutions à ce bazar innommable.

...

Comment ça j'essaye de créer de la hype autour de mon prochain post ?!

Merci à [@Bhullnatik](https://twitter.com/Bhullnatik) pour la relecture.

