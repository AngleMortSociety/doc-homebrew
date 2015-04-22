
# Homebrew

## Présentation

[Homebrew][] est un gestionnaire de paquets pour OS X. En effet, par défaut, il n'est pas possible d'installer de nouveaux programmes en ligne de commande via le Terminal sur le système d'[Apple][] comme il est courant de le faire sur Linux avec des commandes telles que `apt-get` ou `aptitude`. Homebrew répond à cette problématique via la commande du Terminal `brew` qui se comporte de manière très similaire aux autres gestionnaires de paquets nommés précédemment. Homebrew installe les paquets dans leurs propres dossiers et crée des liens symboliques de leurs fichiers vers `/usr/local/`. Aucun fichier n'est installé en dehors de son préfixe et vous pouvez les placer où vous le souhaitez.

Notez qu’il existe d'autres programmes similaires à Homebrew :

- [MacPorts][], ou
- [Fink][]

Toutefois, Homebrew devient de plus en plus populaire, il est très léger, rapide et maniable.

## Pré-requis

Il est nécessaire d'avoir la configuration suivante pour utiliser Homebrew :

- Un Mac équipé d'un processeur Intel
- OS X 10.6 ou supérieur
- Les outils de ligne de commande pour Xcode (*Command Line Tools for Xcode*) :  
	Il est possible de les installer avec la commande suivante :  
	`xcode-select --install`  
	Ou de télécharger ces outils à l'adresse suivante : <https://developer.apple.com/downloads>
- Un Terminal compatible Bourne-Shell (*bash* ou *zsh*)

Si vous devez installer des paquets qui nécessitent l'utilisation des composants X11, il est nécessaire d'installer [XQuartz][].

De plus, si vous devez utiliser des paquets nécessitant [Java][], il faudra installer ce logiciel et entrer la commande suivante dans le Terminal :

```Bash
Java Developer Update
```

## Installation

Il est nécessaire de copier/coller la ligne suivante dans le Terminal (les droits *admin* ne sont pas nécessaires) :

``` bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Mise à jour de Homebrew

Homebrew doit se mettre à jour avec le dépôt [GitHub][] afin de vous permettre de rechercher, d'installer ou de mettre à jour des paquets, comme vous le feriez sous Linux avec ce genre de commandes : `apt-get update`.

``` bash
brew update
```

Il est à noter qu'il est nécessaire d'exécuter cette commande pour chaque session où vous auriez besoin d'utiliser Homebrew afin de récupérer les dernières références disponibles.

## Mise à jour des paquets

Pour vérifier si des mises à jour sont disponibles pour les commandes installées avec Homebrew :

``` bash
brew outdated
```

Voici les options disponibles :

| Option 		| Détail 															|
| :------------	| :----------------------------------------------------------------	|
| *--quiet*		| Affiche uniquement les noms des paquets à mettre à jour.			|
| *--verbose*	| Affiche les informations détaillées des paquets à mettre à jour.	|

Afin de mettre à jour toutes les commandes :

``` bash
brew upgrade
```

Il est possible de ne mettre à jour que certaines commandes :

``` bash
brew upgrade <paquet>
```

Il est à noter que les options valides avec la commande `install` sont aussi disponibles avec cette commande `upgrade`.

## Recherche

Pour vérifier si un paquet est disponible :

``` bash
brew search <paquet>
```

Il est possible d'utiliser une expression régulière pour rechercher un paquet en l'entourant de slashs `/` :

``` bash
brew search /REGEX/
```

Afin de lister tous les paquets disponibles qu'il est possible d'installer avec Homebrew :

``` bash
brew search
```

Il existe aussi une interface web pour la recherche de paquets : [Braumeister][].

## Installation de paquets

Pour installer un paquet :

``` bash
brew install <paquet>
```

En cas de problème lors d'une installation, il est possible d'utiliser la commande suivante :

``` bash
brew doctor
```

Les messages d'erreurs vous aideront ainsi à trouver les problèmes à corriger.

## Suppression de paquets

La désinstallation d'une commande se fait de la manière suivante :

``` bash
brew remove <paquet>
```

En lieu et place de `remove` il est possible d'utiliser `rm` ou `uninstall` ainsi que l'option *--force*.

## Diverses informations

Il est possible d'obtenir des informations sur un paquet :

``` bash
brew info <paquet>
```

La liste de toutes les commandes installées par Homebrew peut être connue avec la commande :

``` bash
brew list --versions
```

Pour plus d'informations sur la commande :

``` bash
man brew
```

Une option permet d'ouvrir le site Internet de `brew` dans le navigateur par défaut du système d'exploitation :

``` bash
brew home
```

Il est également possible d'ouvrir le site Internet d'une commande :

``` bash
brew home <paquet>
```

Afin de visualiser toutes les commandes internes et externes relatives à `brew` :

``` bash
brew commands
```

La version courante de Homebrew installée sur le système peut être connue avec la commande :

``` bash
brew --version
```

Il existe une interface graphique qui permet d'utiliser Homebrew, il s'agit de [CakeBrew][].

[Homebrew]: http://brew.sh/index_fr.html "Homebrew - Site officiel"
[Apple]: http://www.apple.com/fr "Apple - Site officiel"
[MacPorts]: https://www.macports.org "MacPorts - Site officiel"
[Fink]: http://finkproject.org "Fink - Site officiel"
[XQuartz]: https://xquartz.macosforge.org/landing/ "XQuartz - Site officiel"
[Java]: http://www.oracle.com/technetwork/java/javase/downloads/index.html "Java - Site officiel"
[GitHub]: https://github.com "GitHub - Site officiel"
[CakeBrew]: https://www.cakebrew.com "CakeBrew - Site officiel"
[Braumeister]: http://braumeister.org "Braumeister - Site officiel"
