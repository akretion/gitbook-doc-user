---
description: appelé aussi "Liste de Matériel" ou "Bill of Material" en anglais.
---

# Nomenclatures

Une Nomenclature permet de gérer la composition d'un produit en définissant ses composants et leurs quantités.

Avec les modules principaux "Inventaire" et "Fabrication" installés il est possible de choisir entre deux types de Nomenclatures :

![](../.gitbook/assets/image%20%28225%29.png)

* **Fabriquer ce produit** : quand on souhaite **suivre le stock** du produit final. Pour augmenter la quantité en stock de ce produit final il faut créer un _Ordre de Fabrication_,  dont les composants à consommer sont donnés par la _Nomenclature_ du produit final.
* **Kit** : quand on ne souhaite **pas suivre le stock** du produit final. Lors de la vente d'un produit final associé à une _Nomenclature_ de Kit,  on ne suivra que les mouvements de stock des composants \(de leur stock vers le client\) sans créer de produit final intermédiaire.

{% hint style="info" %}
Le module [mrp\_subcontracting](https://github.com/OCA/manufacture/tree/12.0/mrp_subcontracting) permet d'ajouter un troisième type de Nomenclature pour **sous-traiter la fabrication** d'un produit final.

Les composants sont alors associés à un mouvement de stock de leur emplacement vers le sous-traitant et le produit final est associé à un mouvement de stock du sous-traitant vers son emplacement de réception.
{% endhint %}

## Configuration des produits

Un produit associé à une Nomenclature de type "Fabriquer ce produit" devra être de type "Produit Stockable" :

![](../.gitbook/assets/image%20%28224%29.png)

Et de préférence 

## Nomenclatures imbriquées les unes dans les autres

