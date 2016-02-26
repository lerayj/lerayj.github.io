---
layout:     post
title:      Sérieusement Js?! ...
date:       2016-02-26 12:31:19
summary:    Comment éviter de se perdre dans la jungle du Web Js
categories: javascript
---

<h2>Intro</h2>
Nous sommes à mon avis dans une forte periode de transition dans le web.

Les __SPA__ (Single Page Application) sont à la mode, et c'est vrai que c'est cool.
Mais j'ai depuis l'impression de voir deux clans; ou tout du moins type de devlopeur Web:
Ce que nous appellerons les __"hypsters"__ du code, qui utilisent toutes les dernières technos (je ne parlerai que du js pour cette catégorie) et avec qui vous vous sentez idiot/dépassé quand vous parler dev avec eux.

D'un coté le Web __"a l'ancienne"__, avec tous ces framwork MVC que ce soit en php (Symfony2, CakePHP,...) ou Ruby (RoR), qui sont à l'aise avec leurs acquis et ne souhaite pas forcément ce lancer dans autres chose (mais qui sortent quand même un produit; et souvent mieux maîtrisé)

<h2>Welcome back to the WebDev!</h2>

![desk](http://i.imgur.com/KyK6HUj.gif){:style="float: left; height:150px;margin-top: 10px;margin-right: 20px;"}

Je suis arrivé dans le dev js il y a maintenant une dizaine de mois. 
J'avais déjà fais du Web il y a maintenant quelques années (2 - 3 ans) avec Symfony2 et CakePhp.

Je vais donc vous parler de ma transition jusqu'a aujourd'hui, en tant que dev FullStack Js WebApp, mon ressenti, comment je l'ai vécu et comment j'essaye d'éviter les pièges de ce New World.

**Spoiler Alerte* * 

Ca à été a la fois passionant et déprimant.

<h2>Un jour je serai le plus grand <del>dresseur</del> hipster</h2>

Js, Node,... Tous le monde en parle, c'est à la mode, mais je n'ai absolument rien suivi. 
Merde moi aussi je veux être cool!

Téléchargement/Installation/setup de node.js
Swipe sur Chrome, on va Googler un peu comment commencer.

<h3>L'écosysytème. Such Wow.</h3>

Des technos sont jeunes, des noms de libs/packages rigolos à gogo, de nouveaux projets sortent sur github tous les jours,...
Hacker News feed de tous ces tools/lib/framework/, il y en à tous les jours en front page: Chips.js, Espelette.js, Hammer.js,... 

(ne cherchez pas j'ai mis les mots qui me passai par la tête, mais c'est bien possible que ca existe!)


<h3>Le language</h3>

Le language en lui même est a part; on ne peux pas parlé de programmation objets comme dans les autre languages, ce n'est pas non plu du procédural. 

Je pense qu'on aime ou on n'aime pas. Certains trouve ca trop verbeux, d'autres trop broken,... Bref chacun a sont avis.

Pour ma part, j'adère.


Mais le sujet n'est pas la.


J'ai abordé le sujet js comme je fesai avec tous les autres languages; par de longues recherches sur Googles des best practices et des outils indispensable.

Et c'est la que le cauchemar commence. 



 <blockquote>
  <p>
 La marche des vertueux est semée d’obstacles qui sont les entreprises égoïstes que fait sans fin surgir l’œuvre du Malin.Béni soit-il l’homme de bonne volonté qui, au nom de la charité, se fait le berger des faibles qu’il guide dans la vallée d’ombre de la mort et des larmes… [...]
  </p>
  <footer><cite title="Un WebDev Hypster à un old school">Un noob anonyme en js</cite></footer>
</blockquote>

<h2>Fuck it. Just Fuck it.</h2>

Des outils dans l'univers js, ils y en a des milliers, voir millions. Beaucoup. Beaucoup trop?

Souvent ils font la même chose avec des approches différentes, qui se livre souvent une guerre par communauté de fanboys/devs éclairés interposé.

>"Et alors? C'est bien non? Ca laisse du choix!" 

Comme on dit un peu oui, mais pas trop.

 Ca ne vous stresse pas d'apprendre, passer du temps, s'impliquer dans une techno, pour que 2 mois après un petit nouveau vienne voler la vedette? 

 Je ne dénigre pas l'évolution, mais la vitesse à laquel les tendances changes, qui permettent difficilement de complètement maîtriser un outils tous en restant "à la pointe".

 Bref, ne nous dispersons pas,.

* Webpack
* RequireJs
* Browserify
* Gulp
* Grunt
* Broccoli
* AMD
* CommonJs
* asm
* babel
* typescript
* coffescript
* ...


![desk](http://i.imgur.com/lSt1P.gif)
![desk](https://media.giphy.com/media/Lcn0yF1RcLANG/giphy.gif){:style="height: 173px;"}
![desk](https://media.giphy.com/media/StdULHPSni728/giphy.gif){:style="height: 173px;"}

C'est quoi ce bordel?! A l'époque, quand je bossai sur Symfony2 par exemple, j'apprend Symfony, Twig et Doctrine; et Boum, un projet que tous le monde considère comme "au top".

Maintenant je dois apprendre a utiliser des 10 de trucs, dont je ne prend pas l'utilité, mais tous le web en vente les merites et le gain de productivité qu'il apporte, qui de plus ne sont pas des composants de l'app.
Cela ne sont que des tools pour aider a construire votre app.

Pour certains, qui y sont maintenant habitué, cela peut surement paraitre idiot, mais quand on comment rien, je dit bien RIEN n'est évident. Dans un prochain post, je commenterai donc les different "types" d'outils.

<h2>L'histoire d'un dev idiot</h2>

Je vais vous raconter une petite histoire (ce comportement est peux être stupide, peut être ne verrez vous pas se que je parle,... mais je suis sur que certaines personnes se reconnaitrons!):

Je découvre une nouvelle technos avec 1000 stars sur github, qui viens d'être publié en front page de Hacker New. 

Cool.

Je ne sais pas ce que c'est mais ca a l'air sexy. Le logo est cool, le Website aussi. Il faut que je test!

Wait, c'est quoi exactement? Ca ressemble pas a *insert tool name you want here*? 

Je dresse la liste. En plus ca a l'air vraiment très différent pour faire la même chose, il va falloir tout ré apprendre.
C'est parti, ca me semble jouable et utile, je tente.

Useless, ne perd pas ton temps avec des conneries comme ca, tu va encor y passer la soirée pour avoir la même chose.

![desk](https://media.giphy.com/media/b1ys7yyXBDG0w/giphy.gif)

 Et bien, ce gars la c'est moi. Peut-être vous aussi.

<h2>La solution ou du moins</h2>

Est ce que j'utilise déjà un tools similaire qui serai voué a être remplacé par
est ce que la hype me semble finallement justifié? Les apport par rapport a l'existant sont ils vraiment énormes? 
Faux.
Utilisez ce qu'il vous faut quand il vous faut. Je vous recommande vraiment d'integrer un part un toutes les technos qui vous interesse.

<blockquote>
  <p>
    - [...] du coup je me setup un petit Gulp qui transpile mon CoffeScript et mon SASS avant de bundle avec Webpack mon app.
    <br />
     - Ha... Ouais, ouais je vois... C'est quoi ton projet?
     <br />
     - Une todo list.
  </p>
  <footer><cite title="Un WebDev Hypster à un old school">Un WebDev Hypster à un old school</cite></footer>
</blockquote>

<h2>Next</h2>

Je parlerai des framework/plateforme/grosses libs de l'écosystème js dans un autre posts, comment j'ai fais mes choix sur les tchnos que j'ai décider d'utiliser et d'étudier