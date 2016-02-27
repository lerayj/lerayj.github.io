---
layout:     post
title:      Badass.Js (Part 1)
date:       2016-02-26 12:31:19
summary:    Passer au Web mode js, analyse de l'environnement et impressions fait par un gars normal pas très futé.
categories: javascript
---

<h2>Intro</h2>
Nous sommes dans une forte période de transition dans le web.

Les __SPA__ (Single Page Application) sont à la mode, et c'est vrai que c'est cool.
Mais j'ai depuis l'impression de voir deux clans; ou tout du moins deux type de developeurs Web:

Ce que nous appellerons les __"hipsters"__ du code, qui utilisent toutes les dernières technos avec qui vous sentez ce légerèrement mal à l'aise (pour ne pas dire idiot / dépassé / retard) quand ils vous parlent de leurs dernière impémentation de WebComponent Polymer dans React.

Opposé aux devs Web __"à l'ancienne"__, avec tous les frameworks MVC classiques que ce soit en php (Symfony2, CakePHP,...) ou Ruby (RoR), qui sont à l'aise avec leurs acquis et ne souhaitent pas forcément ce lancer dans autre chose.

<h2>Welcome back to the WebDev!</h2>

![desk](http://i.imgur.com/KyK6HUj.gif){:style="float: left; height:160px;margin-top: 10px;margin-right: 20px;"}

Je suis revenu dans le developement Web il y a quelques mois. 
J'avais déjà travaillé 2 ou 3 ans auparavant avec Symfony2 et CakePhp, du très classique.

Je vais dans ce billet vous parler de la transition jusqu'a aujourd'hui, en tant que dev <b>Js FullStack</b>.


<h2>Un jour je serai le plus grand <del>dresseur</del> hipster</h2>

Depuis *Node*, tous le monde parle js, c'est à la mode, mais je n'ai absolument rien suivi. 

Merde moi aussi je veux être **cool**!

Téléchargement, Installation, setup de node.js, swipe sur Chrome, on va Googler un peu comment ca marche.

<h3>L'écosystème. Such Wow.</h3>

Les technos sont jeunes, des noms de libs/packages rigolos à gogo sur **Npm**, des projets sortent super souvent sur **GitHub**,...

**Hacker News** regorge d'articles annoncant la sortie de ces tools/lib/framework.
Il y en à tous les jours en front page: *Chips.js*, *Espelette.js*, *Hammer.js*,... 

(ne cherchez pas j'ai mis les premiers mots qui me passai par la tête, mais c'est bien possible qu'ils existent!)


<h3>Le language</h3>

Avant de passer au coeur du problème, parlons rapidement du *js*. 

Pour ceux qui, comme moi, l'utilisai uniquement avec **Jquery** pour des animations et/ou validations, sans jamais vraiment s'interesser ou comprendre le language, il y a de quoi être surpris.

Le fonctionnement du language en lui même est à part; on ne peux pas vraiment parler de  paradigme *Objet*  ni d'orientation strictement *procédural*. 

Non, le *js* ne ressemble pas vraiment aux autres languages (normal me dirai vous).

Les **scopes** sont étranges, le principe de **closure** wtf, les contextes **"this"** on l'air d'être random, des **callback** dans tous les sens...

<div style="text-align: center">
<img src="http://i.giphy.com/HwmV5U348FdKM.gif">
</div>
*(Si ca en interesse je pourrai faire un billet sur les principaux trucs bizarres/différents du js qui m'ont fait galérer au début)*

Il va falloir un peu de temps pour s'adapter.

Vous trouverez énormement de bataille sur le Web à son propos. *Pros* / *cons* Js. Certains le trouve trop verbeux, d'autres trop broken, d'autres trop libre, d'autres génial... 

Au final on aime ou on n'aime pas. A chacun sont avis, pour ma part, **j'adhère**. Mais le sujet n'est pas la.

J'ai abordé le Js comme je l'ai fais avec tous les autres languages; par de plus ou moins longues recherches sur Google des best practices ainsi que les outils indispensables qui font l'unanimité dans la communauté.

Et c'est la que le **cauchemar commence**. 



 <blockquote>
  <p>
 La marche des vertueux est semée d’obstacles qui sont les entreprises égoïstes que fait sans fin surgir l’œuvre du Malin.Béni soit-il l’homme de bonne volonté qui, au nom de la charité, se fait le berger des faibles qu’il guide dans la vallée d’ombre de la mort et des larmes… [...]
  </p>
  <footer><cite title="Un noob anonyme en js">Un noob anonyme en js</cite></footer>
</blockquote>

<h2>Fuck it. Just Fuck it.</h2>

Des outils dans l'univers js, ils y en a des **milliers**, voir **millions**. Beaucoup. Beaucoup trop?

>"Et alors? C'est bien non? Ca laisse du choix!" 

Comme on dit un peu oui, mais pas trop.

Ils font la même chose avec des approches différentes, se livre souvent une guerre à grands coups de fanboys interposés.

Et il en sort de nouveaux souvent. Très souvent. Trop souvent.

Passer du temps, s'impliquer dans une techno pour que 2 mois après un petit nouveau vienne voler la vedette et le remplacer...

**Fatiguant non?**

Je ne dénigre pas l'évolution, qui signifie souvent que le language se porte bien, et qui se fait dans tous les environnement.
Mais plutôt la vitesse à laquel les tendances changent.

Cela permet difficilement de maîtriser **pour de vrai** un outil tous en restant *up-to-date*.

Bref, ne nous dispersons pas. Voilà en 2 minutes de recherches ce que j'ai trouvé sur Internet à propos des outils de DevWeb en js:

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

<h4>C'est quoi ce bordel?!</h4> 

A l'époque, j'avais appris Symfony2, Twig et Doctrine; et <b>Boum</b>, le projet étais "au top".

<h4>Que c'est t-il passé?!</h4>

Maintenant je dois apprendre à utiliser des dizaines de trucs, dont je ne comprend ni le but, ni l'utilité.
Mais ca il ne faut pas le dire au risque de passer pour un abruti.

Tous le Web vante le mérite de ces outils et surtout le gain de *productivité / performances* qu'ils apportent. 
Si vous voulez faire un bon produit; **il vous les faut**.

*Dans un prochain post, je les classerai et expliquerai les principaux leurs buts pour clarifier et démystifier tous ca*

De plus, il est assez difficile de trouver des *ressources "passerelles"* sur le web expliquant comment ce lancer dans ce monde (le Web 2.0 ou 3.0 ou n'importe quel autre terme de marketeux) quand on est ni un Js guy depuis 3 ans, ni un total noob dans la prog!

<blockquote>
  <p>
    - [...] du coup je me setup un petit Gulp qui transpile mon CoffeeScript et mon SASS avant de bundle avec Webpack mon app. Easy.
    <br />
     - Ha... Ouais, ouais je vois... C'est quoi ton projet?
     <br />
     - Une todo list.
  </p>
  <footer><cite title="Un WebDev Hypster à un old school">Un WebDev Hypster à un old school</cite></footer>
</blockquote>


Pour les vieux de la vieille du js, qui ont suivi l'évolution de l'écosysteme, tout cela peut surement paraitre idiot et issu de ma limitation intellectuel, mais je vous assure que quand on arrive dans le "nouveau monde" du developpement Web, **rien**, je dit bien **RIEN** n'est évident. 

Je soupsonne également beaucoup de gens de n'avoir fait que le *getting started* d'une techno, ne jamais l'avoir vraiment exploité en profondeur; avant de crier au génie...

Je peux me tromper. Peux être que cette pensée émane de ma jalousie envers ceux qui savent, benchmarkent et connaissent de A à Z un outil avant même que j'en est entendu parler.

<h2>Bob do Hype Web Programming. Bob is smart.</h2>

Je vais vous raconter une petite histoire, celle de Bob:

Bob découvre une nouvelle techno montante, *PiouPiou.js*, 1000 stars sur github en 3 jours, qui viens d'être publié sur la front page de Hacker News. 

> "Cool!" se dit Bob.

Bob ne sais pas ce que c'est, mais ca lui paraît sexy. Le logo est cool, le Website aussi. 

> "Il faut que je teste! Il me le faut absolument!"

Bob est super excité, a déjà installé le nouveau Graal, c'est bon, il n'y a plu qu'a.  

> "Wait, c'est quoi exactement? Ca ressemble pas a *Patchouli.js*, le tool que j'ai implémenté la semaine dernière? 

C'est vrai que c'est la même chose que *Patchouli.js* mais ca fonctionne très différament! Bob va encore devoir bouquinner pas mal de doc...

Mais Bob veux être cool. Tous le monde dit que *PiouPiou.js* c'est mieux, la théorie des masses ne peux pas se tromper.

*3 heures plus tard passé dans la souffrance, Bob a fini*

C'est bon! C'est implémenté, fonctionnel, Bob ne comprend pas tout mais bon, ca viendra avec le temps. Maintenant son *Dev Flow* est de nouveau hype!

Bob est heureux.

Bob retourne sur Hacker News et... 

<b>Wait; c'est quoi ce nouveau tool *Milou.js* ?! 1000 stars sur GitHub en 3 jours, ... </b>

<div style="text-align: center;">
	<img src="https://media.giphy.com/media/b1ys7yyXBDG0w/giphy.gif">
	<p>	Et bien <b>Bob</b>, c'est <b>moi</b>.</p>

</div>

**Dat Twist!**

Et peut-être vous aussi (enfin j'espère que certains ce reconnaitrons!).

Si dans l'histoire je connais au moins l'usage du produit, je ne vous raconte pas le nombre de fois ou je n'ai même pas saisi le but du tool mais tout de même essayer d'implémenter!
*(brainless over 9000)*


<h2>Next</h2>

Dans une deuxieme partie, je vous parlerai de comment j'essaye d'éviter de tomber en permanence dans cet enfer, quel est la solution à ce foutoir innomable.


