---
layout: post
title: Assembler la pile technologique de votre application
prev:
  label: Penser Services
  url: /articles/fr/xxxxx
next:
  label: Routing URLs in Static Apps
  url: /articles/fr/xxxxx
---

Une fois que vous avez décidé de construire une application web statique, il y a encore plusieurs choix importants
à faire en termes de pile technologique (stack) de votre application. Bien qu'une application web statique peut être
écrite entièrement dans un seul fichier HTML (avec de la CSS et du JavaScript embarqué), les applications complexes
bénéficient grandement de la grande variété d'outils et services disponibles pour le développement web statique.
Les applications web statiques utilisent généralement une combination of des catégories d'outils qui suivent.

### Langages pré-processeurs

Les langages pré-processeurs sont des langages de programmation qui sont compilés en HTML, JavaScript, ou CSS.
Ils peuvent offrir une syntaxe plus concise, des fonctionnalirés supplémentaires, ou d'autres avantages 
par rapport au langage de base. Bien que certains de ces langages sont écrits en JavaScript et peuvent être entièrement parsés
et executés dans le navigateur, ils sont généralement compilés vers le langage cible avant d'être déployés sur le serveur web.

**Exemples:** [CoffeeScript](http://coffeescript.org), [LESS](http://www.lesscss.org/), [HAML](http://haml.info/), [Dart](https://www.dartlang.org/)

### Outils de "build" / Générateurs de site

Les applications web statiques sont stockées sur le serveur et servies au navigateur sous forme de fichiers HTML,
CSS, et JavaScript, mais il y a d'autres façons de gérer le début du processus. Les outils de build aident les développeurs
à effectuer les tâches importantes telles que combiner plusieurs fichiers en un, compiler les langages pré-processeurs,
ou même "packager" le code en une application mobile.

Différents outils seront créés selon les besoins. Certains servent un besoin spécifique
alors que d'autres peuvent être utilisés quel que soit l'application que voulez construire. 
Lorsque vous choisissez un outil de build, il est logique de chercher quelquechose qui s'adapte à votre workflow, 
est activement maintenu, et dispose d'une communauté active d'utilisateurs.

**Exemples:** [Jekyll](http://jekyllrb.com/), [Grunt](http://gruntjs.com/), [Yeoman](http://yeoman.io/), [Harp](http://harpjs.com/)

### Gestionnaires de packages

Les gestionnaires de packages permettent aux développeurs d'installer de manière aisée le code de modules 
open source ou partagées qui doivent servir pour un ensemble d'applications. Lorsque vous utilisez un gestionnaire de paquets,
vous pouvez déclarer, pour votre project, des **dépendances** que le gestionnaire de paquets va automatiquement télécharger
et installer au bon endroit. Ceci facilite à la fois l'installation de nouveaux modules et la mise à jour de 
modules existants dans vos projets.

**Exemples:** [Bower](http://bower.io/), [Component](http://component.io)

### Frameworks JavaScript

Le framework JavaScript vous fournit les outils et méthodologies pour organiser la logique et la structure de données 
de votre application, ainsi que (souvent) des façons d'exécuter des templates et/ou manipuler le HTML de la page.
Votre choix de framework est un des aspects les plus importants pour votre application du fait qu'il a un impact
considérable sur tout, de la structure de fichiers du projet à la manière dont vos balises sont écrites.

Chaque framework utilise une méthodologie différente, par exemple "Model View Controller" (MVC) ou "Model View
View Model" (MVVM). Chaque méthodologie a ses forces, ses faiblesses, et ses communautés, et il est utile d'investir du temps
pour bien investiguer les options avant de faire son choix.

**Exemples:** [Angular](http://angularjs.org/), [Ember](http://emberjs.com/), [Backbone](http://backbonejs.org/)

### Frameworks d'interface utilisateur

Un framework d'interface utilisateur peut vous aider à implémenter rapidement les patterns communs d'interface,
en fournissant de bons styles et comportements par défaut pour votre application. Utiles aussi bien pour le
prototypage rapide d'application que comme base pour du code en production, ces frameworks vous apportent
des éléments tels que les boutons, les grilles de présentation ("grid layouts"), les formulaires, etc.

**Exemples:** [Bootstrap](http://getbootstrap.com), [Foundation](http://foundation.zurb.com)

### Hébergement

Of course, you'll need a place to host your project once you're ready to bring it online. There are many options
for static web hosting including traditional shared hosts, online storage with hosting, and new dedicated static
web hosting services. When choosing a host, there are a few things (other than cost) to look for:

* Does the host provide any kind of content acceleration through a global server network?
* Can I host an SSL-protected static web app on the provider?
* How easy is the deploy process? Are there developer-friendly features like rollback?

**Examples:** [Divshot](http://www.divshot.io/), [Amazon S3](http://aws.amazon.com/s3/), [GitHub Pages](http://pages.github.com/)

### Back-End Services

Back-end service providers offer a way to implement a part of your application's business needs without having to host
or build custom code for it. These services may provide database storage, user authentication, email delivery, or
a variety of other services. Some back-end services try to offer a comprehensive package while others focus on a narrower
slice of your application needs.

**Examples:** [Firebase](http://www.firebase.com/), [UserApp](http://userapp.io), [Hull](http://hull.io)

### Third-Party APIs

If you're building a static web app and would like to integrate with data from a third-party API, you're in luck!
Many API providers now offer either dedicated JavaScript libraries for direct browser integration or support static
web apps through [Cross-Origin Resource Sharing](https://developer.mozilla.org/en-US/docs/HTTP/Access_control_CORS).
Connecting to APIs in-browser saves you the duplicated infrastructure cost of proxying requests through your own servers.

**Examples:** [AWS SDK for Browser](http://aws.amazon.com/sdkforbrowser/), [GitHub API](http://developer.github.com/v3/)

### Custom Server APIs

As you build out your application, you may find there are pieces that can't be handled by an off-the-shelf third-party
provider. That's ok, and totally in keeping with a static application mindset! When you run into these cases, it's best
to build the functionality you need as a compact, independent, purpose-driven service that can be easily consumed by the
browser and any other platforms you support. 

---

Choosing a technology stack that works well for you will be vital to the productivity and maintainability of your project.
What works well for one application may not work well for another, but one of the benefits of building static is that
you have more flexibility to compose an ideal, modular stack that suits your needs.
