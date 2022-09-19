## Exercice 1

1. `sudo groupadd dev;sudo groupadd infra` crée deux groupes, dev et infra

2. `sudo useradd -m -s /bin/bash LOGIN` Crée des utilisateurs avec leurs dossiers personnels, et bash comme interpréteur de commande

3. `sudo usermod -a -G GROUPNAME NAME` permet d'ajouter un utilisateur à un groupe

4. `getent group GROUPNAME` ou `grep '^GROUPNAME:' /etc/group` permet de lister les membres d'un groupe

5. `sudo chgrp GROUPNAME FILENAME` permet de changer le groupe propriétaire d'un fichier

6. `sudo usermod -g GROUPNAME USERNAME` permet de changer le groupe primaire d'un utilisateur

7. `sudo mkdir /home/dev; sudo chgrp dev /home/dev; sudo chmod g=rw /home/dev` permet de créer un fichier dev dans home, de l'attribuer au groupe dev et d'autoriser sa modification à tous les membres de dev

8. `sudo chmod g+t /home/dev` permet de n'autoriser que le propriétaire du d'un fichier à le renommer ou le supprimer

9. Non, car le compte est incatif, puisqu'il n'a pas de mdp

10. `sudo psswd alice` permet de changer le mdp de l'utilisateur alice, `su alice` permet de s'y connecter

11. En se connectant sur le compte d'alice, puis en tapant `id`, on peut obtenir l'uid et le gid d'alice

12. `id 1003` permet d'identifier l'utilisateur avec l'uid 1003

13. `ut -d: -f3 < <(getent group dev)` permet d'obtenir le gid du groupe dev

14. `getent group 1002` permet d'obtenir le group dont le gid est 1002 (Dev)

15. `sudo gpasswd -d USERNAME GROUPNAME` permet d'enlever un utilisateur d'un groupe, mais on ne peut pas enlever un utilisateur de son groupe primaire (question 6)

16. `sudo chage -m 5 -M 90 -W 14 -E 2021-06-01 -I 30 dave` permet de modifier le compte dave, pour qu'il expire le 1er juin 2021, qu'il doive changer son mdp tous les 90 jours maximum, qu'il soit averti 14 jours avant la datel imite, que son compte soit bloquéé 30 jours après la limite, et qu'il doive attendre 5 jours entre chaque changement de mdp

17. `getent passwd root` permet de savoir que root utilisae bash comme interpréteur

18. Le compte nobody est un compte avec un nombre minimal de permission, utile pour se connecter sur des services vulnérables, et minimiser l'impact sur le système en cas de hack

19. Sudo conserve le mot de passe en mémoire pendant 15 minutes par défaut, la commande `sudo -k` permet de forcer sudo à oublier le mot de passe


# Exercice 2

1. `ls -l test` -> -rw-rw-r--
    `ls -l fichier` - -rw-rw-r--

2. `chmod 000 fichier; sudo nano fichier; sudo cat fichier` permet de supprimer tous les droits sur le fichier, puis de le modifier et de l'afficher en tant que root, ce qui est possible. Root permet donc de surpasser les droits d'un fichier

3. La commande `>` a besoin des droits en écriture pour fonctionner

4. On ne peut pas exécuter le fichier, en utilisateur ou avec sudo, car il ne s'agit pas d'un fichier exécutable

5. `chmod u-r ~/test; ls; cat fichier; chmod u+r ~/test` le droit de lecture dans un dossier permet de voir les fichiers contenus dedans, mais pas d'y acceder (r permet de le faire)

6. Il est possible de modifier le fichier avec les droits d'écriture dessus, mais ils ne sont pas nécessaires pour le supprimer

7. Les droits d'exécution sur un répertoire permettent d'y acceder et d'y rajouter ou supprimer des fichiers

8. Les droits s'appliquent sur tous les répertoires, même le répertoire courant, au moment où ils sont changés

9. `chmod g=r fichier` 

10. 

11. 

12. 

13. 

14. 

15. 

16. 