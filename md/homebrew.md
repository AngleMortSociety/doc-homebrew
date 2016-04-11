
# Homebrew

## Présentation

[Homebrew][] est un gestionnaire de paquets (on parle aussi de *formules*) pour OS X. En effet, par défaut, il n'est pas possible d'installer de nouveaux programmes en ligne de commande via le Terminal sur le système d'[Apple][] comme il est courant de le faire sur Linux avec des commandes telles que `apt-get` ou `aptitude`. Homebrew répond à cette problématique via la commande du Terminal `brew` qui se comporte de manière très similaire aux autres gestionnaires de paquets nommés précédemment. Homebrew installe les paquets dans leurs propres dossiers et crée des liens symboliques de leurs fichiers vers `/usr/local/`. Aucun fichier n'est installé en dehors de son préfixe et vous pouvez les placer où vous le souhaitez.

Notez qu’il existe d'autres programmes similaires :

- [MacPorts][], ou
- [Fink][]

Toutefois, Homebrew devient de plus en plus populaire, il est très léger, rapide et maniable.

## Pré-requis

Il est nécessaire d'avoir la configuration suivante pour utiliser Homebrew :

- Un Mac équipé d'un processeur Intel
- OS X 10.6 ou supérieur
- Xcode installé via le Mac App Store ainsi que sa licence acceptée (à l'ouverture du logiciel)
- Les outils de ligne de commande pour Xcode (*Command Line Tools for Xcode*) :  
    Il est possible de les installer avec la commande suivante (dans le Terminal) : `xcode-select --install`  
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

Attention, depuis El Capitan, il est nécessaire une fois l'installation terminée d'entrer la commande suivante :

``` bash
sudo chown -R $(whoami):admin /usr/local
```

Ceci permet d'apporter des modifications sur les droits de dossiers du système, ce qui rend possible l'installation des formules Homebrew.

## Mise à jour de Homebrew

Homebrew doit se mettre à jour avec les dépôts [GitHub][] afin de vous permettre de rechercher, d'installer ou de mettre à jour des formules, comme vous le feriez sous Linux avec ce genre de commandes : `apt-get update`.

``` bash
brew update
```

Il est à noter qu'il est nécessaire d'**exécuter cette commande** pour **chaque session** où vous auriez besoin d'utiliser Homebrew afin de récupérer les **dernières références disponibles**.

## Recherche

Pour vérifier si une formule est disponible :

``` bash
brew search <formule>
```

Il est possible d'utiliser une expression régulière pour rechercher une formule en l'entourant de slashs `/` :

``` bash
brew search /REGEX/
```

Afin de lister toutes les formules disponibles qu'il est possible d'installer avec Homebrew :

``` bash
brew search
```

Il existe aussi une interface web pour la recherche de formules : [Braumeister][].

## Installation de formules

Pour installer une formule :

``` bash
brew install <formule>
```

En cas de problème lors d'une installation, il est possible d'utiliser la commande suivante :

``` bash
brew doctor
```

Les messages d'erreurs vous aideront ainsi à trouver les problèmes à corriger.

## Suppression de formules

La désinstallation d'une formule se fait de la manière suivante :

``` bash
brew remove <formule>
```

En lieu et place de `remove` il est possible d'utiliser `rm` ou `uninstall` ainsi que l'option *--force*.

## Mise à jour des formules

Pour vérifier si des mises à jour sont disponibles pour les formules installées avec Homebrew :

``` bash
brew outdated
```

Voici les options disponibles :

| Option        | Détail                                                            |
| :------------ | :---------------------------------------------------------------- |
| *--quiet*     | Affiche uniquement les noms des formules à mettre à jour.         |
| *--verbose*   | Affiche les informations détaillées des formules à mettre à jour. |

Afin de mettre à jour toutes les formules :

``` bash
brew upgrade
```

Il est possible de ne mettre à jour que certaines formules :

``` bash
brew upgrade <formule>
```

Il est à noter que les options valides avec la commande `install` sont aussi disponibles avec cette commande `upgrade` (voir le manuel pour plus de détails).

## Diverses informations

Il est possible d'obtenir des informations sur une formule :

``` bash
brew info <formule>
```

La liste de toutes les formules installées avec Homebrew peut être connue avec la commande :

``` bash
brew list --versions
```

Pour plus d'informations sur Homebrew, lisez le manuel :

``` bash
man brew
```

Afin d'ouvrir le site Internet officiel de Homebrew dans le navigateur Internet par défaut du système d'exploitation :

``` bash
brew home
```

Il est également possible d'ouvrir le site Internet d'une formule :

``` bash
brew home <formule>
```

Afin de visualiser toutes les formules internes et externes relatives à Homebrew :

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
