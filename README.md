# ansible-project-M1
Voici comment exécuter le playbook Ansible "Create Local Environment" depuis un Mac :
## Prérequis:

- Un terminal sur votre Mac
- Ansible doit être installé sur votre Mac (pour installer Ansible, utilisez la commande suivante : brew install ansible)
- Installer virutal box

## Instructions:

1. Ouvrez un terminal sur votre Mac.
2. Assurez-vous que vous êtes dans le répertoire où se trouve le playbook Ansible. 
2. Créer 2 dossiers : 1 dossier back et 1 dossier front
4. Dans le dossier front, créer un fichier .env dans lequel vous allez inscrire les lignes suivantes : 
```sh
    REACT_APP_API_URL=http://192.168.50.5:3005/api/
    REACT_APP_API_URL_IMAGE=http://192.168.50.5:3005/
```
5. Dans le dossier back, créer un fichier .env dans lequel vous allez inscrire les lignes suivantes : 
```sh
    NODE_ENV = production
    PORT = 3005
    MONGO_URI = mongodb+srv://EliotAlderson:TestBH-91@cluster0.gbvxg.mongodb.net/mernshop?retryWrites=true&w=majority
    JWT_SECRET = abc123
    PAYPAL_CLIENT_ID = AWnkyRgbahZXYvm4-FuCLzRrQMUdKKvn5ab9k2erIIyKNmWXyEt4blg5LlgZ69aN_kpIzOguQswwdCN6
    CLIENT_URL = "https://brilliant-licorice-c691cc.netlify.app"
```

6. Rendez-vous dans le fichier main.yml qui se trouve dans ROLE_FRONT/tasks/main.yml et à la ligne 13 indiquer le chemin du .env du front
7. Rendez-vous dans le fichier main.yml qui se trouve dans ROLE_BACK/tasks/main.yml et à la ligne 9 indiquer le chemin du .env du front
8. Exécutez la commande suivante pour lancer le playbook Ansible :
```sh
ansible-playbook -i inventaire.yml playbook.yml
```

Le playbook va exécuter les tâches suivantes dans la VM front et dans la VM back :

1. Installer Vagrant via Homebrew
2. Copier le fichier Vagrantfile dans le répertoire approprié
3. Installe et démarre les machines virtuelles (VMs) avec Vagrant
4. Dans la VM il git clone le projet front/back
5. Copie et colle les .env à la racine de l'application (back/front)
6. Déployer les conteneurs front-end et back-end 

> Note: Vous pouvez suivre la progression du playbook dans le terminal.

## Relancer le playbook
Dans le cas ou vous souhaiteriez relancer le playbook, pour une quelconque raison, il vous faudra supprimer les éléments suivants:
- Vagrantfile (à ne pas confondre avec Vagrantfile.j2)
- dossier .vagrant
- Et pour finir supprimer les VM qui ont été crée par Vagrant

✨ Et voila ! Vous avez lancé avec succès le playbook Ansible "Create Local Environment" depuis votre Mac.
