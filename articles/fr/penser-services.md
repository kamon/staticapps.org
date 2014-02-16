---
layout: post
title: Penser Services
prev:
  label: Pourquoi construire des Applications Web Statiques ?
  url: /articles/fr/pourquoi-construire-des-applis-statiques
next:
  label: Assembler votre stack d'application statique
  url: /articles/fr/assembler-votre-stack-d-appli-statique
---

Les applications web statiques ont des contraintes très clairement définies, et de ce fait
se prêtent naturellement à l'**Architecture orientée service** ou, en anglais, **Service-Oriented Architecture (SOA)**.
Une application construite avec SOA est composée de plusieurs briques indépendantes (services)
se coordonnant pour réaliser les objectifs de l'application.

Construire une application avec l'orientation services apporte trois bénéfices clé :

1. Chaque service est construit de manière indépendante. Les services peuvent donc utiliser des technologies
   particulièrement adaptées à leurs domaines spécifiques.
   Par exemple, un service de recherche pourrait fonctionner de manière très différente d'un service de livraison d'e-mail.
2. Des frontières claires entre services signifient des expériences utilisateur plus susceptibles de supporter
   la montée en charge. Les services peuvent être optimisés de manière individuelle, et le fait qu'un service
   ne réponde pas ne fait pas nécessairement tomber l'application entière.
3. Souvent, les services peuvent être structurés de telle manière qu'il est possible qu'ils soient entièrement
   implémentés par des fournisseurs tierce partie.

L'orientation services n'est pas juste un modèle théorique pour des logiciels à succès. 
Les sites les plus gros et supportant le plus de traffic, sur le web aujourd'hui,  
utilisent le SOA pour construire des applications plus rapides et plus résilientes.

> Each service could be revved on its own deployment schedule, often weekly, empowering
> each team to deliver innovation at its own desired pace.  We unwound the centralized 
> deployment team and distributed the function into the teams that owned each service. 
> <span class="attribution"><a href="http://techblog.netflix.com/2012/06/netflix-operations-part-i-going.html">Netflix</a> on transitioning to SOA</span>

Amazon a [reçu un fameux mandat de Jeff Bezos](http://apievangelist.com/2012/01/12/the-secret-to-amazons-success-internal-apis/) 
(à l'époque en 2002!) demandant à toutes les équipes d'exposer leur travail avec des services d'API internes
qui doivent être construites de manière à pouvoir être rendues publiques à tout moment.
Il semble que la création d'Amazon Web Services soit au moins partiellement à porter au crédit de ce mandat.

---

Comment les applis web statiques s'intègrent dans la vision SOA ? D'une certaine manière, vous pouvez voir
une appli web statique comme un **User Interface Service**. Elle a la responsabilité de se connecter à
et se corrdonner avec les autres services de votre application pour fournir une expérience intuitive, cohésive,
pour un utilisateur final.

Chose intéressante, cela veut dire qu'il peut être très simple de construire plusieurs UIs pour   
la même application. Par exemple, vous pouvez construire une interface pour les utilisateurs finaux,
et une autre, complètement séparée, pour les adminitrateurs de l'application.
Les Architectures orientée service peuvent être implementées de diverses manières, bien que dans notre cas
la communication entre services va probablement se faire avec l'envoi et la réception 
de données JSON via HTTP.

Lorsque vous réfléchissez à la meilleure façon de structurer votre application, avoir à l'esprit 
la modularité et les bénéfices de l'Architecture orientée service peut vous aider à faire les bons choix 
dès le début. Comme vous allez le voir dans les futurs châpitres, le navigateur peut être un très bon agent de coordination
pour une myriade de services web.
