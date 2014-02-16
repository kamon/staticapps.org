---
layout: post
title: Pourquoi construire des Applications Web Statiques ?
prev:
  label: Definissons les Applications Web Statiques
  url: /articles/fr/definissons-les-applis-statiques
next:
  label: Penser Services
  url: /articles/fr/penser-services
---

Plutôt que d'assembler du contenu dans les processus côté serveur, les applications web statiques s'appuient 
sur le navigateur de l'utilisateur pour gérer les interactions et la présentation du contenu. A une époque
considéré comme uniquement utile pour le contenu statique, les applis web statiques modernes peuvent dynamiquement 
récupérer des données, synchroniser plusieurs utilisateurs en temps réel, et plus.
Mais pourquoi *choisir* de construire une application web statique ?

**Appel à un large public.** Les applications web statiques sont construites avec les techniques HTML, JavaScript, et CSS. 
Bien que les développeurs web peuvent se spécialiser dans des langages et frameworks tels que Ruby, Python, et .NET,
tout développeur web (mais également de nombreux designers, entrepreneurs, et étudiants) sont familiers avec ces 
briques de base de la plate-forme web.

**Rapid Dévelopment rapide.** En utilisant des frameworks modernes tels que [Bootstrap](http://getbootstrap.com) et [AngularJS](http://angularjs.org), 
et des outils comme [Divshot](http://www.divshot.com/), vous pouvez rapidement "prototyper" une interface 
web. Ce prototype peut devenir votre application en le "connectant" à des services de données.

**Montée en charge simple.** Les applis web statiques sont juste des fichiers stockés sur un serveur web et 
envoyés tels quels à l'utilisateur final. Elles peuvent supporter la charge de millions d'utilisateurs avec 
des technologies de base (off-the-shelf). Vous aurez besoin de services back-end efficientes et qui supporte la montée en charge,
mais ces services sont de plus en plus disponibles auprès de fournissuers tierce-partie.
Les applis statiques vous permettent de vous concentrer sur votre application, pas votre infrastructure.

**Modularité dès le départ.** Toutes les applications web conçues pour supporter la charge ont
une forme d'architecture modulaire. Cela permet aux développeurs de construire les pièces de l'application
complète en utilisant des technologies spécialisées, bien adaptées aux problèmes spécifiques.
Les applications web statiques encouragent cette modularité dès le départ en imposant que toutes les données
back-end soient fournies par des services séparés de l'interface utilisateur.

**Flexibilité accrue.** Il est facile de contruire des interfaces alternatives lorsque le "front end" et le "back end"
sont séparés. Construire une application mobile, exposant une API de données publiques, faire un client en ligne de commande,
créer un panneau d'administration, et plus, deviennent beaucoup plus simple quand le back-end et le 
front-end sont construits de manière indépendante.

Bien sûr, les applications web statiques viennent avec leur part de défis. Le code exécuté dans le navigateur doit être
soigneusement conçu pour éviter d'ouvrir des failles de sécurité et permettre l'exploitation de ceux-ci. 
Il peut s'avérer difficile d'arriver à ce qu'un moteur de recherche prenne en compte le contenu dynamique
affiché au sein d'une application web statique. L'expérience utilisateur doit être soigneusement optimisé pour éviter l'impression de délai lorsque 
l'interface utilisateur et les données sont chargés indépendamment.
Chacun de ces défis peut être surmonté, et chacun sera abordé dans un futur chapître de ce guide.

