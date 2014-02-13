
On parle d'**Application web statique** dans le cas de toute application qui peut êre servie
directement au navigateur d'un utilisateur final sans aucune modification, coté serveur, du 
contenu HTML, CSS, ou JavaScript. Une telle définition peut inclure des sites avec une arborescence très plate, 
et qui ne changent pas, par exemple un site "institutionnel". Mais les *applications* web statiques 
font généralement référence à des sites riches qui servent du contenu dynamique en utilisant
des technologies au niveau du navigateur plutôt que sur le serveur.


### Une application web Tradionnelle

De nombreuses applications web s'appuient sur la g�n�ration de pages HTML c�t� serveur
pour fournir une exp�rience dynamique.

Cela fonctionne, en termes simples, de la mani�re suivante :

1. Le client (navigateur) envoie une requ�te au serveur web � une adresse donn�e.
2. Le serveur re�oit la requ�te et fait suivre son information � l'application web.
3. L'application web se connecte aux bases de donn�es ou autres sources d'information
   en fonction des caract�ristiques de la requ�te (tel que l'adresse, la session utilisateur, ou autre).
4. L'application web utilise ces donn�es pour g�n�rer dynamiquement du HTML (par exemple, pour afficher
   le nom d'un utilisateur dans l'ent�te ou peupler une page de recherche avec des r�sultats).
5. Le serveur envoie le HTML cr�� au client, qui va l'interpr�ter et l'afficher � l'utilisateur final.

Notez que l'application web elle-m�me pourrait utiliser une parmi une multitude de technologies, frameworks,
et langages de programmation (Ruby, Python, Node.js, Java, .NET, et Go pour ne citer que quelques uns).
Ce que ces outils ont en commun c'est que *le HTML est construit � partir de donn�es dynamiques sur le serveur
et envoy� au navigateur en tant que document complet*.

### Une application web Statique

Comparons ce qu'on vient de voir au cas d'une application web statique :

1. Le client (navigateur) envoie une requ�te au serveur web statique � une adresse donn�e.
2. Le serveur re�oit la requ�te et assure la correspondance entre l'adresse et un simple fichier HTML
   stock� sur le serveur.
3. Le serveur envoie le fichier HTML au client, qui va ainsi l'interpr�ter et l'afficher � l'utilisateur final.
4. Le JavaScript dans la page HTML utilise le navigateur pour se connecter � des services de donn�es et 
   r�cup�rer les informations n�cessaires pour construire le contenu de la page.
5. Le JavaScript dans la page prends les donn�es et manipule le HTML de la page, le mettant � jour
   avec les donn�es r�cup�r�es � l'�tape pr�c�dente.
   
La principale difference ici est que dans une appli web traditionnelle, le *serveur* est responsable de
r�cup�rer les donn�es et de les compiler en HTML que l'utilisateur peut voir, alors que dans une appli web statique
c'est le *navigateur* qui se charge de �a.

> **Tip:** Want to see if a given page is a static web app? Just use **View Source** in your browser. If you
> see user-specific data or other dynamic content in the source code, it's a traditional app. If you
> only see the basic structure of the page, it's a static app.

Cela peut sembler une petite diff�rence, mais cela a un impact important sur l'architecture, la conception,
et l'exp�rience utilisateur de l'application dans sa globalit�. Nous regarderons en d�tail certaines des raisons
pour lesquelles vous pourriez faire le choix de construire des applis web statiques.

### Applis hybrides

Les applis traditionnelles et statiques sont aux deux ext�mes oppos�s du spectre

Les applications traditionnelles et statiques sont aux extr�mit�s oppos�es du spectre. Entre les deux il y a 
de nombreuses fa�ons d'utiliser des aspects de chacun pour obtenir certains des avantages des deux. 
Il est courant, par exemple, pour une application, de stocker des pages enti�rement g�n�r�es � partir de 
contenu dynamique, puis d'utiliser JavaScript pour chercher des donn�es suppl�mentaires, personnalis�es
pour un utilisateur donn�.

> If you visit **Airbnb** while logged in, you may notice that for a second or two, the page may say
> "Sign Up" and "Log In". Once fully loaded, the page shows your profile picture and name. This is an
> example of a hybrid app with some data rendered by the server, some by the browser.

Bien que les applis hybrides peuvent apporter � la fois les avantages des applis statiques et ceux des applis
traditionnelles, elles viennent aussi avec plusieurs challenges sur le plan architectural.
Avec l'am�lioration en cours des navigateurs et des technologies qui font tourner les applis statiques,
l'on peut avoir plusieurs des avantages des applis hybrides dans un site compl�tement statique.
