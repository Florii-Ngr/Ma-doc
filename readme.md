# Documentation

## Convention BEM
* B  => Block
* E => Element
* M => Modifier


```html
<ul class="mainList mainList--xmas">
  <li class="mainLis_item">
    <!-- _itemLink = Element -->
    <a class="mainList_itemLink mainList_itemLink--isActive" href="/home"> home </a>
 </li>
 <li class="mainLis_item">
   <!-- _itemLink = Element -->
   <a class="mainList_itemLink" href="/about"> About</a>
</li>
<li class="mainLis_item">
  <!-- _itemLink = Element -->
  <a class="mainList_itemLink" href="/works"> Works</a>
</li>

</ul>
```

```css
.mainList{
  display: flex;
  justify-content: space-between;
  &__item{
    background: green;

  }
  &__item{
    list-style: none;

  }
  &__itemLink{
    color: red;
    &--isActive{
      color: white;
    }
  }
}
```

<!--Exemple en CSS du rendu-->
```css
.mainList{
  display: flex;
  justify-content: space-between;
}
.mainList--xmas{

}
.mainLis_item{
    background: green;
      list-style: none;
}
.mainList_itemLink{
    color: red;
}
.mainList_itemLink--isActive{
  color: white;
}
```
## Les pseudo attributs
Les pseudo attribut 'before / after' permettent de créé des noeud HTML en CSS.
Ils sont essentielement utilisés pour ajouter des ornement, des décoration etc..
On peut entendu faire des animations avec, les positionner par rapport a leurs parents (relative/ absolute). **Ils doivent obligatoirement avoir un 'content: '' `**
afin de s'afficher.




```HTML

<section class="cover">

  <h1 class="cover_mainTitle"> presentation des pseudo-attributs </h1>

</section>
```
```CSS
.cover{
  background: #FDFDFD;
  padding: 20px;
  &_mainTitle{
    text-align: center;
    font-size: 24px;
    color: green;
    position: relative;
    &::before,
    &::after{
      position: absolute;
      content:'';
      display: block;
      width: 50px;
      height: 50px;
      background: green;
      position: relative;
      top: 0;
      }
      &::before{
        left: 0;
      }
      &::after{
        right: 0;
      }
    }
  }
}
```

## REM, EM, %, VW Sising

### %

### EM
* Relative a la taille de son parent direct.
### REM
```CSS
.cover{
  font-size: 16px;/* 1OO% = 12px*/
  &_mainTitle{ /* 1em = 12px/ 0.8m <> 16px */
    font-size: 0.8em;
  }
}
```


* Le REM est base sur la taille de la racine ( soit la balise <html>) qui, par defaut a une valeur de 16px. Afin d'eviter tous calcul,
il est necessaire de l'ecraser en donnant une base de 10px soit 62.5%.

* Le REM est interessant a utiliser si les medi-queries employer sont en REM egalement.
Cela vous permettra egalement de garder des proportion égales lorsqu'on va redimensionner la page.

* Ses proportion seront égalemnet garder quand l'utilisateur zoomera dans voter page.
```css
html{
  font-size: 62.5%;  
}
```
```CSS
html{

  font-size: 62.5%;
}
.__mainTitle{
  font-size: 1.6em
  width: 32em;
}

```

### VW(idth)/ VH(eight)

* Unité relative à la taille de votre ecran (peu importe le device)
* Attention au VH et a son contenu. 100vH <> 100v quoi qu'il arrive .
* VW : treds utile pour les interface fluide

## Liens utiles :
*




### parcel avec npm

Dans le terminale :

### installer parcel

npm install -g parcel-bundler

### Creer un fichier package.json

npm init -y

Parcel peut prendre n'importe quel type de fichier comme point d'entrée, mais un fichier HTML ou JavaScript est un bon point de départ. Si vous liez votre fichier JavaScript principal dans le code HTML en utilisant un chemin relatif, Parcel le traitera également pour vous et remplacera la référence par une URL dans le fichier en sortie.



### Définition :

Convention : façon de faire du css avec des "règles" et des normes à suivre (nom des classes etc...)


### SASS ( Syntactical Awesome Stylesheets)

les flexboxgrid

col-xs-(nombre de colonnes) : Mobile

col-md-(nombre de colonnes) : Tablette

col-lg-(nombre de colonnes) : Desktop

ALIGNEMENTS

.start- : à gauche

.center- : au millieu

.end- : à droite

(Plus ou moins)

LES FLEX direction

flex-direction : row; = affiche les élément en ligne
flex-direction : column; = affiche les elements en colonnes
flex-wrap : wrap; = affiche les élémrnt sur 2 colonnes



les @mixins : On définit un mixin avec la directive @mixin, suivie d'un nom unique que vous choisissez. Les accolades contiennent les déclarations de styles qui constituent le mixin

exemple:

*/ @mixin mixin-name {
  margin: 0;
  padding: 0;
} /*

### CSS dans parcel

Crée un dossier "components" dans styles dans ce dossier il y aura TOUS les fichiers CSS de votre projet puis dans le fichiers "style.scss" écrire /*@import './components/nom_du_fichier_CSS';*/  

L'avantage de "découper" son CSS est plus facile pour éviter de tout casser son CSS chaque partie est independante.

### Installation dépendances pour framework JS dans parcel (React, Preact et VUE)

### React

/* Ajoutez un script de démarrage à package.json

package.json
"scripts": {
  "start": "parcel index.html"
} */

npm install --save react
npm install --save react-dom
npm install --save-dev parcel-bundler

### Preact

npm install --save preact
npm install --save preact-compat
npm install --save-dev parcel-bundler
npm install --save-dev babel-preset-env
npm install --save-dev babel-preset-preact

/* Ensuite, assurez-vous que la configuration Babel suivante est présente.

 .babelrc
{
  "presets": ["env", "preact"]
}
Ajoutez un script de démarrage à package.json

// package.json
"scripts": {
  "start": "parcel index.html"
} */

/* Ajoutez un script de démarrage à package.json

 package.json
"scripts": {
  "start": "parcel index.html"
} */

### VUE

npm install --save vue
npm install --save-dev parcel-bundler


/* Ajoutez un script de démarrage à package.json

 package.json
"scripts": {
  "start": "parcel index.html"
}



## Définition :

Convention : façon de faire du css avec des "règles" et des normes à suivre (nom des classes etc...)

## Keyframes

Définition : La règle @ @keyframes permet aux auteurs de définir les étapes qui composent la séquence d'une animation CSS. Cela permet de contrôler une animation plus finement que ce qu'on pourrait obtenir avec les transitions.

Exemple :


```css
.arrow {
    text-align: center;
    animation-name: floating; /* Nom de l'animation */
    animation-duration: 1.5s;
    animation-iteration-count: infinite;
    animation-timing-function: ease-in-out;
  }
  @keyframes floating { /* Nom de l'animation (pour appeler l'animation dans l'élément')*/
    from {
      transform: translate(0, 0px);
    }

    65% {
      transform: translate(0, 15px);
    }

    to {
      transform: translate(0, -0px);
    }
  }
  ```
