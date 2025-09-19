# Refcard

## Raccourcis clavier Bash

CTRL + B: Recule d'un caractère
CTRL + F: Avance d'un caractère

CTRL + H: Supprime le caractère avant le curseur (équivalent de la touche Backspace)
CTRL + D: Supprime le caractère sous le curseur (équivalent de la touche Delete)

CTRL + J: Exécute la commande (équivalent de la touche Entrée)
CTRL + M: Exécute la commande (équivalent de la touche Entrée)

CTRL + I: Auto-complétion (équivalent de la touche Tab)

CTRL + @: Place un marqueur à la position actuelle du curseur
CTRL + X, CTRL + X: Échange la position du curseur avec le marqueur

CTRL + C: Interrompt la commande en cours
CTRL + Z: Met en pause la commande en cours
CTRL + A: Déplace le curseur au début de la ligne
CTRL + E: Déplace le curseur à la fin de la ligne
CTRL + U: Supprime tout avant le curseur
CTRL + K: Supprime tout après le curseur
CTRL + W: Supprime le mot avant le curseur (équivalent de ALT + Backspace)
CTRL + L: Efface l'écran (équivalent de la commande 'clear')
CTRL + D: Envoie un EOF (ferme le terminal)
CTRL + R: Recherche dans l'historique des commandes
CTRL + Y: Colle le texte précédemment coupé
CTRL + T: Échange le caractère sous le curseur avec le précédent
CTRL + G: Annule la recherche dans l'historique
CTRL + P: Rappelle la commande précédente dans l'historique
CTRL + N: Rappelle la commande suivante dans l'historique
CTRL + S: Bloque le terminal (désactive avec CTRL + Q)
CTRL + Q: Débloque le terminal
CTRL + S: Recherche dans l'historique des commandes (équivalent de CTRL + R)

ALT + <: Déplace le curseur au début de l'historique
ALT + >: Déplace le curseur à la fin de l'historique
ALT + N: Rappelle la commande suivante dans l'historique
ALT + P: Rappelle la commande précédente dans l'historique
ALT + U: Met en majuscule le mot après le curseur
ALT + L: Met en minuscule le mot après le curseur
ALT + C: Met en majuscule la première lettre du mot après le curseur
ALT + F: Avance d'un mot
ALT + B: Recule d'un mot
ALT + D: Supprime le mot après le curseur
ALT + . : Insère le dernier argument de la commande précédente
TAB: Auto-complétion des commandes et des fichiers

## Placeholders courants

~ : Répertoire personnel de l'utilisateur
. : Répertoire courant
.. : Répertoire parent
!! : Dernière commande
!n : Commande numéro n dans l'historique
$? : Code de retour de la dernière commande
$0 : Nom du script en cours d'exécution
!* : Tous les arguments de la dernière commande
^abc^123: Remplace 'abc' par '123' dans la dernière commande
`command` : Exécute une commande et remplace par sa sortie (obsolète, utiliser $())
`$(command)` : Exécute une commande et remplace par sa sortie (moderne)
`${var}`: Référence une variable
`{a,b,c}` : Expansion de séquence (ex: echo {1,2,3} affiche 1 2 3)
`{1..5}` : Expansion de séquence numérique (ex: echo {1..5} affiche 1 2 3 4 5)
`{a..e}` : Expansion de séquence alphabétique (ex: echo {a..e} affiche a b c d e)
`$(command1; command2)` : Exécute plusieurs commandes dans une sous-coquille
`$(command &)` : Exécute une commande en arrière-plan dans une sous-coquille
`$((expression))` : Évalue une expression arithmétique

## Redirections

`>` : Redirige la sortie standard vers un fichier (écrase le fichier)
`>>` : Redirige la sortie standard vers un fichier (ajoute à la fin du fichier)
`2>` : Redirige la sortie d'erreur vers un fichier (écrase le fichier)
`&>` : Redirige la sortie standard et la sortie d'erreur vers un fichier (écrase le fichier)
`&>>` : Redirige la sortie standard et la sortie d'erreur vers un fichier (ajoute à la fin du fichier)
`<` : Redirige l'entrée standard depuis un fichier
`<<` : Redirige l'entrée standard depuis une chaîne de texte (heredoc)
`<<<` : Redirige l'entrée standard depuis une chaîne de texte (here string)
`|` : Pipe, redirige la sortie standard d'une commande vers l'entrée standard d'une autre commande
`|&` : Pipe, redirige la sortie standard et la sortie d'erreur d'une commande vers l'entrée standard d'une autre commande
`2>&1` : Redirige la sortie d'erreur vers la sortie standard
`command1 | command2 | command3` : Chaîne de commandes avec pipes

## Commandes de base

uname -a : Affiche les informations système
date : Affiche la date et l'heure actuelles
cal : Affiche le calendrier du mois en cours
whoami : Affiche le nom de l'utilisateur courant

## Interaction avec le système de fichiers

pwd : Affiche le répertoire courant
ls : Liste les fichiers et répertoires
  `-l`: Affiche les détails (permissions, propriétaire, taille, date)
  `-a`: Affiche les fichiers cachés
  `-h`: Affiche les tailles en format lisible (Ko, Mo, Go)
  `-R`: Liste les répertoires de manière récursive
  `-t`: Trie par date de modification
  `-r`: Inverse l'ordre de tri
  `-Q`: Entoure les noms de fichiers de guillemets
  `-i`: Affiche les numéros d'inode
  `-d`: Affiche les répertoires eux-mêmes, pas leur contenu
  `-S`: Trie par taille
  `-1`: Affiche un fichier par ligne
cd [répertoire] : Change de répertoire
mkdir [nom] : Crée un nouveau répertoire
  `-p`: Crée les répertoires parents si nécessaire
  `-m [permissions]`: Définit les permissions du répertoire
rmdir [nom] : Supprime un répertoire vide
rm [fichier] : Supprime un fichier
  `-i`: Demande confirmation avant de supprimer chaque fichier
  `-f`: Force la suppression sans demander confirmation
  `-v`: Affiche les fichiers supprimés
  `-r` ou `-R`: Supprime les répertoires et leur contenu de manière récursive

cp [source] [destination] : Copie un fichier ou répertoire
  `-i`: Demande confirmation avant d'écraser un fichier existant
  `-f`: Force la copie en écrasant les fichiers existants sans demander confirmation
  `-v`: Affiche les fichiers copiés
  `-r` ou `-R`: Copie les répertoires et leur contenu de manière récursive

mv [source] [destination] : Déplace ou renomme un fichier ou répertoire

## Exécution de commandes

source [fichier] : Exécute les commandes d'un fichier dans le shell courant
./[fichier] : Exécute un fichier dans le répertoire courant (doit être exécutable)

## Consultation de fichiers

cat [fichier] : Affiche le contenu d'un fichier
less [fichier] : Affiche le contenu d'un fichier page par page
head [fichier] : Affiche les premières lignes d'un fichier
tail [fichier] : Affiche les dernières lignes d'un fichier
   `-n [nombre]`: Affiche les n premières/dernières lignes (ex: head -n 10)
   `-f`: Suit les ajouts en temps réel (ex: tail -f)

nano [fichier] : Ouvre un fichier dans l'éditeur de texte nano
vi [fichier] : Ouvre un fichier dans l'éditeur de texte vi
hexdump -C [fichier] : Affiche le contenu d'un fichier en hexadécimal
file [fichier] : Détermine le type d'un fichier
stat [fichier] : Affiche les informations détaillées d'un fichier
wc [fichier] : Compte les lignes, mots et caractères d'un fichier
diff [fichier1] [fichier2] : Compare deux fichiers ligne par ligne

## Manipulation de fichiers et flux

touch [fichier] : Crée un fichier vide ou met à jour la date de modification
echo [texte] : Affiche du texte à l'écran
  `-n`: N'ajoute pas de nouvelle ligne à la fin
  `-e`: Interprète les séquences d'échappement (ex: \n, \t)
cat > [fichier] : Crée un fichier et y écrit du texte (CTRL +
D pour terminer)
cat >> [fichier] : Ajoute du texte à la fin d'un fichier (CTRL +
D pour terminer)

## Variables d'environnement

`export VAR=valeur` : Définit une variable d'environnement
`echo $VAR` : Affiche la valeur d'une variable d'environnement
`env` : Affiche toutes les variables d'environnement
`printenv` : Affiche toutes les variables d'environnement
`unset VAR` : Supprime une variable d'environnement
`$PATH` : Affiche le chemin des exécutables
`$HOME` : Affiche le répertoire personnel de l'utilisateur
`$SHELL` : Affiche le shell par défaut de l'utilisateur
`$USER` : Affiche le nom de l'utilisateur courant
`$PS1` : Affiche le prompt du shell
`$PWD` : Affiche le répertoire courant
`$OLDPWD` : Affiche le précédent répertoire courant

## Gestion des processus

ps : Affiche les processus en cours
top : Affiche les processus en cours en temps réel
htop : Affiche les processus en cours en temps réel avec une interface améliorée (doit installer)
kill [PID] : Termine un processus par son PID
killall [nom] : Termine tous les processus portant le nom spécifié
bg : Reprend un processus en arrière-plan
fg : Reprend un processus en avant-plan
jobs : Affiche les processus en arrière-plan

## Compression/Décompression

Compresser/Décompresser un .tar.gz
tar -czvf archive.tar.gz [fichier/répertoire] : Crée une archive compressée
tar -xzvf archive.tar.gz : Extrait une archive compressée

Compresser/Décompresser un .zip
zip archive.zip [fichier/répertoire] : Crée une archive compressée
unzip archive.zip : Extrait une archive compressée

Compresser/Décompresser un .tar.xz
tar -cJvf archive.tar.xz [fichier/répertoire] : Crée une archive compressée
tar -xJvf archive.tar.xz : Extrait une archive compressée

Compresser/Décompresser un .7z
7z a archive.7z [fichier/répertoire] : Crée une archive compressée
7z x archive.7z : Extrait une archive compressée

Version moderne avec bsdtar (apt install libarchive-tools)

bsdtar -xf [archive] (Extrait tout type d'archive)
bsdtar -cf [archive] [fichier/répertoire] (Crée une archive .tar)
bsdtar -tf [archive] (Liste le contenu d'une archive)

## Permissions

chmod [options] [permissions] [fichier] : Change les permissions d'un fichier ou répertoire
chown [utilisateur]:[groupe] [fichier] : Change le propriétaire et le groupe d'un fichier ou répertoire
chgrp [groupe] [fichier] : Change le groupe d'un fichier ou répertoire
umask : Affiche ou définit le masque de création de fichiers
sudo [commande] : Exécute une commande avec les privilèges du superutilisateur
su [utilisateur] : Change d'utilisateur
who : Affiche les utilisateurs connectés
w : Affiche les utilisateurs connectés et leurs activités
id : Affiche l'UID et le GID de l'utilisateur courant
groups : Affiche les groupes de l'utilisateur courant
passwd : Change le mot de passe de l'utilisateur courant

1: x: Execution (ou traversal pour les répertoires)
2: w: Write
4: r: Read

chmod 755 fichier : rwxr-xr-x
chmod 644 fichier : rw-r--r--
chmod u+x fichier : Ajoute la permission d'exécution pour le propriétaire
chmod g-w fichier : Retire la permission d'écriture pour le groupe
chmod o=r fichier : Définit les permissions pour les autres à lecture seule
chmod a+x fichier : Ajoute la permission d'exécution pour tous

## Raccourcis less/more/man

Espace: Avance d'une page
b: Recule d'une page
Entrée: Avance d'une ligne
y: Recule d'une ligne
/: Recherche une chaîne de caractères
n: Recherche la prochaine occurrence
N: Recherche l'occurrence précédente
g: Va au début du fichier
G: Va à la fin du fichier
q: Quitte
h: Affiche l'aide
m: Place un marque-page à la position actuelle
' : Va au marque-page spécifié (ex: 'a pour aller au marque-page a)
` : Va au marque-page précédent
+ : Va à la ligne spécifiée (ex: +10 pour aller à la ligne 10)
- : Va à la ligne spécifiée depuis la fin (ex: -10 pour aller à la 10ème ligne depuis la fin)

## Git

git status : Affiche l'état du dépôt
git add [fichier] : Ajoute un fichier à l'index
git commit -m "message" : Crée un commit avec un message
git push : Pousse les commits vers le dépôt distant
git pull : Récupère les modifications du dépôt distant
git clone [url] : Clone un dépôt distant
git branch : Liste les branches
git checkout [branche] : Change de branche
git merge [branche] : Fusionne une branche dans la branche courante

## Recherche

grep "texte" [fichier] : Recherche du texte dans un fichier

`-P`: Utilise les expressions régulières Perl
`-r`: Recherche récursive dans les répertoires
`-i`: Recherche insensible à la casse
`-v`: Inverse la recherche (affiche les lignes qui ne correspondent pas)
`-n`: Affiche les numéros de ligne
`-c`: Compte le nombre de correspondances
`-l`: Affiche uniquement les noms des fichiers contenant des correspondances
`-w`: Recherche des mots entiers
`-A n`: Affiche n lignes après la correspondance
`-B n`: Affiche n lignes avant la correspondance
`-C n`: Affiche n lignes avant et après la correspondance
`-o`: Affiche uniquement les parties correspondantes

rg "texte" [répertoire] : Recherche du texte dans tous les fichiers d'un répertoire (doit installer), utilise PCRE by default.

`--json`: Affiche les résultats au format JSON

## Remplacement de texte

sed 's/ancien/nouveau/g' [fichier] : Remplace "ancien" par "nouveau" dans un fichier
  `-i`: Modifie le fichier en place
  `-n`: N'affiche pas les lignes par défaut (utilisé avec p pour afficher les lignes modifiées)
  `-e`: Permet d'exécuter plusieurs commandes sed
  `-r`: Utilise les expressions régulières étendues

perl -pe 's/ancien/nouveau/g' [fichier] : Remplace "ancien" par "nouveau" dans un fichier
  `-i`: Modifie le fichier en place
  `-n`: N'affiche pas les lignes par défaut (utilisé avec p pour afficher les lignes modifiées)
  `-e`: Permet d'exécuter plusieurs commandes perl
  `-l`: Gère automatiquement les nouvelles lignes

perl -0777 -pe 's/ancien/nouveau/gs' [fichier] : Remplace "ancien" par "nouveau" dans un fichier, même sur plusieurs lignes

## Utilitaires

`uniq [fichier]` : Supprime les lignes consécutives identiques dans un fichier
  `-c`: Préfixe les lignes par le nombre d'occurrences
  `-d`: Affiche uniquement les lignes dupliquées
  `-u`: Affiche uniquement les lignes uniques
  `-i`: Ignore la casse lors de la comparaison
`sort [fichier]` : Trie les lignes d'un fichier
  `-r`: Trie en ordre inverse
  `-n`: Trie numériquement
  `-k [n]`: Trie par la n-ième colonne
  `-u`: Supprime les doublons après le tri
  `-t [caractère]`: Utilise un caractère spécifique comme délimiteur de champ
`cut -d [délimiteur] -f [n] [fichier]` : Extrait la n-ième colonne d'un fichier
`awk '{print $n}' [fichier]` : Affiche la n-ième colonne d'un fichier
`xargs [commande]` : Construit et exécute des commandes à partir de l'entrée standard
    `-n [nombre]`: Nombre d'arguments par commande
    `-I {}`: Remplace {} par l'argument dans la commande
`tr` 'set1' 'set2' : Remplace les caractères de set1 par ceux de set2
  `-d`: Supprime les caractères de set1
  `-s`: Remplace les occurrences répétées par un seul caractère
`tee [fichier]` : Lit depuis l'entrée standard et écrit à la fois sur la sortie standard et dans un fichier
  `-a`: Ajoute à la fin du fichier au lieu de l'écraser
  `-i`: Ignore les interruptions (SIGINT)

## Aide

man [commande] : Affiche le manuel d'une commande
  `-k [terme]`: Recherche un terme dans les titres des pages de manuel
  `-f [commande]`: Affiche une brève description de la commande
apropos [terme] : Recherche un terme dans les titres des pages de manuel
whatis [commande] : Affiche une brève description de la commande
tldr [commande] : Affiche des exemples d'utilisation simplifiés (doit installer)

Section du manuel

1: Commandes utilisateur
2: Appels système
3: Fonctions de bibliothèque
4: Fichiers spéciaux (périphériques)
5: Formats de fichiers et conventions
6: Jeux et divertissements
7: Divers
8: Commandes d'administration système

## Réseau

ping [hôte] : Envoie des paquets ICMP à un hôte
  `-c [nombre]`: Nombre de paquets à envoyer
  `-i [secondes]`: Intervalle entre les paquets
  `-s [taille]`: Taille des paquets en octets
  `-t [TTL]`: Définit le Time To Live des paquets
  `-W [secondes]`: Temps d'attente maximum pour une réponse
ss -tuln : Affiche les connexions réseau et les ports d'écoute
  `-t`: Affiche les connexions TCP
  `-u`: Affiche les connexions UDP
  `-l`: Affiche uniquement les sockets en écoute
  `-n`: N'affiche pas les noms d'hôtes ou de services (affiche les adresses IP et numéros de port)
  `-p`: Affiche le PID et le nom du programme propriétaire de la socket
ip addr : Affiche les adresses IP des interfaces réseau
ip route : Affiche la table de routage

## Internet

wget [url] : Télécharge un fichier depuis une URL
  `-O [fichier]`: Enregistre le fichier sous un nom spécifique
  `-c`: Reprend un téléchargement interrompu
  `-q`: Mode silencieux (n'affiche pas la progression)
  `--limit-rate=[vitesse]`: Limite la vitesse de téléchargement (ex: 100k, 1m)
curl [url] : Transfère des données depuis ou vers une URL
  `-o [fichier]`: Enregistre la sortie dans un fichier
  `-O`: Enregistre le fichier avec son nom d'origine
  `-L`: Suit les redirections
  `-I`: Affiche uniquement les en-têtes HTTP
  `-d [données]`: Envoie des données dans une requête POST
  `-H [en-tête]`: Ajoute un en-tête HTTP personnalisé

## Environnements virtuels Python

uv venv [nom_env] : Crée un environnement virtuel
source [nom_env]/bin/activate : Active l'environnement virtuel
deactivate : Désactive l'environnement virtuel
pip install [package] : Installe un package dans l'environnement virtuel
pip uninstall [package] : Désinstalle un package de l'environnement virtuel
pip list : Liste les packages installés dans l'environnement virtuel
uv add [package] : Installe un package dans l'environnement virtuel
pipx install [package] : Installe un package globalement dans un environnement isolé (doit installer pipx)

## Gestionnaire de paquets (Debian/Ubuntu)

apt update : Met à jour la liste des paquets
apt upgrade : Met à jour les paquets installés
apt install [paquet] : Installe un paquet
apt remove [paquet] : Désinstalle un paquet
apt search [terme] : Recherche un paquet
apt show [paquet] : Affiche les informations d'un paquet
apt autoremove : Supprime les paquets inutilisés

`-y`: Répond automatiquement "oui" aux questions
`--purge`: Supprime les fichiers de configuration lors de la désinstallation

## Fun

cowsay [texte] : Affiche un texte avec une vache ASCII
fortune | cowsay : Affiche une citation aléatoire avec une vache ASCII (doit installer fortune)
sl : Affiche une animation de train (doit installer sl)
lolcat : Affiche du texte en couleur arc-en-ciel (doit installer lolcat)

## À installer

Manuel en français
sudo apt install manpages-fr manpages-fr-extra

Outils de développement
sudo apt install build-essential git curl wget vim htop

Outils réseau
sudo apt install net-tools iputils-ping traceroute dnsutils

## Substituts modernes

lsd : Substitut moderne de ls (doit installer)
batcat: Substitut moderne de cat avec coloration syntaxique (doit installer)
fd : Substitut moderne de find (doit installer)
ripgrep (rg) : Substitut moderne de grep (doit installer)
sd : Substitut moderne de sed (doit installer)
hexyl : Substitut moderne de hexdump (doit installer)
broot : Explorateur de fichiers en ligne de commande (doit installer)
fzf : Outil de recherche floue (doit installer)
git-delta : Substitut moderne de git diff avec coloration syntaxique (doit installer)
