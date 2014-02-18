---
layout: post
title: Routage des URLs dans les applis web statiques
prev:
  label: Assembling Your Static App Stack
  url: /articles/assembling-your-static-app-stack
next:
  label: Authentication and Authorization
  url: /articles/authentication-and-authorization
---

Dans [Definissons les Applications Web Statiques](/articles/defining-static-web-apps) nous avons vu que
dans les applications web statiques le serveur se contente de passer des fichiers HTML plats sans aucun traitement 
supplémentaire. Néanmoins, une application web de qualité se sert d'**URLs lisibles** qui **décrivent le contenu se trouvant
à cet endroit**. Par exemple, en développant une application qui affiche les informations de la météo, `/zip/90014` est 
une meilleure manière de représenter la météo à Los Angeles comparé à `/#w-zone.120453931`.
D'où la question: Comment maintenir des URLs propres et lisibles tout en faisant le gros du boulot au niveau du navigateur ?

### Structure d'URL

Voici un schéma rapide de l'anatomy d'une URL :

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

When building a static application, there are two primary challenges with traditional URL structures:

1. Because static apps use JavaScript to construct dynamic content for the page, reloading the page when
   a link is clicked is both unnecessary and undesireable. Instead, static apps will ideally load/display new data
   using JavaScript or simply hide or show various elements appropriately.
2. Even if a static app only has a single HTML file that is meant for all URLs, users may enter the application
   from any path name. If the server is not prepared for this, things will appear broken to the user.

The HTML5 specification brought a solution to the first problem via the History API, and the second problem
can be addressed through server configuration or the use of newer static web hosts that are built for single-page
static apps.

### L'API "HTML5 History"

Modern browsers give developers the ability to programatically create new browser history entries that alter the
displayed URL without the need for a new request. Using the `history.pushState` method developers have full control
of the browser's navigational history for an application.

> You may have heard of "hash" or "hashbang" URLs. These URLs utilize the fragment portion of the URL as if it
> were an extension of the path name (e.g. `#/zip/90014`). While once a common or encouraged practice, the HTML5 History API makes
> hash URL misuse unnecessary. Only consider this technique if you must [support older browsers](http://caniuse.com/#search=pushstate).

While it is actually very simple to implement HTML5 History directly (see [this great article on the Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/Guide/API/DOM/Manipulating_the_browser_history)
for an overview), most developers will use a routing library that is either built in to their framework of choice
(such as [Backbone Router](http://backbonejs.org/#Router) or [ngRoute](http://docs.angularjs.org/api/ngRoute)) or
utilize a library that provides more concrete implementations of common practices (such as [Page.js](http://visionmedia.github.io/page.js/)).

### Travailler "côté serveur"

Properly handling URLs is one of the only areas of static web application development where the server matters.
Most static web servers will not work with HTML5 `pushState` by default. Instead, if a user navigates to a "deep link"
the server won't recognize the URL and will issue a 404 error.

Modern static application hosts such as Divshot fully support routing for HTML5 apps,
but services such as Amazon S3, Dropbox, and GitHub Pages have no capability for URL reassignment. Some offer a generic
"error page" that can be repurposed for static application routing, but doing so is strongly discouraged as for any non-browser the pages
will appear to be erroneous. If you are self-hosting, it is possible to [configure web servers such as Apache and Nginx](http://readystate4.com/2012/05/17/nginx-and-apache-rewrite-to-support-html5-pushstate/)
to work with the HTML5 History API.

While it is tempting to simply send all paths to the same file, it may be worthwhile to keep your rules more tightly scoped
(for example, rendering your application for `/zip/*` but not for `/nonsense`).

---

User-friendly, readable URLs are a vital aspect of any web application. More than just the way a user
gets to your application, URLs are a part of the user experience when it comes to navigation, sharing,
and search engine friendliness. URLs provide a mental context about the structure and content of your site
for the user, and having well-structured, memorable URLs will make your site more functional and more easily
incorporated into your users' daily habits.
