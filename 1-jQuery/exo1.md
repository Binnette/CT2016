# jQuery - Exo 1

## 1.a - jQuery est de partout ! (ou presque)
- Ouvrez une page internet au hazard (Google, wikipédia, etc)
- Appuyez sur la touche F12 depuis Google Chrome
- Cliquer sur l'onglet Console
- Saisir $ puis la touche Entrée

Si undefined est affiché alors jQuery n'est pas utilisé par ce site.
Sinon jQuery, une de ses mouture ou l'un de ces clones est installé.

Pour voir la version de jQuery
- Saisir $.fn.jquery puis la touche Entrée

Exemple de résultat sur fr.wikipedia.org : "1.11.3"
jQuery 1.11.3 est donc utilisé par Wikipédia.

## 1.b - Injecter jQuery sur dans une page
- Ouvrir https://code.jquery.com/jquery-3.1.1.min.js dans un onglet du navigateur
- Copier le contenu de cette onglet ( il s'agit du code JS minifié de jQuery)
- Trouvez une page web sans jQuery (par exemple : https://github.com)
- Appuyer sur la touche F12
- Cliquer sur l'onglet Console
- Coller le texte, puis appuyer sur la touche Entrée
- Saisir $ ou $.fn.jquery
- Résultat "3.1.1". C'est bon, jQuery est injecté sur la page
- Vous pouvez l'utiliser

## 1.c - Les sélecteurs
- Toujours sur la même page
- Tester les différents selector https://api.jquery.com/category/selectors/
- Exemples :
- $("div") / $("span") / $("p") / $("h1")
- $(".bold") / $(".title") / $(".main")
- $("#id) / $("#login") / $("#password")
- Si vous n'avez pas trop d'idée vous pouvez explorer le code de la page en cliquant sur l'onglet "Elements"
- Vous pouvez également utiliser l'icône flèche à gauche de l'onglet Element pour pointer un element dans la page. En cliquant cous accéder au code HTML de cet élément
- Ajouter des filtres dans vos sélecteurs
- Exemples : $("div:visible") / $("span:empty") / $("p:even") / $(".bold:visible") / $("div:hidden")
- Tester les sélecteurs multiples
- Exemple $("div, span, p")
- Chainer vos sélecteurs
- Exemples $("#id.bold") / $("span.bold:visible") / $(".bold.italic")

## 1.d Les manipulations
- Reprenez vos précédent sélecteurs
- Tester les différentes fonctions de manipulation https://api.jquery.com/category/manipulation/
- Ajouter supprimer une class css
- Exemple $("div").addClass("bold") / $("div").removeClass("bold")
- Tester si un élement a une class css particulière
- $("#id").hasClass("bold") ce qui revient plus ou moins à $("#id.bold")
- Obtenir la valeur "value" d'un élément
- Exemple $("input").val()
- Si aucune valeur n'est retournée, vous pouvez toujours en affecter une
- Exemple $("input:visible").val("TESTTESTTEST")
- Quelque part dans la page TESTTESTTEST va apparaitre dans un champ input
- Obtenir la valeur d'un attribut particulier
- Exemple $("a").prop("href")
- Modifier les attributs d'un élément
- Exemple $("a").prop("href", "http://google.fr")
- Modifier le css
- Exemple $("\*").css("color", "red") / $("div").css("font-weight", "bold")
- Il existe des raccourcis pour certaines propriétés
- Exemple $("\*").height("10px") / $("\*").width("10px")
- Obtenir la position d'un élément
- Supprimer des éléments
- Exemple $("a").remove() / $("div").remove() / $("body").empty()
- Ajouter des élements
- Exemple $("body").append("test") / $("a").append("<button>Clik</button>")
- Modifier le contenu d'un élément
- $("button").text("bouton") / $("button").html("btn") 
- Le plus part de ces fonctions peuvent s'utiliser en 'Getters" pour obtenir une valeu
- Exemples $("a").css("color") / $("a").width() / $("a").text()
