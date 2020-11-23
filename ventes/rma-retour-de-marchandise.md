---
description: 'Avec les modules "RMA" de l''OCA : https://github.com/OCA/rma'
---

# RMA - Retour de Marchandise

La création d'un objet "RMA" dans Odoo permet de suivre les actions prises lors du retour d'un produit par un client en 3 étapes :

1. Création d'un objet "RMA"
2. Réception \(du produit retourné\) liée à cet objet "RMA"
3. Choix entre Rembourser, Remplacer ou Renvoyer le produit retourné.

## Création d'un objet "RMA"

Il est possible de créer un objet "RMA" de plusieurs manières :

* soit **manuellement** depuis le menu RMA

![](../.gitbook/assets/image%20%2894%29.png)

* soit **depuis un mail** en définissant un alias de domaine pour les mails entrants \(permettant à Odoo de recevoir des mails\) et un alias de mail d'une équipe de RMA \(pour associer les emails envoyés à l'adresse `alias_equipe_rma@alias_domaine.com` à une création de RMA\)

![](../.gitbook/assets/image%20%2893%29.png)

![](../.gitbook/assets/image%20%2897%29.png)

* soit **depuis un** _**Bon de Commande**_ \(ayant une quantité de produit déjà livré\) avec le bouton "Create RMA" du module [rma\_sale](https://github.com/OCA/rma/tree/12.0/rma_sale) de l'OCA

![](../.gitbook/assets/image%20%2896%29.png)

* soit **depuis un mouvement de stock** sortant réalisé, avec le bouton "Retourner" et l'option "Create RMAs" cochée.

![](../.gitbook/assets/image%20%2895%29.png)

## Réception \(du produit retourné\) liée à cet objet "RMA"

Lorsqu'un RMA est confirmé, un mouvement de stock entrant "Receipt" est créé automatiquement :

![](../.gitbook/assets/image%20%2898%29.png)

Il faut alors confirmer le mouvement de stock de réception du produit retourné afin de faire apparaître les boutons des actions possibles :

![](../.gitbook/assets/image%20%2899%29.png)





