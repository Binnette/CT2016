# Bootstrap - Exo 1

## 1.a - Convertir le livre d'or en appli Bootstrap

- Le but de l'exercice est de  convertir notre précédente application en Boostrap
- Pour rappel, le livre d'or possède 2 champs (pseudo et commentaire) et un bonton "Commenter" qui permet d'ajouter le commentaire dans une "table".
- Repartez d'un fichier html vide
- Copier dans ce fichier le "Basic template" http://getbootstrap.com/getting-started/#template
- Ouvrez votre fichier html dans Google Chrome...
- Il manque pas mal de choses.
- Rajouter un menu http://getbootstrap.com/components/#navbar-default
- Personalisez le en remplacant "Brand" par le nom de votre appli
- Rajouter un jumbotron http://getbootstrap.com/components/#jumbotron
- Ce jumbottron contiendra les champs et le bouton
- Ajouter le champ pseudo http://getbootstrap.com/css/#forms-horizontal
- Ajouter le champ texte http://getbootstrap.com/css/#textarea
- Ajouter le bouton http://getbootstrap.com/css/#forms-horizontal
- En dessous du jumbottron, ajouter la table des commentaires http://getbootstrap.com/css/#tables-striped


## 1.b Vers une single page application

- le but de l'exercice est de "rajouter une page" dans notre application, mais sans créer un nouveau fichier html
- Encapsulez le jumbottron et la table des commentaire dans une div
- Mettre un id à cette div "livre-d-or"
- Ajoutez un style "display:none" sur la div
- Créer une nouvelle div avec l'id "accueil"
- Ajouter un peu de texte dans cette div
- Implémenter le comportement suivant :
- Au clic sur la navbar "brand", affichez la div accueil
- Au clic sur la navbar "lien livre d'or" (à créer), affichez la div livre-d-or
- Indice : utilisez les fonctions hide et show de jQuery pour afficher la bonne div lors du clic sur les boutons du menu http://api.jquery.com/category/effects/basics/

## 1.c Utilisation de la grille

- Dans votre nouvelle page d'accueil nous allons ajouter du contenu grâce à la grille http://getbootstrap.com/css/#grid
- Ajouter une ligne dans votre grille.
- Ajouter 2 cellules dans cette ligne.
- Ces cellules devront s'afficher horizontalement en version desktop et verticallement en version Mobile
- Ajouter une nouvelle ligne avec 2 cellules de 12 colonnes
- La permière cellule sera visible uniquement en desktop et l'autre uniquement en mobile

## 1.d Rajouter un thème

- Chercher une image pleine de couleur sur le web
- Copier l'url de cette image
- Renseigner cette url sur le site http://www.lavishbootstrap.com/
- Cliquer sur le bouton Go Lavish
- Si le thème vous plaît, cliquez sur "Download lavish-bootstrap.css"
- Inclure ce fichier css dans votre fichier html
- On peut obtenir une vrai application comme celle-ci : http://binnette.github.io/homebank-converter/
