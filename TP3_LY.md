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

### 9. Oui on peut accèder à une session en tant qu'alice
```console
User@localhost:~$ sudo passwd alice
User@localhost:~$ su alice
