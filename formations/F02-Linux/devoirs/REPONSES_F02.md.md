F02 — Réponses aux questions : Fondamentaux Linux

Nom et prénom : Jamaelle Kerlane
Formation : 13Layers Academy
Module : F02 — Fondamentaux Linux

1. Linux

Linux est un système d'exploitation libre et open source qui permet à un ordinateur de fonctionner et de gérer ses ressources matérielles et logicielles.

Il faut distinguer trois éléments :

- Le noyau Linux : c'est la partie centrale du système. Il assure la communication entre les logiciels et le matériel de l'ordinateur.
- Une distribution Linux : c'est un ensemble comprenant le noyau, des logiciels et des outils permettant d'utiliser le système. Exemple : Ubuntu.
- Le terminal : c'est une interface qui permet de communiquer avec le système en utilisant des commandes écrites.

2. Système de fichiers

Les principaux répertoires Linux ont chacun un rôle particulier :

- "/" : c'est la racine du système. Elle contient tous les autres répertoires.
- "/home" : contient les dossiers personnels des utilisateurs et leurs fichiers.
- "/etc" : contient les fichiers de configuration du système et de certains logiciels.
- "/var/log" : contient les fichiers journaux qui enregistrent les événements et les activités du système.
- "/tmp" : sert à stocker temporairement des fichiers utilisés par les programmes.

3. Navigation

Les commandes de navigation permettent de se déplacer dans les répertoires et de connaître son emplacement.

- "pwd" : affiche le chemin du répertoire dans lequel on se trouve.
- "ls -la" : affiche les fichiers et dossiers, y compris les fichiers cachés, avec leurs informations détaillées.
- "cd .." : permet de remonter au répertoire parent.
- "cd ~" : permet de retourner directement dans le dossier personnel de l'utilisateur.

Exemple :

cd ~/Documents
pwd
ls -la
cd ..
cd ~

Ces commandes permettent d'accéder au dossier Documents, d'afficher son contenu, de remonter d'un niveau et de revenir au dossier personnel.

4. Manipulation des fichiers

Les commandes de manipulation permettent de créer, copier, déplacer et supprimer des fichiers ou des dossiers.

- "touch fichier.txt" : crée un fichier vide s'il n'existe pas.
- "mkdir -p dossier/sous-dossier" : crée un dossier et ses sous-dossiers.
- "cp fichier.txt copie.txt" : copie un fichier.
- "mv ancien.txt nouveau.txt" : déplace ou renomme un fichier.
- "rm fichier.txt" : supprime un fichier.

Précaution avec rm :

Il faut vérifier soigneusement le nom et le chemin du fichier avant de supprimer, car la suppression avec "rm" ne passe généralement pas par la corbeille et peut être difficile à annuler.

5. Visualisation

Les commandes de visualisation permettent de consulter le contenu des fichiers.

- "cat" : affiche directement tout le contenu d'un fichier. Elle est pratique pour les petits fichiers.
- "less" : permet de consulter un fichier progressivement, de faire défiler son contenu et de rechercher du texte. Elle est utile pour les fichiers volumineux.
- "head" : affiche les premières lignes d'un fichier. Par défaut, elle affiche les dix premières lignes.
- "tail -n 10" : affiche les dix dernières lignes d'un fichier.

Exemple :

cat notes.txt
less notes.txt
head notes.txt
tail -n 10 notes.txt

On choisit la commande selon la taille du fichier et la partie du contenu que l'on souhaite consulter.

6. Recherche et pipes

La commande "grep" permet de rechercher un mot ou une expression dans un fichier.

Le symbole "|", appelé pipe ou tube, permet d'envoyer le résultat d'une commande vers une autre commande.

Les redirections permettent d'enregistrer des résultats dans des fichiers :

- ">" : écrit un résultat dans un fichier en remplaçant son ancien contenu.
- ">>" : ajoute un résultat à la fin d'un fichier sans effacer son contenu précédent.

Exemple pour compter les lignes contenant ERROR :

grep "ERROR" app.log | wc -l

La commande "grep" recherche les lignes contenant ERROR, puis le pipe transmet ces lignes à "wc -l", qui compte le nombre de lignes.

7. Permissions

Sous Linux, les permissions définissent les actions autorisées sur les fichiers et les dossiers.

Les trois permissions principales sont :

- "r" (read) : autorise la lecture.
- "w" (write) : autorise la modification ou l'écriture.
- "x" (execute) : autorise l'exécution d'un fichier ou l'accès à un répertoire.

Chaque fichier possède notamment :

- Un propriétaire : l'utilisateur auquel appartient le fichier.
- Un groupe : un ensemble d'utilisateurs pouvant bénéficier de permissions particulières sur ce fichier.

Que fait chmod u+x script.sh ?

Cette commande ajoute le droit d'exécution au propriétaire du fichier "script.sh".

Pourquoi éviter chmod 777 ?

Parce que cette commande accorde les droits de lecture, d'écriture et d'exécution à tous les utilisateurs. Cela peut permettre à une personne non autorisée de modifier ou d'exécuter un fichier. Il est donc préférable d'accorder uniquement les permissions nécessaires.

8. Utilisateurs

Linux distingue plusieurs niveaux d'accès :

- Utilisateur normal : utilise le système avec des permissions limitées à ses propres droits.
- Root : est le compte administrateur principal. Il possède des privilèges très élevés sur le système.
- Sudo : est une commande qui permet à un utilisateur autorisé d'exécuter une commande avec les privilèges d'administration.

Pourquoi appliquer le principe du moindre privilège ?

Ce principe consiste à donner à chaque utilisateur uniquement les droits nécessaires pour accomplir son travail.

Cela permet de limiter les erreurs, les modifications non autorisées et les risques de sécurité.

9. Surveillance du système

Les commandes de surveillance permettent de vérifier l'état et les ressources d'un système Linux.

- "ps aux" : affiche les processus en cours d'exécution, avec des informations comme l'utilisateur, le PID et l'utilisation des ressources.
- "top" : affiche les processus en temps réel et permet de surveiller l'utilisation du processeur et de la mémoire.
- "df -h" : affiche l'espace disque utilisé et disponible dans un format lisible.
- "free -h" : affiche les informations sur la mémoire RAM utilisée, libre et disponible.
- "uname -r" : affiche la version du noyau Linux utilisé.

Ces commandes sont utiles pour surveiller les performances et détecter certains problèmes du système.

10. Bash et DevOps

Un script Bash est un fichier contenant plusieurs commandes Linux qui peuvent être exécutées automatiquement dans un ordre précis.

Il permet de regrouper plusieurs instructions afin d'éviter de les saisir manuellement à chaque utilisation.

Explication du shebang :

#!/usr/bin/env bash

Cette ligne indique au système que le fichier doit être interprété avec Bash. Elle permet de rechercher l'interpréteur Bash dans les chemins disponibles sur le système.

Deux exemples de tâches DevOps automatisables avec Bash :

1. La sauvegarde automatique de fichiers et de dossiers importants.
2. La surveillance de l'espace disque et des ressources du serveur.

L'utilisation de scripts Bash permet de gagner du temps, de réduire les erreurs humaines et de faciliter l'administration des systèmes.
