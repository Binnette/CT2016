## Intro

- Site officiel : https://jquery.com/
- Définition : bibliothèque JS libre et multi-plateforme qui facilite l’écriture de scripts côté client
- Langages : JS
- Licence : MIT (open source)
- Mainteneurs : « The jQuery Foundation » https://jquery.org/

![Logo jQuery](https://github.com/Binnette/CT2016/blob/master/1-jQuery/assets/logo-jquery.png)

## La Licence

- Puis je utiliser jQuery dans mes applications perso/pro ? OUI
- Extrait de la licence MIT sur https://tldrlegal.com/license/mit-license

**Quick Summary of MIT License**

> A short, permissive software license. Basically, you can do whatever you want as long as you include the original copyright and license notice in any copy of the software/source.  There are many variations of this license in use.

| Can            | Cannot      | Must              |
| -------------- |-------------| ----------------- |
| Commercial use | Hold liable | Include Copyright |
| Modify         |             | Include Licence   |
| Distribute     |             |                   |
| Sublicense     |             |                   |
| Private Use    |             |                   |

## Les selectors

- Ils permettent de trouver des éléments DOM de la page
- Recherche d’un élément par son id
  - $("#dropdown-products") retourne l’élément avec l’id “dropdown-products”
- Recherche par type d’élément
  - $("div") retourne un tableau contenant toutes les div de la page
- Recherche par classe css
  - $(".bold") recherche les élements DOM qui ont la class .bold
- Filtrer pour ne garder que les éléments ‘visibles’ (affichés à l’écran)
  - $(":visible")
- Les selector peuvent être chainés
  - $("input:visible") retourne les inputs affichés à l’écran
- Et bien d’autres encore : https://api.jquery.com/category/selectors/

## Manipulation du DOM

- Une fois votre élémént DOM trouvé, vous pouvez le modifier
- Modifier le css
  - $("div").css("color", "red");
  - $("div").css("font-weight", "bold");
- Supprimer un élément du DOM
  - $("#element").remove();
- Ajouter un élément après un autre
  - $("span").after("Salut");
  - $("span").after("<button>Click</button>");
- Obtenir la valeur d’un input
  - $("input").val();
- Et bien d’auters encore https://api.jquery.com/category/manipulation/
- Masquer/Afficher un élément, etc.

## Pour aller plus loin 1/2

* jQuery permet également entre autres :
  * De faire des appels Ajax
  * D’animer une page web (accordéon déroulant, caroussel d’images, etc)

* jQuery peut être complété par des plugins http://plugins.jquery.com/
  * Par exemple Select2 qui permet d’ajouter des dropdown avec auto-complétion https://select2.github.io/

![select2](https://github.com/Binnette/CT2016/blob/master/1-jQuery/assets/select2.png)

  * Jquery ui qui est une palette de composants web https://jqueryui.com/

![jquery-ui](https://github.com/Binnette/CT2016/blob/master/1-jQuery/assets/jquery-ui.png)

## Pour aller plus loin 2/2

Vu qu’il est possible de manipuler les pages web affichées sur notre écran.
**Pourquoi ne pas en tirer avantage ?**

* Ce site web ne vous plait pas ?
  * Modifier le !

* Il manque une fonctionnalité à ce site web ?
  * Coder la !

* Et pour se simplifier la tâche, il existe des extension dans Chrome ou Firefox pour injecter automatiquement du code JS sur une page

* Démo avec le site de la carte ticket restaurant 
  * https://github.com/Binnette/ticket-resto-exporter.user.js


**--FIN DES SLIDES--**