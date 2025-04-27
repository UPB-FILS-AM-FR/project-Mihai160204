| Auteur              | Information         |
|---------------------|---------------------|
| Mogoș Mihai-Dănuț | [GitHub Profile](https://github.com/Mihai160204) |

<h2>Coffre-fort électronique avec mot de passe et alarme utilisant Arduino Mega2560🔒</h2>

## Description

Dans un monde où la sécurité devient de plus en plus importante, le contrôle d’accès à l’aide de codes personnels est une solution pratique et sécurisée.
Ce projet implémente un coffre-fort électronique utilisant un Arduino Mega 2560, un clavier 4x4 pour la saisie du mot de passe et un servomoteur SG90 pour l'ouverture du coffre-fort.

Si le mot de passe correct est saisi, le coffre-fort s'ouvre et une LED verte s'allume. Dans le cas contraire, le système déclenche une alarme sonore à l'aide d'un buzzer actif et allume une LED d'avertissement rouge.

## Motivation

La sécurisation des biens personnels ou professionnels est devenue un enjeu essentiel dans notre société moderne. Alors que les solutions commerciales comme les coffres-forts électroniques existent en abondance, la création d'un système fait-maison apporte plusieurs avantages:

1) <b>Apprentissage approfondi:</b> En construisant un tel dispositif soi-même, on apprend activement comment fonctionnent les systèmes embarqués, les capteurs, les actionneurs, et les principes de sécurisation électronique.

2) <b>Flexibilité totale:</b> Contrairement aux produits standards, un coffre-fort Arduino peut être adapté à des besoins spécifiques: longueur du mot de passe, complexité du mécanisme, intégration de capteurs supplémentaires (capteur d'empreinte, capteur NFC, capteur Bluetooth).

3) <b>Coût réduit:</b> Utiliser des composants de base tels que des LED, des servomoteurs et un clavier permet de concevoir un système fiable à un coût bien inférieur à celui du marché.

4) <b>Développement des compétences STEM:</b> Ce projet implique des compétences en électricité, en mécanique, en programmation et en logique algorithmique, parfait pour tout étudiant ou passionné souhaitant enrichir ses compétences techniques.

## Architecture

Le système du coffre-fort électronique est structuré en trois grandes couches fonctionnelles, interconnectées de manière fluide pour assurer la détection, le traitement et la réponse:

1) <b>Détection des entrées utilisateur</b>

a) <b>Clavier 4x4:</b> Ce module capte la saisie manuelle de l'utilisateur. Chaque touche du clavier correspond à une combinaison spécifique de lignes et de colonnes, ce qui permet à l'Arduino de détecter quelle touche est pressée.

b) <b>Lecture séquentielle du mot de passe:</b> Chaque pression de touche est enregistrée dans un buffer temporaire jusqu'à ce que l'utilisateur termine sa saisie.

2) <b>Traitement de l'information</b>

a) <b>Carte Arduino Mega 2560: </b> Cœur du projet, l'Arduino compare le mot de passe saisi avec celui stocké en mémoire.

b) <b>Logique décisionnelle:</b> Si le code est correct, l’Arduino envoie un signal pour déverrouiller la serrure via le servomoteur, allume la LED verte et désactive l'alarme. Si le code est incorrect, l’Arduino active la LED rouge et déclenche une alarme sonore via le buzzer actif.

c) <b>Sécurité renforcée:</b> Le programme peut être facilement modifié pour intégrer des fonctions avancées : verrouillage après trois erreurs, temporisation de réinitialisation, ou notification à distance.

3) <b>Actionnement physique</b>

a) <b>Servomoteur SG90:</b> Actionne la gâche du coffre-fort en effectuant une rotation de 90° ou 180° selon la configuration.

b) <b>LED et buzzer:</b> Fournissent des retours visuels et sonores immédiats sur l'état du coffre, renforçant la sécurité et l'ergonomie pour l'utilisateur.

4) <b>Alimentation</b>

a) <b>Batterie 9V + module d'alimentation:</b> Fournit une autonomie suffisante pour une utilisation prolongée sans connexion USB permanente.

## Schéma électrique

![Schéma électrique]







## Composants

| Nombre | Appareil                                                                                                                                                                                    | Usage                                        | Prix unitaire (RON)  |  Prix total (RON)  |
|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|----------------------|--------------------|
|   1.   | [Arduino MEGA 2560 + cable USB](https://www.optimusdigital.ro/ro/compatibile-cu-arduino-mega/2560-placa-de-dezvoltare-compatibila-cu-arduino-mega-2560-atmega2560-ch340-si-cablu-50-cm.html?search_query=arduino+mega&results=107)                      | Microcontrôleur                              | 77.39                | 77.39              |
|   2.   | [Clavier 4x4](https://www.optimusdigital.ro/ro/senzori-senzori-de-atingere/470-tastatura-matriceala-4x4-cu-conector-pin-de-tip-mama.html?search_query=KEYPAD+4X4&results=4)	               | Saisie du code	                              | 6.99                 | 6.99               |
|   3.   | [Servo-moteur SG90](https://www.optimusdigital.ro/ro/motoare-servomotoare/26-micro-servomotor-sg90.html?search_query=servo+motor+sg90&results=11)	                                         | Mouvement mécanique du coffre	              | 13.99                | 13.99              |
|   4.   | [Buzzer actif 5V](https://www.optimusdigital.ro/ro/audio-buzzere/633-buzzer-activ-de-5-v.html?search_query=buzzer+activ&results=18)	                                                       | Signal sonore pour mot de passe incorrect    | 1.40                 | 1.40               |
|   5.   | [LED verte + LED rouge](https://www.optimusdigital.ro/ro/optoelectronice-led-uri/704-led-bicolor-de-3-mm-rosu-si-verde-cu-catod-comun.html?search_query=led+verde+si+rosu&results=58)       | Indicateurs d'état	                          | 0.99                 | 0.99               |
|   6.   | [Résistances 220Ω](https://www.ardumarket.ro/ro/product/12r-rezistenta-025w?gad_source=1&gbraid=0AAAAA-sic2THpYfHjQtxT-gGh5uNjzRU7&gclid=CjwKCAjwq7fABhB2EiwAwk-YbNMGppdCkNHmvr0KxCj4rfpuS-2DB0f-qqV8CVHxLQWQM2yVn0LbABoCSLAQAvD_BwE)	                                                                                                                                                                           | Protection pour LED	                        | 0.05                 | 0.05               |
|   7.   | [Breadboard 830 points](https://sigmanortec.ro/Breadboard-830-puncte-MB-102-p125923983)          | Montage des composants	                      | 11.07                 | 11.07               |
|   8.   | [Jeu de câbles M-M et M-F](https://sigmanortec.ro/40-Fire-Dupont-30cm-Tata-Mama-p210854349)	                                   | Connexions électriques	                      | 7.94x2               | 15.88              |
|        |                                                                                                                                                                                             |                                              |                      | Total: 127.72      |

## Référence

[YouTube Tutorial](https://www.youtube.com/watch?v=dDi6UTGd31k&ab_channel=ElectroSpark)

















  
