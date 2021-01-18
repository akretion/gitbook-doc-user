---
description: appelé aussi "Liste de Matériel" ou "Bill of Material" en anglais.
---

# Nomenclatures

Une Nomenclature permet de gérer la composition d'un produit en définissant ses composants et leurs quantités.

Avec les modules principaux "Inventaire" et "Fabrication" installés il est possible de choisir entre deux types de Nomenclatures :

* **Fabriquer ce produit** : quand on souhaite **suivre le stock** du produit final.
* **Kit** : quand on ne souhaite **pas suivre le stock** du produit final.

![](../.gitbook/assets/image%20%28233%29.png)

{% hint style="info" %}
Le module [mrp\_subcontracting](https://github.com/OCA/manufacture/tree/12.0/mrp_subcontracting) permet d'ajouter un troisième type de Nomenclature pour **sous-traiter la fabrication** d'un produit final.

Les composants sont alors associés à un mouvement de stock de leur emplacement vers le sous-traitant et le produit final est associé à un mouvement de stock du sous-traitant vers son emplacement de réception.
{% endhint %}

## Fabriquer un produit et consommer ses composants

Pour augmenter la quantité en stock d'un produit qui a une Nomenclature de **type "Fabriquer ce produit"** il faut créer un _Ordre de Fabrication_,  dont les composants à consommer sont donnés par la _Nomenclature_ :

![](../.gitbook/assets/image%20%28224%29.png)

Il faut aussi que le produit soit :

* de type "_Produit stockable_" pour pouvoir suivre sa quantité en stock
* et que la route d'approvisionnement "_Produire_" soit sélectionnée afin de déclencher la création de cet _Ordre de Production_ lorsqu'une augmentation de stock est demandée \(cf [Routes d'approvisionnement](../routes-dapprovisionnement.md)\).

![](../.gitbook/assets/image%20%28232%29.png)

![](../.gitbook/assets/image%20%28231%29.png)

## Vendre un Kit

Lors de la vente d'un produit final associé à une _Nomenclature_ de **type Kit**,  on ne suivra que les mouvements de stock des composants \(de leur emplacement de stockage vers le client\) **sans créer de produit final** :

![Bon de Commande d&apos;une table en kit](../.gitbook/assets/image%20%28235%29.png)

![Bon de Livraison des composants du kit associ&#xE9; au Bon de Commande](../.gitbook/assets/image%20%28234%29.png)

## Nomenclatures imbriquées les unes dans les autres

Les composants d'une Nomenclature peuvent eux-mêmes être fabriqués \(ou assemblés\) à partir d'une _sous-Nomenclature_.

Si cette _sous-Nomenclature_ est de type "Fabriquer ce produit" \(et que les [routes d'approvisionnement](../routes-dapprovisionnement.md) "_Produire_" et "_Approvisionner à la commande_" du produit intermédiaire sont bien sélectionnées\), un sous-Ordre de Fabrication sera créé :

![](../.gitbook/assets/image%20%28226%29.png)

![Ordre de Fabrication du produit final](../.gitbook/assets/image%20%28225%29.png)

![sous-Ordre de Fabrication des composants](../.gitbook/assets/image%20%28230%29.png)

En revanche si cette _sous-Nomenclature_ est de type "Kit", alors les composants du Kit seront directement appelés dans l'Ordre de Fabrication du produit final sans avoir à fabriquer de produit intermédiaire :

![](../.gitbook/assets/image%20%28236%29.png)

![](../.gitbook/assets/image%20%28229%29.png)

