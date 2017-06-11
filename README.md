# Installation
- Créer une VM : <code>docker-machine create -d virtualbox <i>machine_name</i></code>
- Créer un répertoire <code>app</code> qui contiendra le code de votre application
- Ajouter le répertoire <code>app</code> dans les dossiers partagés de la VM
- Se connecter en SSH sur la machine : <code>docker-machine ssh <i>machine_name</i></code>
- Créer un fichier <code>sudo vi /var/lib/boot2docker/bootlocal.sh</code> qui contiendra les lignes suivantes :
- - mkdir /home/docker/app/</li>
- - mount -t vboxsf -o uid=1000,gid=50,umask=0000 app /home/docker/app<br>
- Ce dossier sera utilisé pour la configuration <strong>volumes</strong> du docker-compose<br>
- Enregistrer puis redémarrer la VM
