# Unités de Mesures

Pour acheter et vendre un article dans des unités de mesure différentes il faut cocher l'option "_Unités de Mesure_" dans les configurations de l'application Inventaire :

![](.gitbook/assets/image%20%2887%29.png)

Cela permet de faire apparaître ces **deux champs d'Unités de Mesure**, une pour la vente \(et l'inventaire, et les ordres de production\) et l'autre pour l'achat :

![](.gitbook/assets/image%20%2881%29.png)

Seulement Odoo ne permet nativement que de choisir des unités de mesure de la **même "**_**Catégorie**_**"** \(les centimètres et les mètres par exemple\). Une catégorie aura donc une unité de mesure de référence et les autres unités de mesure seront des multiples de cette unité de référence :

![](.gitbook/assets/image%20%2890%29.png)

Pour acheter ou vendre dans des unités de **catégories différentes** ou bien enregistrer d'autres relations entre différentes unités de mesure pour chaque article, il faut utiliser les modules de l'OCA qui traitent des unités de mesure secondaires  :

[https://github.com/OCA/sale-workflow/tree/13.0/sale\_order\_secondary\_unit](https://github.com/OCA/sale-workflow/tree/13.0/sale_order_secondary_unit)

[https://github.com/OCA/purchase-workflow/tree/12.0/purchase\_order\_secondary\_unit](https://github.com/OCA/purchase-workflow/tree/12.0/purchase_order_secondary_unit)



