# QC-BBS Meshtastic Version

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/B0B1OZ22Z)

Le system QC-BBS avec Meshtastic devices. cd système gère les courriels, le bulletin board et quelques utilitaires
C'est une version francophone et adapter du système [TC²-BBS-Mesh]


### Requirements

- Python 3.x
- Meshtastic
- pypubsub

### Installation

1. Copiez le référentiel :

```sh
git clone https://github.com/TheCommsChannel/TC2-BBS-mesh.git
cd QC-BBS-mesh
```

2. Configurez un environnement virtuel Python :

```sh
python -m venv venv
```

3. Activez l'environnement virtuel :
  

- sur Windows:

```sh
venv\Scripts\activate
```

- sur macOS ou Linux:

```sh
source venv/bin/activate
```

4. Installez les packages requis :

```sh
pip install -r requirements.txt
```

5. Configurez la configuration dans `config.ini` :
   
**[interface]**

 Si vous utilisez « type = série » et que vous avez plusieurs appareils connectés, vous devrez décommenter la ligne « port = » et saisir le port de votre appareil.

 Exemple Linux :
 `port = /dev/ttyUSB0`

 Exemple Windows :
 `port = COM3`

 Si vous utilisez type = tcp, vous devrez décommenter la ligne hostname = 192.168.x.x et saisir l'adresse IP de votre appareil Meshtastic.

 **[sync]**

 Entrez dans une liste d'autres nœuds BBS avec lesquels vous souhaitez synchroniser les messages et les bulletins. Séparez chacun par une virgule et sans espace, comme indiqué dans l'exemple ci-dessous.
 Vous pouvez trouver le nodeID dans le menu sous « Configuration radio > Utilisateur » pour chaque nœud, ou utiliser ce script pour obtenir les données nodedb d'un appareil :

 [Meshtastic-Python-Examples/print-nodedb.py sur main · pdxlocations/Meshtastic-Python-Examples (github.com)](https://github.com/pdxlocations/Meshtastic-Python-Examples/blob/main/print -nodedb.py)

 Exemple de configuration :
 Example Config:
```ini
[interface]
type = serial
# port = /dev/ttyUSB0
# hostname = 192.168.x.x

[sync]
bbs_nodes = !f53f4abc,!f3abc123
```

### Exécution du serveur

Exécutez le serveur avec :

```sh
python server.py
```

Assurez-vous d'avoir suivi les étapes de l'environnement virtuel Python ci-dessus et de l'avoir activé avant de l'exécuter.

## Caractéristiques

- **Système de messagerie** : envoyez et recevez des messages électroniques.
- **Tableaux d'affichage** : publiez et consultez des bulletins sur divers tableaux.
- **Répertoire des chaînes** : ajoutez et affichez les chaînes dans le répertoire.
- **Statistiques** : affichez les statistiques sur les nœuds, le matériel et les rôles.
- **Mur de la honte** : affichez les appareils dont le niveau de batterie est faible.
- **Fortune Teller** : Obtenez une fortune aléatoire. Extrait du fichier fortunes.txt. N'hésitez pas à modifier ce fichier, à le supprimer ou à en ajouter d'autres si vous le souhaitez.

## Utilisation

Vous interagissez avec le BBS en envoyant des messages directs au nœud connecté au système exécutant le script Python. En lui envoyant un message, vous obtiendrez une réponse avec le menu principal.
Effectuez des sélections en envoyant des messages en fonction de la lettre ou du chiffre entre parenthèses - Envoyer M pour le menu [M]ail par exemple.

Une vidéo de son utilisation est disponible sur notre chaîne YouTube :

[![TC²-BBS-Mesh](https://img.youtube.com/vi/d6LhY4HoimU/0.jpg)](https://www.youtube.com/watch?v=d6LhY4HoimU)


## Merci

Un grand merci à [Meshtastic](https://github.com/meshtastic) et [pdxlocations](https://github.com/pdxlocations) pour les excellents exemples Python :

[python/examples chez master · meshtastic/python (github.com)](https://github.com/meshtastic/python/tree/master/examples)

[pdxlocations/Meshtastic-Python-Examples (github.com)](https://github.com/pdxlocations/Meshtastic-Python-Examples)

## Licence

Licence publique générale GNU v3.0
