RAPPORT DES TRAVAUX PRATIQUES F02 — LINUX

Nom et prénom : Jamaelle Kerlane
Formation : 13Layers Academy
Module : F02 — Fondamentaux Linux

TP1 — Navigation et arborescence

Objectif

Créer une arborescence de dossiers et apprendre à se déplacer dans le terminal Linux.

Commandes utilisées

mkdir -p ~/13layers-F02
mkdir -p ~/13layers-F02/Projets ~/13layers-F02/Logs ~/13layers-F02/Scripts
pwd
ls -la

Questions et réponses

1. À quoi sert la commande pwd ?
Elle affiche le chemin absolu du répertoire courant.

2. À quoi sert ls -la ?
Elle affiche les fichiers et dossiers, y compris les éléments cachés, avec leurs informations détaillées.

3. À quoi sert mkdir -p ?
Elle permet de créer des dossiers et leurs sous-dossiers sans afficher d'erreur si le dossier existe déjà.

4. Quelle est la différence entre un chemin absolu et un chemin relatif ?
Un chemin absolu indique l'emplacement complet depuis la racine du système. Un chemin relatif indique l'emplacement à partir du répertoire courant.

TP2 — Manipulation des fichiers

Objectif

Créer, copier, renommer et afficher des fichiers.

Commandes utilisées

cat > Projets/notes.txt
cp Projets/notes.txt Logs/notes.txt
mv Logs/notes.txt Logs/notes-archive.txt
cat Logs/notes-archive.txt
ls -l Projets/notes.txt

Questions et réponses

1. Quelle est la différence entre cp et mv ?
La commande cp permet de copier un fichier tandis que mv permet de déplacer ou de renommer un fichier.

2. Comment vérifier que le fichier original existe toujours ?
On utilise ls -l Projets/notes.txt pour vérifier sa présence.

TP3 — Recherche et redirections

Objectif

Rechercher des informations dans un fichier et comprendre les redirections.

Commandes utilisées

cat > Logs/app.log
grep "ERROR" Logs/app.log
grep "ERROR" Logs/app.log | wc -l
echo "Première ligne" > Logs/test.txt
echo "Deuxième ligne" >> Logs/test.txt
cat Logs/test.txt

Résultats

La recherche avec grep a affiché les deux lignes contenant ERROR. Le comptage avec wc -l a retourné 2.

Le fichier test.txt contient deux lignes.

Questions et réponses

1. À quoi sert le symbole | ?
Il permet de transmettre le résultat d'une commande à une autre commande.

2. Quelle est la différence entre > et >> ?
Le symbole > écrit dans un fichier en remplaçant son contenu précédent. Le symbole >> ajoute du contenu à la fin du fichier sans effacer les données existantes.

TP4 — Gestion des permissions

Objectif

Comprendre les permissions Linux et exécuter un script Bash.

Commandes utilisées

cat > Scripts/demo.sh
ls -l Scripts/demo.sh
chmod u+x Scripts/demo.sh
./Scripts/demo.sh

Résultat

Le script a affiché : Bonjour 13Layers.

Questions et réponses

1. Que signifient les permissions rwx ?

- r : lecture.
- w : écriture.
- x : exécution.

2. Pourquoi éviter chmod 777 ?
Cette commande donne tous les droits à tous les utilisateurs. Elle peut donc présenter un risque de sécurité.

TP5 — Diagnostic du système

Objectif

Consulter les informations relatives à l'utilisateur, au noyau, au disque, à la mémoire et aux processus.

Commandes utilisées

whoami
uname -r
df -h
free -h
ps aux | head

Questions et réponses

1. Pourquoi examiner l'espace disque ?
Pour connaître l'espace utilisé et l'espace disponible afin d'éviter que le disque soit saturé.

2. Pourquoi surveiller la mémoire RAM ?
Pour connaître la quantité de mémoire utilisée et disponible et détecter une éventuelle saturation.

3. Pourquoi consulter les processus en cours ?
Pour identifier les programmes actifs et surveiller les ressources qu'ils utilisent.

TP6 — Automatisation avec Bash

Objectif

Créer un script permettant d'afficher automatiquement des informations sur le système.

Commandes utilisées

chmod u+x Scripts/system_info.sh
./Scripts/system_info.sh

Questions et réponses

1. À quoi sert le shebang #!/usr/bin/env bash ?
Il indique au système que le script doit être exécuté avec l'interpréteur Bash.

2. Pourquoi automatiser des tâches avec Bash dans DevOps ?
L'automatisation permet de répéter rapidement des opérations, de réduire les erreurs manuelles et de faciliter l'administration des systèmes.
