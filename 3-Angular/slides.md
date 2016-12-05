### Présentation AngularJS 1 et 2
29/11/2016

### Sources

### Sources (Miroirà

#### AngularJs 1
* angular-base.7z
* angular-common.7z

#### AngularJs 2
* angular2-gulp-starter.7z

## Concepts généraux

### Architecture 3/3

AngularJs se place en première ligne dans une architecture 3/3. Il consomme les données du backend et sert d’interface homme machine (IHM)

Les données sont consommées depuis le backend via des requêtes HTTP asynchrone,Ces données brut sont ensuite formatées en composants visuels (tableau, graphique …)Le backend expose des fonctions REST. Le frontend consomme ces données (généralement en format Json).

Les données sont persistées et récupérées ici. Le backend est utilisé pour effectuer les requêtes dans les bases de données (couche persistance) 

![Archi3-3](https://github.com/Binnette/CT2016/blob/master/3-Angular/assets/Archi3-3.png)

### Architecture MVVM

La vue est couplée aux données en DataBinding et invoque les méthodes du ViewModel.

Le ViewModel invoque les méthodes du modèle. Il contient les données spécifique à la gestion de l’écran et les méthodes de réponses aux interactions utilisateurs. Il contient également une référence vers une ou plusieurs modèles.

Le modèle contient les données et les méthodes (calculs, appels de services, …).

![Archi-MVVM](https://github.com/Binnette/CT2016/blob/master/3-Angular/assets/Archi-MVVM.png)

### Outils de développement

NodeJs : est un serveur d’application JavaScript. Il peut servir de Backend, servir des assets (html js css images) 

NPM (Node Package Manager) est l’outils de gestion des dépendances. Il sert aussi à lancer des commandes. Il est configuré via le fichier packages.json

Bower est un autre gestionnaire de dépendances mais uniquement pour des librairies front (angular, jquery, bootstrap …). Son utilisation est optionnel en complément de NPM.

Gulp / Grunt servent à automatiser des tâches (compilation, minification, copie de fichiers …)

## Angular 1

### Fondements

AngularJS est né en 2009 dans les locaux de Google. Deux développeurs du nom de Brad Green et Shyam Seshadri commençaient sérieusement à déprimer devant leur projet appelé "Google Feedback". 

Le projet contenait approximativement 17 000 lignes de code JavaScript et continuait à grossir. Ce qui le rendait de plus en plus difficile à maintenir et à tester.

C'est à ce moment-là que Shyam Seshadri proposa de redévelopper entièrement la solution avec un framework fait maison. Au bout de trois semaines, l'application ne comptait plus que 1 500 lignes de codes.

À compter de ce jour, les autres développeurs de l'équipe ont décidé de prendre en main ce framework et de travailler avec au quotidien. AngularJS est né.

### Principes fondamentaux

Architecture MVVM Une évolution du MVC facilitant l’implémentation du data binding et le découplage de l’application.

Data Binding : .Les données modifiées dans le controlleur ou component le sont directement dans la vue et vice-versa.

Injection de dépendances : tout comme l'architecture MVC, lorsque l'on parle d'injection de dépendances, on parle d'un concept prépondérant dans tout développement. Grâce à cela, les modules que vous développerez n'auront plus à se soucier d'instancier leurs dépendances.

La manipulation du DOM au moyen de directives : la manipulation du DOM conduit souvent à la création de code difficilement maintenable et difficilement testable. Nous verrons qu'avec Angular, ce n'est plus le cas du tout !

### Tests unitaires

Tous les éléments d’AngularJs sont testables (contrôleurs, directives, filters, services …)
Les tests unitaires utilisent les outils suivants : 

Karma orchestre le lancement des tests. Sa configuration se trouve dans karma.conf.js. 

PhantomJs est un navigateur Headless, c’est-à-dire utilisable en ligne de commande. Très utile lors d’une utilisation avec Jenkins par exemple 

Jasmine qui contient les outils d’ascertions « assert … »

ng-describe qui est préférable à describe permet d’écrire les tests en limitant le code boilerplate.
Le fichier « src/app/modules/config/config.components.spec.js »

### Architecture applicative

![Archi-app](https://github.com/Binnette/CT2016/blob/master/3-Angular/assets/Archi-app.png)

### Installation

Dans le projet angular-common lancer les commandes suivantes

```Bash
npm install
gulp build
npm test
```

Copier le résultat dans les dépendances de angular-base

```Bash
copy angular-common -> angular-base/node_modules
```

Dans le projet angular-base lancer les commandes suivantes

```Bash
npm install
npm install -g gulp
gulp build-dev
npm test
```

Lancement de l’application

```Bash
gulp server
```

### Ajouter un module fonctionnel

Création du module fonctionnel “monmodule”

Créer le répertoire suivant "src/app/modules/monmodule"

Créer les fichiers ci-dessous :

* src/app/modules/monmodule/monmodule.module.js
* src/app/modules/monmodule/monmodule.controller.js
* src/app/modules/monmodule/monmodule.tpl.html

Dans “src/app/app.js” ajouter 'app.monmodule‘ dans la liste des modules injectés
Dans “src/index.html” ajouter  monmodule.module.js monmodule.controller.js

Tester le résultat http://localhost:3000/angular-base/#!/monmodule

### Tests end to end

Le but des tests E2E est de lancer l’application dans un navigateur web pour obtenir les mêmes comportements qu’un utilisateur lambda. Ces tests sont utiles pour vérifier les interactions côté client, ainsi que le bon retour lors d’une action.

Pourquoi des tests E2E

* L’avantage des tests E2E est de pouvoir tester son application comme elle apparaîtra aux yeux de l’utilisateur.

Lancer les commandes suivantes :
```Bash
npm install -g protractor
npm install -g webdriver-manager
webdriver-manager update --standalone
webdriver-manager start
```

## Angular 2

### Fondements

Au travers d’Angular 2, Google cherche à faire table rase du passé, en remettant à plat de nombreux concepts présents dans Angular 1.

Cette stratégie a été motivée par 4 principes fondateurs :

Augmenter les performances : l’un des plus grands reproches qui ait été fait à Angular sont ses lacunes en termes de performance. Pour palier ce problème, les développeurs d’Angular ont décidé de se reposer davantage sur les briques natives du navigateur, comme par exemple, les WebComponents.

Améliorer la productivité : en affichant une syntaxe expressive basée sur la syntaxe de ES2015/TypeScript (annotations, import, types, …), plutôt que sur des surcouches, Angular 2 rompt avec une longue tradition de frameworks à boilerplate.

S’adapter au mobile : la conception modulaire du framework permet de réduire considérablement son empreinte mémoire sur les terminaux mobiles. Par ailleurs, il s’intègre avec les composants de « material design », ce qui permet la création d’applications dites « responsive » et multi-plateformes (téléphone, tablettes, ordinateur de bureau) ;

Embrasser les nouveaux standards du Web… en se basant sur des technologies telles que le ShadowDom, Observables et autres nouveautés apportées par ES2015. Angular 2 s’intègre par ailleurs parfaitement bien avec les composants construits via d’autres bibliothèques (Polymer, X-Tag, etc.).

### Rupture avec l’existant

Des « directives » aux « scopes », en passant par le « two-way data binding », Angular 2 n’en garde que les stigmates. Google nous offre ici un tout nouveau framework qui ne tient de son prédécesseur que le nom.
Voici une liste non exhaustive des concepts qui disparaissent :

« Two-way data binding » : la création de cycle dans le graphe de détection des changements impliquait de nombreux problèmes de performance et de compréhension.

« Controllers » : désormais, les contrôleurs font partie intégrante du contexte this des composants.

« Scope / RootScope » : l’ensemble des « scopes » sont maintenant liés au contexte this des composants ;

« Watch / Observe / Apply / Digest » : la détection des changements est effectuée par Zone.Js.

« module / directive / factory » : les dépendances sont injectées à partir d’annotations « Spring-like » et les imports sont effectués selon la syntaxe ES2015.

De nombreuses directives deviennent obsolètes (exemple : ng-hide, ng-show, etc.), mais certaines ont survécu au grand nettoyage. On retrouvera donc avec plaisir nos habituels if et for, bien que parfois renommés.

### TypeScript

TypeScript n’est pas imposé, mais son usage est encouragé car il apporte de nombreuses facilités de développement, comme par exemple une autocomplétion très poussée, pour peu que vous utilisiez un IDE digne de ce nom. Par ailleurs, en imposant une syntaxe plus stricte et un typage statique, TypeScript rend le code plus lisible et maintenable.

Tous les navigateurs modernes sont supportés. Angular 2 peut même tourner sur IE9, avec l’utilisation des polyfills. En revanche, il faut tirer un trait définitif sur les versions antérieures d’Internet Explorer.

Typescript peut être testé directement sur le navigateur via System.js mais doit transpiler du Javascript pour une utilisation en production. Cette tâche peut être automatisée avec Gult ou Grunt.

### Architecture applicative

![Archi-app2](https://github.com/Binnette/CT2016/blob/master/3-Angular/assets/Archi-app2.png)

### Migration

La migration d’Angular 1 vers Angular 2 est automatisable mais pas entièrement.

En lieu et place des controllers, implémentez des components : il est en effet possible de basculer vos .directive() en .component() (présent dans Angular 1.5) .

Supprimez les références à $scope, ces derniers disparaissent. Attachez vos variables au this pour les rendre accessibles dans vos templates et utilisez l’attribut controllerAs des directives .

Privilégiez les services : en sortant un maximum de logique métier vers les services, vous gagnerez un temps non négligeable lors de la migration de vos directives .

Enfin migrer le code en TypeScript.

Une piste de migration pour les grosses applications : ajoutez Angular 2 à vos dépendances et migrez progressivement vos composants à mesure que vous devez leur apporter des modifications / améliorations.

### Installation

Lancer les commandes suivantes

```Bash
npm install -g typings
npm install
```

Lancer le backend NodeJs
```Bash
gulp backend
http://localhost:5000
```

Build avec l’environnement de dev
```Bash
gulp serve-dev
gulp
http://localhost:3000
http://localhost:3001
```

Juste compiler
```Bash
gulp build
```

Build avec l’environement de prod
```Bash
gulp serve-prod
http://localhost:3010
http://localhost:3011
```

Tests unitaires
```Bash
npm test
```

### Ajouter un module fonctionnel

Créer le répertoire suivant "mkdir src/app/monmodule"

Créer les fichiers suivants :

* src/app/monmodule/index.ts
* src/app/monmodule/monmodule.component.ts
* src/app/monmodule/monmodule.css
* src/app/monmodule/monmodule.html
* src/app/monmodule/monmodule.module.ts
* src/app/monmodule/monmodule.routes.ts
* src/app/app.module.ts

Dans le fichier src/app/app.module.ts
```Javascript
import { MonModule } from './monmodule/monmodule.module';

imports: [
…
MonModule
],
```

Tester le résultat
```Bash
http://localhost:3000/monmodule
```

**--FIN DES SLIDES--**