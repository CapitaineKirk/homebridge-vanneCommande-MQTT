# homebridge-vanneCommande-mqtt

<img src="https://github.com/CapitaineKirk/homebridge-vanneCommande-mqtt/blob/main/photos/HW-584.jpg" width=150 align="right" />  

## But

Envoyer des commandes au module HW-584 dans le cadre d'une integration dans homebridge d'un dispositif permettant de contrôler une vanne d'arrosage.
Ce module est équipé d'une connexion ethernet et de seize entrées/sorties configurables.  

Ce package crée deux accessoires:
- une vanne (valve)
- un interrupteur (switch)  

La vanne est couplée à l'interrupteur. Un changement de l'état de l'un fait changer l'état de l'autre.
La vanne permet à l'utilisateur de déclencher un arrosage avec un minuteur.
L'interrupteur permet de programmer des arrosages

## Remerciements
Merci à l'équipe homebridge (https://homebridge.io) pour la qualité de son travail.  
Merci à Michael Nielson (https://github.com/nielsonm236) pour son firmware alternatif pour le HW-584 (travail de pro, respect).

## Installation

1. Installez [homebridge](https://github.com/nfarina/homebridge#installation-details)  
2. Installez ce plugin: `npm install -g homebridge-VanneCommande-mqtt`  
3. Mettez à jour le fichier `config.json`  
4. Configurez le module HW-584 (voir la doc sur le site de Michael)

## Configuration

```json
"accessories": [
     {
       "accessory": "VanneCommande-mqtt",
       "name": "Lauriers",
       "module": "Module20",
       "port" : 1,
       "indice" : 1,
       "debug": 0
     },
     {
       "accessory" : "SwitchCommande-mqtt",
       "name" : "Arrosage Test",
       "indice" : 1,
       "debug": 0
     }
]
```

1. Vanne  

| Key | Description | Default |
| --- | --- | --- |
| `accessory` | Doit être `VanneCommande-mqtt` | N/A |  
| `name` | Nom qui apparaîtra dans l'application Home | N/A |  
| `module` | Nom déclaré dans la configuration du HW-584 | N/A |  
| `port` | Numéro de la sortie connectée à la commande d'ouverture/fermeture de la vanne | N/A |  
| `indice` | Numéro permettant le lien avec l'interrupteur | N/A  
| `dureeDemandee` | Durée (en seconde) de l'ouverture de la vanne | 900  
| `debug` | Active le mode verbeux | 0 |  

2. Interrupteur  

| Key | Description | Default |  
| --- | --- | --- |  
| `accessory` | Doit être `SwitchCommande-mqtt` | N/A |  
| `name` | Nom qui apparaîtra dans l'application Home | N/A |  
| `indice` | Numéro permettant le lien avec la vanne | N/A  
| `debug` | Active le mode verbeux | 0 |  
 

## Installation
Le but est de d'installer le module dans un environnement permettant un fonctionnement péren (c'est à dire, à l'abri de l'eau)
Cela sera décrit utltérieurement dans une documention qui sera publiée.

