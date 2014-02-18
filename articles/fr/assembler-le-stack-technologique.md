---
layout: post
title: Assembler le stack technologique de votre application
prev:
  label: Penser Services
  url: /articles/fr/penser-services.md
next:
  label: Routage des URLs dans les applis statiques
  url: /articles/fr/routage-des-urls-dans-les-applis-statiques
---

Une fois que vous avez décidé de construire une application web statique, il y a encore plusieurs choix importants
à faire en termes de stack technologique de votre application. Bien qu'une application web statique peut être
écrite entièrement dans un seul fichier HTML (avec de la CSS et du JavaScript embarqué), les applications complexes
bénéficient grandement de la grande variété d'outils et services disponibles pour le développement web statique.
Les applications web statiques utilisent généralement une combination of des catégories d'outils qui suivent.

### Langages pré-processeurs

Les langages pré-processeurs sont des langages de programmation qui sont compilés en HTML, JavaScript, ou CSS.
Ils peuvent offrir une syntaxe plus concise, des fonctionnalirés supplémentaires, et d'autres avantages 
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

### Hébergement pour le web statique

Bien sûr, vous aurez besoin d'un endroit où héberger votre projet une fois que vous êtes prêt à le mettre en ligne.
Il y a de nombreuses options pour de l'hébergement web statique, y compris les hébergements mutualisés traditionnels,
et les nouveaux services dédiés à l'hébergement web statique. Lorsque vous choisissez un espace d'hébergement, il y a quelques
éléments (en dehors du coût) à prendre en considération :

* L'hébergement fournit-il un service d'accélération de contenus via un réseau global de serveurs ?
* Le fournisseur offre-t-il la possibilité d'héberger une appli web statique avec protection SSL ?
* Quel degré de facilité avec le processus de déploiement ? Y a-t-il des options pour le confort du développeur, comme le rollback ?

**Exemples:** [Divshot](http://www.divshot.io/), [Amazon S3](http://aws.amazon.com/s3/), [GitHub Pages](http://pages.github.com/)

### Services "back-end" ou techniques 

Les fournisseurs de services "back-end" offrent un moyen d'implémenter une partie des besoins de votre application 
sans avoir à héberger ou développer du code spécifique pour ces besoins. Il peut s'agir, entre autres, de stockage 
de bases de données, d'authentification d'utilisateurs, ou d'envoi d'email. Certains fournisseurs tendent vers une offre
large et cohérente tandis que d'autres se concentrent sur une portion plus restreinte des besoins de votre application.

**Examples:** [Firebase](http://www.firebase.com/), [UserApp](http://userapp.io), [Hull](http://hull.io)

### APIs tierces / génériques

Si vous construisez une appli web statique et souhaitez intégrer des données d'une API tierce, vous avez de la chance !
De nombreux fournisseurs d'API offrent maintenant soit des bibliothèques JavaScript dédiées pour une intégration directe 
au niveau du navigateur ou supportent les applis web statiques via la technique [Cross-Origin Resource Sharing](https://developer.mozilla.org/en-US/docs/HTTP/Access_control_CORS).
Se connecter aux APIS au niveau navigateur vous fait gagner le coût d'infrastructure supplémentaire si vous deviez relayer 
les requêtes via vos propres serveurs.

**Exemples:** [AWS SDK for Browser](http://aws.amazon.com/sdkforbrowser/), [GitHub API](http://developer.github.com/v3/)

### APIs spécifiques

A mesure que vous construisez votre application, certaines parties peuvent se révéler difficiles ou impossibles 
à implémenter via une API prête à l'emploi. C'est acceptable et c'est totalement conforme avec l'idée d'une application statique.
Lorsque vous vous retrouvez dans ces cas, il est préférable de construire la fonctionnalité dont vous avez besoin sous forme 
d'un service compacte, indépendant, conçu pour être facilement consommé par le navigateur et toutes les autres 
plate-formes que vous supportez.

---

Le choix d'un stack technologique qui fonctionne bien pour vous est vital pour la productivité et la maintenabilité de votre projet.
Ce qui fonctionne bien pour une application peut ne pas fonctionner pour une autre, mais un des avantages de 
l'approche "web statique" est que vous avez plus de flexibilité pour composer une pile technologique modulaire qui 
colle au mieux à vos besoins.