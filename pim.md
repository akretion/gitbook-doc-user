---
description: Gestion centralisée des informations sur les produits
---

# PIM - Product Information Management

Modules développés principalement par [Akretion](http://akretion.com) et [ACSONE](http://acsone.eu) comme partie du projet d'e-commerce open-source [Shopinvader](https://shopinvader.com/) : [https://github.com/shopinvader/odoo-pim/](https://github.com/shopinvader/odoo-pim)

## Objectif

✨ Regrouper dans une même application la gestion des informations sur les produits.

![](.gitbook/assets/image%20%2826%29.png)

## Attributs et Jeux d'Attributs de produits

🗄️ La fonctionnalité principale apportée par cet ensemble de module est la possibilité de créer et d'organiser autant d'**Attributs de produits** que l'on souhaite, sans préjudicier la vitesse d'accès aux données. 

En créant un _Attribut de produit_, on crée un nouveau champ disponible pour tous les produits appartenant au même **Jeu d'Attribut**, et visible dans l'onglet "_Attributs_" de la fiche du produit :

![Attributs d&apos;un produit du Jeu d&apos;Attributs &quot;Meuble&quot;](.gitbook/assets/image%20%2835%29.png)

### Création d'un Attribut

Un **Attribut** peut être un champ déjà existant dans Odoo \(_Natif_\) ou créé pour l'occasion \(_Custom_\) et peut être de n'importe quel **type** \(booléen, texte, sélection multiple...\)

![](.gitbook/assets/image%20%2841%29.png)

{% hint style="info" %}
Un Attribut de type "_Binaire_" est un fichier ou une image.
{% endhint %}

🗂️ ****Un Attribut appartient nécessairement à un **Groupe d'Attribut** \(lors de l'affichage de la fiche produit, tous les attributs du même Groupe seront affichés ensemble\) et peut être présent dans plusieurs **Jeux d'Attributs** à la fois \(p.ex. le même attribut "_Consommation Électrique_" peut se retrouver à la fois dans les Jeu d'Attribut "_Frigo_" et dans "_Ordinateur_"\).

⚡ L'option "_**Sérialisé**_" est à cocher en cas de grosse base de donnée \(plus d'une centaine d'attributs\) afin de ne pas ralentir la vitesse de l'accès aux informations lors de l'appel des données. Tous les attributs "_Sérialisés"_ seront regroupés dans le même objet JSON dans une seule colonne de la table SQL des produits dans la base de donnée, ce qui permet de ne pas alourdir inutilement la table des produits avec des centaines de colonnes vides la plupart du temps.

### Les Attributs de type _Sélection_ ou _Sélection Multiple_

📚 Les **Options** possibles d'un Attribut de _Sélection_ ou de _Sélection Multiple_ peuvent être soit **créées de toute pièce**, soit définies en pointant **certains Objets d'un même type** existant dans Odoo \(c'est-à-dire des objets d'un même "_Modèle_" dans Odoo\). 

Pour que les _Options_ d'un Attribut de _Sélection_ pointent vers des objets existants dans Odoo, il suffit de sélectionner le **Modèle Associé** de l'Attribut puis d'ajouter les _Options_ soit manuellement via le bouton "_Choisir les Options de l'Attribut_", soit en définissant un _Domaine_ avec la [syntaxe propre à Odoo](http://www.erpish.com/odoo/how-to-use-domains-to-filter-data-records-in-odoo/).

![](.gitbook/assets/image%20%2843%29.png)

### Complétude d'un Jeu d'Attribut

🌡️Il est possible de déterminer si les informations d'un produit sont **complètes ou non** grâce aux attributs choisis dans la liste **Complétude** du _Jeu d'Attribut_ de ce produit :

![](.gitbook/assets/image%20%2822%29.png)

Pour chaque élément de la liste **Complétude** on peut déterminer quel est le **taux de complétude** apporté par le remplissage de cet attribut dans une fiche produit.

{% hint style="info" %}
La somme des _Taux de Complétude_ doit être obligatoirement égale à 100.
{% endhint %}

Par exemple ici, si seuls les champs "_Pays de destination possibles_" et "_Description Technique_" sont remplis, les informations du produit ne seront "_remplies qu'à 25%_" :

![](.gitbook/assets/image%20%2833%29.png)

La liste des attributs à compléter étant disponible en tête de l'onglet "_Attributs_".

{% hint style="warning" %}
Il est possible que certaines informations ne s'affichent pas directement quand on change la valeur d'un Jeu d'Attribut d'un produit ou qu'on rempli un  champ à compléter.

🔄 Dans ces cas, il faut penser à **rafraîchir la page de son navigateur** afin de synchroniser les données affichées avec les données réellement enregistrées en base de donnée.
{% endhint %}















