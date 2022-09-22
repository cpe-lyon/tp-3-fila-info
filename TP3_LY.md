# Exercice 1. Gestion des utilisateurs et des groupes

### 1. Creation de groupe **dev** et **infra** :
```console
User@localhost:~$ sudo groupadd dev
User@localhost:~$ sudo groupadd infra
```

### 2. Creation des utilisateurs **alice**, **bob**, **charlie** et **dave**:
```console
User@localhost:~$ sudo useradd NomUtilisateur
```

### 3. Ajouter un utilisateur existant au groupe:
```console
User@localhost:~$ sudo gpasswd -a NomUtilisateur NomGroupe
Adding user NomUtilisateur to group NomGroupe 
```

### 4. Donnez deux moyens d’afficher les membres de infra

**Une première méthode:**
```console
User@localhost:~$ getent group infra
```
**Une deuxième méthode:**
```console
User@localhost:~$ grep infra /etc/group
```

### 5. Groupe propriétaire des repertoire
```console
User@localhost:~$ sudo usermod -m -d NomGroupe NomUtilisateur
```

### 6. Remplacer le groupe primaire
- dev pour alice et bob
```console
User@localhost:~$ sudo usermod -g dev NomUtilisateur
```
- infra pour charlie et dave
```console
User@localhost:~$ sudo usermod -g infra NomUtilisateur
```

### 7. Créez deux répertoires /home/dev et /home/infra  pour le contenu commun aux membres de chaque dfjggroupee, et mettez en place les permissions leur permettant d’écrire dans ces dossiers.

- creation des repertoires
```console
User@localhost:~$ sudo mkdir /home/dev
User@localhost:~$ sudo mkdir /home/infra
```
- gestion des permissions
```console
User@localhost:~$ sudo chmod 060 /home/dev
User@localhost:~$ sudo chmod 060 /home/infra
```

### 8. Permission, seul le propriétaire d’un fichier ait le droit de renommer ou supprimer ce fichier 
```console
User@localhost:~$ sudo chmod 750 /home/dev
User@localhost:~$ sudo chmod 750 /home/infra
```
### 9. 
Oui car on est connecté en tant que root, et peut modifier le mot de passe.

### 10. Activer le compte d'Alice
```console
User@localhost:~$ sudo passwd alice
User@localhost:~$ su alice
```

### 11. Obtenir l’uid et le gid de alice
```console
User@localhost:~$ id alice
```

### 12. Retrouver l’utilisateur dont l’uid est 1003
```console
User@localhost:~$ getent passwd 1003
```
### 13. Quel est l'id du group dev
```console
User@localhost:~$ grep dev /etc/group
```

### 14. Quel groupe a pour gid 1002 ?
```console
User@localhost:~$ grep 1002 /etc/group
```

### 15. Retirez l’utilisateur charlie du groupe infra
```console
sudo gpasswd - d charlie infra
```
Charlie n'a plus de droit pour le dossier infra.

### 16. Modifiez le compte de dave 
```console
User@localhost:~$ sudo chage -E 2021-06-01 -m 90 -M 5 -W 14 -I 30 dave
```
### 17. 
L'interprêteur de commande est **bash**.

### 18. Rôle de Nobody
Nobody n'appartient à aucun fichier, il n'est dans aucun groupe qui a des privilèges et dont les seules possibilités sont celles que tous les "autres utilisateurs" ont.

### 19.
Par défaut sudo le conserve pendant 15 mins.

# Exercice 2. Gestion des permissions

1. 

2. 
