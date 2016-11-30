# jQuery - Exo 2

##2.a - Créer une appli jQuery

- Créer un nouveau fichier index.html
- L'éditer avec notepad++
- Coller le code suivant :

```html
<html>
<body>
    <h1>Helloworld</h1>
    Saisissez votre pseudo : <input id="pseudo" />
    <button onclick="DireBonjour()">Cliquez ici</button>

    <script src="http://code.jquery.com/jquery-3.1.1.min.js" type="text/javascript"></script>
    <script type="text/javascript">
        function DireBonjour() {
            var pseudo = "euh";
            //vortre code jQuery ici
            // Il faut récupérer la valeur de l'input et l'affecter à 
            alert("Bonjour " + pseudo + " !");
        }
    </script>
</body>
<html>
```

- Ouvrir le fichier avec Chrome
- Saisir son pseudo dans le champ
- Appuyer sur le bouton
- Malheureusement l'application n'affiche pas votre pseudo!
- Corriger le problème !

## 2.b - Améliorer l'appli

- Le but du jeu est de transformer l'application en livre d'or
- Utilisez le code ci-dessous :

```html
<html>
<head>
    <style>
    table {
        border-collapse: collapse;
    }
    table, th, td {
        border: 1px solid black;
    }
    table tr:nth-child(even) {
        background-color: #ccc;
    }
    </style>
</head>
<body>
    <h1>Helloworld</h1>
    Saisissez votre pseudo : <input id="pseudo" />
    <button onclick="DireBonjour()">Cliquez ici</button>
    
    <br><hr><br>

    <table>
        <tr>
            <th>Pseudo</th>
            <th>Commentaire</th>
        </tr>
        <tr>
            <td>Binnette</td>
            <td>Pas terrible le design de ce site</td>
        </td>
        <tr>
            <td>Binnette</td>
            <td>Je suis le seul utilisateur ?</td>
        </tr>
    </table>
    <script src="http://code.jquery.com/jquery-3.1.1.min.js" type="text/javascript"></script>
    <script type="text/javascript">
        function AjouterCommentaire() {
            var pseudo = "euh";
            //vortre code jQuery ici
        }
    </script>
</body>
<html>
```

- Ajouter un champ texte éditable avec un label "Commentaire" (input type="text")
- Implémenter le comportement suivant : lorsque l'on clique sur le bouton, une nouvelle ligne est ajoutée dans le tableau. Cette ligne contient les informations saisies par l'utilisateur.
- Comportement supplémentaire : une fois le commentaire ajouté dans le tableau, vider les champs saisissables
- Comportement supplémentaire : on clique sur le bouton, ajouter un texte "Commentaire ajouté !" qui disparaît au bout de 3 secondes
- Indice : vous aurez besoin de la fonction setTimeout 
- Comportement supplémentaire : ajouter une colonne dans le tableau avec un bouton "supprimer" par ligne du tableau. Ce bouton permet de supprimer le commentaire
- Comportement supplémentaires : à vous d'en inventer ! :)
