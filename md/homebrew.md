
# Homebrew

## Présentation

[Homebrew][] est un gestionnaire de paquets pour OS X. En effet, par défaut, il n'est pas possible d'installer de nouveaux programmes en ligne de commande via le Terminal sur le système d'[Apple][] comme il est courant de le faire sur Linux avec des commandes telles que `apt-get` ou `aptitude`. Homebrew répond à cette problématique via la commande du Terminal `brew` qui se comporte de manière très similaire aux autres gestionnaires de paquets nommés précédemment. Homebrew installe les paquets dans leurs propres dossiers et crée des liens symboliques de leurs fichiers vers `/usr/local/`. Aucun fichier n'est installé en dehors de son préfixe et vous pouvez les placer où vous le souhaitez.

Notez qu’il existe d'autres programmes similaires à Homebrew :

- [MacPorts][], ou
- [Fink][]

Toutefois, Homebrew devient de plus en plus populaire, il est très léger, rapide et maniable.

## Installation

Il est nécessaire de copier/coller la ligne suivante dans le Terminal (les droits *admin* ne sont pas nécessaires) :

``` bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## Mise à jour des paquets

Pour récupérer la dernière version de Homebrew et de toutes ses commandes sur Github :

``` bash
brew update
```

Attention, il est nécessaire d'exécuter cette commande quand on souhaite chercher, installer ou mettre à jour des paquets avec Homebrew.

Pour vérifier si des mises à jour sont disponibles pour les commandes installées avec Homebrew :

``` bash
brew outdated
```

| Option 		| Détail 															|
| :------------	| :----------------------------------------------------------------	|
| *--quiet*		| Affiche uniquement les noms des paquets à mettre à jour.			|
| *--verbose*	| Affiche les informations détaillées des paquets à mettre à jour.	|

Afin de mettre à jour toutes les commandes :

``` bash
brew upgrade
```

Il est possible de mettre à jour uniquement certaines commandes :

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

## Installation de paquets

Pour installer un paquet :

``` bash
brew install <paquet>
```

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

Il est également possible d'ouvrir le site Internet d'une commande installée avec Homebrew :

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
[CakeBrew]: https://www.cakebrew.com "CakeBrew - Site officiel"
