---
layout: post
title: Routing des URLs dans les applis web statiques
prev:
  label: Assembler le stack technologique de votre application
  url: /articles/fr/assembler-le-stack-technologique.md
next:
  label: Authentification et Autorisation
  url: /articles/fr/authentification-et-autorisation
---

Dans [Definissons les Applications Web Statiques](/articles/fr/defining-static-web-apps) nous avons vu que
dans les applications web statiques le serveur se contente de passer des fichiers HTML plats sans aucun traitement 
supplémentaire. Néanmoins, une application web de qualité se sert d'**URLs lisibles** qui **décrivent le contenu se trouvant
à cet endroit**. Par exemple, en développant une application qui affiche les informations de la météo, `/zip/90014` est 
une meilleure manière de représenter la météo à Los Angeles comparé à `/#w-zone.120453931`.
D'où la question: Comment maintenir des URLs propres et lisibles tout en faisant le gros du boulot au niveau du navigateur ?

### Structure d'une URL

Voici un schéma rapide de l'anatomie d'une URL :

<img src="/articles/images/url-anatomy.svg" class="diagram full-width" alt="URL Anatomy Diagram">

Il est conseillé d'utiliser le **chemin (path name)** pour décrire *ce que* votre application affiche et, en option, 
la **query string** pour fournir des paramètres supplémentaires indiquant *comment* cela doit être affiché.

Le **hash** d'une URL est quelquechose de spécial : le contenu du hash n'est *jamais envoyé au serveur*. En fait, le hash
sert à avoir des liens et de la navigation internes à la page. Supposons que nous avons une page avec du code tel que :

```html
<article id="post-123">
  <!-- Content for the article -->
</article>
<article id="post-456">
  <!-- Content for another article -->
</article>
```

Ouvrir la page avec `#post-456` à la fin de l'URL va automatiquement provoquer le scroll du navigateur jusqu'au 
niveau du second élément.

### Applis statiques et URLs

Lorsque l'on développe une application statique, la gestion des URLs traditionnelles pose deux problèmes :  

1. Les applis statiques utilisant du JavaScript pour construire dynamiquement le contenu de la page, lors d'un click sur un lien,
   il n'y a pas besoin, voir il n'est pas souhaité, que la page soit rechargée. Au lieu de cela, une appli statique 
   charge/affiche les nouvelles données avec du JavaScript ou simplement cache ou montre des éléments en fonction du besoin.
2. Même si l'appli statique utilise un unique fichier HTML pour toutes les URLs, les utilisateurs 
   peuvent interagir avec l'application en passant par n'importe quel chemin. Si le serveur ne sait pas traiter 
   cette éventualité, l'utilisateur peut avoir une impression de dysfonctionnement.
   
La spécification HTML5 a apporté une solution au premier problème avec l'API History. Quant au second,
il peut être traité via la configuration du serveur ou l'utilisation de nouveaux types d'hébergements "web statique" 
conçus pour les applis statiques "mono-page".

### L'API HTML5 History

Les navigateurs modernes permettent aux développeurs de créer de manière programmatique de nouvelles entrées dans 
l'historique du navigateur, modifiant ainsi l'URL affichée sans qu'il n'y ait besoin d'une nouvelle requête. 
En utilisant la méthode `history.pushState`, les développeurs ont complêtement le contrôle de l'historique de 
navigation d'une application.

> Vous avez probablement entendu parler des URLs "hash" ou "hashbang". Ces URLs utilisent la partie de l'URL avec le `#` 
> comme une extension du chemin (ex. `#/zip/90014`). Pratique courante ou encouragée par le passé, l'astuce des URLs hash 
> n'est plus nécessaire depuis l'API HTML5 History. N'envisagez cette technique que si vous devez
> [supporter les anciens navigateurs](http://caniuse.com/#search=pushstate).

Bien qu'il soit en fait très simple d'implémenter l'API HTML5 History directement (lire [ce très bon article sur Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/Guide/API/DOM/Manipulating_the_browser_history)
pour en savoir plus), la plupart des développeurs vont soit utiliser une bibliothèque de routing qui est intégrée à leur framekork   
de choix (telle que [Backbone Router](http://backbonejs.org/#Router) ou [ngRoute](http://docs.angularjs.org/api/ngRoute)), 
soit utiliser une bibliothèque qui fournit des implementations plus concrêtes pour les besoins courants (telle que [Page.js](http://visionmedia.github.io/page.js/)).

### Gestion côté serveur

La gestion efficace des URLs est l'un des seuls domaines du développement d'applications web statiques où 
le choix du serveur est important.
La plupart des serveurs web statiques ne fonctionneront pas par défaut avec la méthode HTML5 `pushState`. En fait,
si l'utilisateur invoque une "URL profonde", le serveur ne saura pas la traiter et retournera une erreur 404.
Les hébergeurs d'applications statiques modernes tels que Divshot supportent complètement le routing pour les applis HTML5,
mais les services tels que Amazon S3, Dropbox, et GitHub Pages ne savent pas faire de la re-assignation d'URL.
Certains offrent une page "error page" qui peut être détournée pour le routing d'application statique, mais cette façon de faire
est fortement déconseillée car, pour un client autre que le navigateur, les pages apparaîtront comme des pages d'erreur.
Si vous mettez en place votre propre hébergement, il est possible de [configurer des serveurs web tels que Apache et Nginx](http://readystate4.com/2012/05/17/nginx-and-apache-rewrite-to-support-html5-pushstate/)
pour fonctionner avec l'API HTML5 History.
Bien que ce soit tentant de simplement associer tous les chemins au même fichier, cela peut valoir le coût de définir vos 
règles de manière strict (par exemple, servir votre application pour `/zip/*` mais pas pour `/nimportequoi`).

---

Des URLs lisibles et simples à utiliser constituent un aspect vital pour toute application web. Au delà de fournir le moyen
par lequel l'utilisateur arrive sur votre application, les URLs font partie de l'expérience utilisateur lorsqu'il s'agit de
facilité de navigation, partage, et recherche. Les URLs fournissent à l'utilisateur un contexte mental de la structure 
et du contenu du site. Ainsi, avoir des URLs mémorisables et bien structurées améliore l'ergonomie de votre site 
et l'intègre plus facilement dans les habitudes quotidiennes de vos utilisateurs.
