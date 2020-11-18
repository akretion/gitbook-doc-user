# Liste de Prix de vente

Les listes de prix de ventes permettent de vendre un même produit avec des prix différents suivant le client \(par exemple pour des promotions **limitées dans le temps**, des promotions **pour les grossistes** ou simplement pour des ventes dans des **devises différentes**\).

{% embed url="https://www.odoo.com/documentation/user/12.0/sales/products\_prices/prices/pricing.html" %}

## Comment modifier le prix de vente selon le client ?

Tout d'abord il faut activer l'option "_Plusieurs prix de vente par produit_" et "_Prix spécifiques par article_" dans le menu _Ventes &gt; Configuration &gt; Configuration &gt; Tarif_.

![](.gitbook/assets/image%20%2881%29.png)

Cela fait apparaître une **liste de prix** dans l'onglet _Ventes_ des articles \(ceux qui ont l'option "_Peut être vendu_" cochée, bien entendu\).

![](.gitbook/assets/image%20%2882%29.png)

On comprend que chaque ligne de cette liste associe un certain **groupe de clients** à un certain prix, qui peut dépendre de la **devise** de ce groupe de clients, d'une **quantité minimale** ou d'une **période de validité**.

Lorsqu'on ajoutera cet article dans un nouveau devis, le prix suggéré automatiquement correspondra donc au prix associé au groupe du client du devis.

{% hint style="danger" %}
Les objets Odoo qui définissent ces "groupes de clients" sont \(lamentablement!\) appelés "**Listes de Prix**" dans Odoo. Cela peut prêter à confusion, il faut donc faire attention ! 
{% endhint %}

Il est possible de définir le "groupe de client" d'un client en remplissant le champ \(mal-nommé\) "Liste de Prix" de sa société mère dans l'onglet "Ventes & Achats" :

![](.gitbook/assets/image%20%2879%29.png)

Si on crée un nouveau devis pour ce client, le champ "_Liste de Prix_" du devis sera rempli automatiquement, et si les conditions de quantité minimale ou de période correspondent aux conditions du tarif noté dans la fiche article pour un client de ce groupe "Grossistes Europe", le prix sera lui aussi automatiquement pré-rempli :

![](.gitbook/assets/image%20%2880%29.png)

{% hint style="info" %}
Même si ces champs "Liste de prix" et "Prix unitaire" sont pré-remplis automatiquement, **il est toujours possible de les modifier manuellement** par la suite.
{% endhint %}

## Définition des "groupes de clients"

Une fois que la configuration "_Plusieurs prix de vente par produit_" est activée, le menu "Listes de prix" devient accessible dans l'application des Ventes :

\[image menu liste prix\]

En pratique, une "Liste de prix" est seulement un nom pour différencier certains clients \(ou devis\) des autres.

Au cas où l'option "Multi-devises" est sélectionnée dans le menu des Configuration de l'application "Facturation", il sera possible d'associer une devise à chaque "groupe de client". Cela définira la devise spécifique pour le tarif d'un produit associé à ce "groupe de client".

\[image fiche liste prix\]

Enfin, on voit qu'il est possible de définir de manière facultative une sélection de "_Groupes de pays_" pour chaque objet "_Liste de Prix_". Cela permet de remplir automatiquement le champ "_Liste de Prix_" lors de la création d'un nouveau contact si son pays fait partie de ces "_Groupes de pays_".

