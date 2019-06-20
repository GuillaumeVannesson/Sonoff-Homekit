# Sonoff Homekit

Ce micrologiciel rend le **Sonoff WIFI Smart Switch** compatible avec **Apple Homekit**!

<img src="https://raw.githubusercontent.com/Gruppio/Sonoff-Homekit/images/images/sonoffonly.png" alt="Sonoff" width="180"/> <img src="https://raw.githubusercontent.com/Gruppio/Sonoff-Homekit/images/images/transparent.png" alt=" " width="20"/><img src="https://raw.githubusercontent.com/Gruppio/Sonoff-Homekit/images/images/homekit.png" alt="Works with Apple Homekit" width="180"/>

### Homekit s'exécute sur le Sonoff ! 😳

Contrairement à d'autres projets sur github, ce micrologiciel ne nécessite RIEN d'autre pour fonctionner.
Il n'est pas basé sur Tasmota Fw, il ne requiert pas Homebridge sur un Raspberry-Pi ou un serveur MQTT , puisque HomeKit ne nécessite qu'une connexion Wi-Fi  et un appareil Apple !

Cette implementation utilise la spécification Homekit fournie par Apple pour les devellopeurs, donc le projet est stable et va fonctionner encore longtemps.

Maintenant vous pouvez avoir des appareils Homekit sans dépenser une fortune !

### Appareils compatibles
Ce logiciel est actuellement testé sur : **Sonoff Basic**, **Sonoff Slampher**, **Sonoff S26** (merci Arjan)

### Vidéo de démonstration

Clickez sur l'image pour jouer la vidéo:
<br>
<a href="http://www.youtube.com/watch?feature=player_embedded&v=_PLeu4v50h0
" target="_blank"><img src="http://img.youtube.com/vi/_PLeu4v50h0/0.jpg" 
alt="Video" width="480" height="270" border="10" /></a>

---

## Nouvelles fonctionnalités

### Interface HTTP
Pour contrôler votre Sonoff depuis un appareil non Apple, naviguez jusqu'à l'adresse IP du sonoff permettra de l'allumer ou l'éteindre.

### Rest APIs
Un ensemble complet d'AIP Rest est disponible:
* **/on**
* **/off**
* **/toggle**
* **/state**

Toutes les requètes sont de type **GET** et sont relative à l'adresse IP du Sonoff.
Afin de démarrer le Sonoff à l'IP 192.168.0.22, on peut exécuter la commande : `$ curl 192.168.0.22/on`

### Reconnexion automatique après une coupure de courant
Un problème avec l'ancien micrologiciel était qu'après une coupure de courant, le Sonoff  recherchait automatiquement la connexion WIFI enregistrée, mais puisque le routeur était encore alimenté, the Sonoff demandait la procédure de configuration. Maintenant ce problème est résolu , si le Sonoff n'a pas de connexion WIFI toutes les 10 minutes, le Sonoff redémarrera.

### État au démarrage sélectionnable
Par défaut le Sonoff aura un état activé à l'allumage, on peut changer cela en sélectionnant "OFF" dans le script `flash.sh`

---

## Instructions d'installation

### Flasher le Sonoff
 1) Débrancher le sonoff du secteur _(ou vous pouvez griller votre PC)_
 2) Connecter le Sonoff à un adaptateur série @ 3.3v
 3) Exécuter le script `flash.sh`

### Ajouter le Sonoff à l'application Maison
 1) Connectee l'iPhone ou l'iPad au nouveau réseau WIFI  `Sonoff Switch-xxx`
 2) Attendre le portail captif et selectionner le réseau WiFi du domicile
 3) Entrez votre mot de passe WiFi
 4) Ouvrir l'application `Maison`
 5) Appuyer sur le symbole `+`
 6) Appuyer sur  `Je n'ai pas de code...`
 7) Selectionnez l'interrupteur Sonoff-xxx 
 7.1 Si le Sonoff-xxx n'apparait pas en haut de la page, essayer d'appuyer le bouton du sonoff une paire de foi et fermer l'application `Maison`
 9) `Confirmer que l'on veut ajouter le Sonoff
 10) Saisir le mot de passe qui est `11111111`

Fini ! 🎉 

#### Special thanks to:
@maximkulkin
@Gruppio

Ce projet n'aurait pas existé sans :
https://github.com/Gruppio/Sonoff-Homekit
https://github.com/maximkulkin/esp-homekit
https://github.com/maximkulkin/esp-homekit-demo
https://github.com/maximkulkin/esp-wifi-config

