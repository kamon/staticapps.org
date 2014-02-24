---
layout: post
title: Definissons les Applications Web Statiques
next:
  label: Pourquoi construire des Applications Web Statiques ?
  url: /articles/fr/pourquoi-construire-des-applis-statiques
---

On parle d'**Application web statique** dans le cas de toute application qui peut êre servie
directement au navigateur d'un utilisateur final sans aucune modification, coté serveur, du 
contenu HTML, CSS, ou JavaScript. Une telle définition peut inclure des sites avec une arborescence très plate, 
et qui ne changent pas, par exemple un site "institutionnel". Mais les *applications* web statiques 
font généralement référence à des sites riches qui servent du contenu dynamique en utilisant
des technologies au niveau du navigateur plutôt que sur le serveur.

### Une application web Tradionnelle

De nombreuses applications web s'appuient sur la génération de pages HTML coté serveur
pour fournir une expérience dynamique.

En termes simples, voici comment cela fonctionne :

1. Le client (navigateur) envoie une requête au serveur web à une adresse donnée.
2. Le serveur reçoit la requête et fait suivre son information à l'application web.
3. L'application web se connecte aux bases de données ou autres sources d'information
   en fonction des caractéristiques de la requête (tel que l'adresse, la session utilisateur, ou autre).
4. L'application web utilise ces données pour générer dynamiquement du HTML (par exemple, pour afficher
   le nom d'un utilisateur dans l'entête ou peupler une page de recherche avec des résultats).
5. Le serveur envoie le HTML créé au client, qui va l'interpréter et l'afficher à l'utilisateur final.

Notez que l'application web elle-même pourrait utiliser parmi une multitude de technologies, frameworks,
et langages de programmation (Ruby, Python, Node.js, Java, .NET, et Go pour ne citer que quelques uns).
Ce que ces outils ont en commun c'est que *le HTML est construit à partir de données dynamiques sur le serveur
et envoyé au navigateur en tant que document complet*.

### Une application web Statique

Comparons ce qu'on vient de voir au cas d'une application web statique :

1. Le client (navigateur) envoie une requête au serveur web statique à une adresse donnée.
2. Le serveur reçoit la requête et assure la correspondance entre l'adresse et un simple fichier HTML
   stocké sur le serveur.
3. Le serveur envoie le fichier HTML au client, qui va ainsi l'interpréter et l'afficher à l'utilisateur final.
4. Le JavaScript dans la page HTML utilise le navigateur pour se connecter à des services de données et 
   récupérer les informations nécessaires pour construire le contenu de la page.
5. Le JavaScript dans la page prends les données et manipule le HTML de la page, le mettant à jour
   avec ces données.
   
La principale difference ici est que dans une appli web traditionnelle, le *serveur* est responsable de
récupérer les données et de les compiler en HTML que l'utilisateur peut voir, alors que dans une appli web statique
c'est le *navigateur* qui s'en charge.

> **Astuce:** Vous voulez voir si une page donnée est est une appli web statique ? Utilisez la fonction **Afficher la source** de votre navigateur. 
> Si vous voyez des données utilisateur ou autres contenus dynamques dans le code source, il s'agit d'une appli traditionnelle. 
> Si vous voyez uniquement la structure de base de la page, il s'agit d'une appli statique.

Cela peut sembler une petite différence, mais cela a un impact important sur l'architecture, la conception,
et l'expérience utilisateur de l'application toute entière. Nous verrons en détail certaines des raisons
pour lesquelles vous pourriez faire le choix de construire des applis web statiques.

### Applis hybrides

Applis traditionnelles et applis statiques sont aux deux extrémités du spectre. Entre les deux il y a 
de nombreuses façons d'utiliser des aspects de chacun pour obtenir certains des avantages des deux. 
Il est courant, par exemple, pour une application, de stocker des pages entièrement générées à partir de 
contenu dynamique, puis d'utiliser JavaScript pour chercher des données supplémentaires, personnalisées
pour un utilisateur donné.

> Lorsque vous visitez le site **Airbnb** en étant identifié, vous avez pu remarquer que pendant une à deux secondes la page indique
> "Inscription" et "Connexion". Une fois complètement chargée, la page montre votre photo et votre nom, tels que 
> enregistrés dans votre profil. Ceci est un exemple d'une appli hybride avec certaines données venant du serveur, 
> et d'autres du navigateur.

Bien que les applis hybrides peuvent apporter à la fois les avantages des applis statiques et ceux des applis
traditionnelles, elles viennent aussi avec plusieurs challenges sur le plan architectural.
Avec l'amélioration progressive des navigateurs et des technologies qui font tourner les applis statiques,
l'on peut avoir plusieurs des avantages des applis hybrides dans un site complétement statique.
