
## Quelques formules

### license

Génère des licences à partir de la ligne de commande.

#### Installation

Tout d'abord, il est nécessaire d'ajouter le dépôt suivant :

``` bash
brew tap nishanths/tap
```

Et enfin, installez la formule :

``` bash
brew install nishanths/tap/license
```

#### Licences disponibles

Afin d'afficher toutes les licences disponibles de cette commande, tapez la commande `license ls`, cette liste devrait s'afficher :

| Argument          | Type de licence                                       |
| :---------------- | :---------------------------------------------------- |
| agpl-3.0          | GNU Affero General Public License v3.0                |
| apache-2.0        | Apache License 2.0                                    |
| artistic-2.0      | Artistic License 2.0                                  |
| bsd-2-clause      | BSD 2-clause "Simplified" License                     |
| bsd-3-clause      | BSD 3-clause "New" or "Revised" License               |
| cc0-1.0           | Creative Commons Zero v1.0 Universal                  |
| epl-1.0           | Eclipse Public License 1.0                            |
| gpl-2.0           | GNU General Public License v2.0                       |
| gpl-3.0           | GNU General Public License v3.0                       |
| isc               | ISC License                                           |
| lgpl-2.1          | GNU Lesser General Public License v2.1                |
| lgpl-3.0          | GNU Lesser General Public License v3.0                |
| mit               | MIT License                                           |
| mpl-2.0           | Mozilla Public License 2.0                            |
| unlicense         | The Unlicense                                         |

#### Aide

Pour afficher l'aide de la commande :

``` bash
license help
```

#### Mettre à jour la commande

Il est préférable de mettre à jour toutes les commandes avec `brew update`. Néanmoins, si vous désirez mettre à jour uniquement cette commande :

``` bash
license update
```

#### Version

Afin de connaître la version de la commande installée actuellement sur votre système :

``` bash
license version
```

#### Options

Les options disponibles sont les suivantes :

| Option        | Signification | Détail                                                                                |
| :------------ | :------------ | :------------------------------------------------------------------------------------ |
| *-y*          | *year*        | Permet de préciser une année, par défaut l'année en cours.                            |
| *-n*          | *name*        | Permet de préciser un nom spécifique, par défaut l'utilisateur déclaré de `git`.      |
| *-o*          | *output*      | Inscrit le résultat dans un fichier, son nom doit alors être indiqué.                 |

#### Exemples

Pour obtenir une licence *MIT* :

``` bash
license mit 
```

Licence *mpl-2.0* enregistrée dans un fichier `LICENSE.txt` :

``` bash
license -o LICENSE.txt mpl-2.0
```

Pour demander une licence *isc* de 2013 au nom de *Alice* :

``` bash
license -y 2013 -n Alice isc
```

### youtube-dl

Cette commande permet de télécharger des vidéos uniques ou des listes de lecture provenant de Youtube.

Pour installer cette commande, rien de plus simple :

``` bash
brew install youtube-dl
```

Il suffit alors d'indiquer à cette commande l'adresse où se situe la vidéo que vous souhaitez récupérer :

``` bash
youtube-dl [adresse youtube]
```

#### Options

Les options disponibles sont les suivantes :

| Option        | Signification | Détail                                                                                            |
| :------------ | :------------ | :------------------------------------------------------------------------------------------------ |
| *-h*          | *help*        | Affiche l'aide complète de la commande.                                                           |
| *-U*          | *Update*      | Permet de récupérer la dernière version disponible, attention les droits admin sont nécessaires.  |
| *-i*          | *ignore*      | Continue le téléchargement tout en ignorant les erreurs éventuelles.                              |
| *--version*   | *version*     | Affiche la version de la commande installée actuellement sur votre système.                       |

Beaucoup d'autres options sont disponibles, vous pouvez les consulter avec l'option *h*, attention toutefois aux options dépréciées.

#### Exemples

Il est possible de limiter la bande passante à 50ko lors des téléchargements :

``` bash
youtube-dl [adresse youtube] --rate-limit 50K
```

Dans le cas du téléchargement d'une liste de lecture, vous pouvez ainsi renommer directement les fichiers à votre convenance avec l'option *o* (pour *output*) :

``` bash
youtube-dl [adresse youtube] -o "./%(playlist_index)s - %(title)s.%(ext)s"
```

Les fichiers seront nommés de cette façon : **01 - nom.extension**. Notez que le `./` indique de télécharger les fichiers dans le dossier courant.
