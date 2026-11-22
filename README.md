# Système intelligent de prêt de matériel à accès contrôlé

## Présentation du projet

Dans ce projet, on cherche à réaliser un système permettant aux étudiants d'emprunter des pinces d'électronicien tout en contrôlant les accès.

Le but est assez simple : savoir qui a emprunté une pince, laquelle a été prise et si elle a bien été rendue.

Le module est prévu pour accueillir **48 pinces, réparties sur 3 rangées de 16**, avec un type de pince par rangée.

## Fonctionnement envisagé

- L'étudiant présente son badge RFID pour s'identifier.
- Il choisit le type de pince qu'il veut emprunter à l'aide des boutons.
- Le système vérifie son autorisation et déverrouille un seul emplacement.
- Un capteur permet de détecter le retrait de la pince.
- Lors du retour, le système détecte la pince et doit pouvoir confirmer le verrouillage.
- Les emprunts et les retours doivent être enregistrés pour permettre leur suivi.

## Architecture étudiée

Pour la partie électronique, on prévoit notamment :

- **STM32F103RB** : gestion principale du système et des entrées/sorties.
- **ESP32 WT32-ETH01** : communication avec le réseau par Ethernet.
- **6 PCF8574** : lecture des 48 capteurs de présence, par I²C.
- **3 PCA9685** : génération des 48 signaux PWM pour les servomoteurs, par I²C.
- **48 servomoteurs** : commande des mécanismes de verrouillage.
- **Lecteur RFID, écran LCD 16×2 et 5 boutons lumineux** : interface avec l'utilisateur.
- **Bandeau LED** : indication de l'état du système.

Ces composants correspondent à l'architecture envisagée pour le moment. Le câblage et les choix mécaniques restent à vérifier au fur et à mesure du projet.

## Contenu du dépôt

Ce dépôt regroupe actuellement les documents de conception :

- [`Cahier_des_charges_pinces_3_pages.pdf`](Cahier_des_charges_pinces_3_pages.pdf) : cahier des charges au format PDF.
- [`Cahier_des_charges_pinces_3_pages.docx`](Cahier_des_charges_pinces_3_pages.docx) : version Word modifiable.
- [`Bilan_E_S.pdf`](Bilan_E_S.pdf) et [`Bilan_E_S.xlsx`](Bilan_E_S.xlsx) : bilan des entrées et sorties.
- [`Schema_synoptique.drawio`](Schema_synoptique.drawio) : schéma synoptique modifiable dans draw.io.
- [`Schema_synoptique.drawio.pdf`](Schema_synoptique.drawio.pdf) et [`Schema_synoptique.drawio.png`](Schema_synoptique.drawio.png) : exports du schéma.

Le code des microcontrôleurs pourra être ajouté ici au fur et à mesure de son développement. Il n'est pas encore présent dans ce dépôt.

## Partie mécanique

La modélisation mécanique est suivie dans un dépôt séparé :

[Voir le dépôt SolidWorks](https://github.com/Darkzveller/Soldiworks_Conception_et_realisation_d_un_systeme_intelligent_de_pret_de_materiel_a_acces_controle)

## Avancement

Le projet est encore en phase de conception. Les documents, le schéma et l'architecture électronique seront mis à jour à mesure que les choix seront validés et que les premiers essais seront réalisés.
