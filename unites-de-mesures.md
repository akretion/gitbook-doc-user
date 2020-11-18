# Unités de Mesures

Pour acheter et vendre un article dans des unités de mesure différentes il faut cocher l'option "_Unités de Mesure_" dans les configurations de l'application Inventaire :

\[image config uom\]

Cela permet de faire apparaître ces deux champs d'Unités de Mesure, une pour la vente et l'autre pour l'achat :

\[image article uom\]

Seulement Odoo ne permet nativement que de choisir des unités de mesure de la même "_Catégorie_" \(les centimètres et les mètres par exemple\). Une catégorie aura donc une unité de mesure de référence et les autres unités de mesure seront des multiples de cette unité de référence :

\[image 3\]

Pour acheter ou vendre dans des unités de catégories différentes ou bien enregistrer d'autres relations entre différentes unités de mesure pour chaque article, il faut utiliser les modules de l'OCA qui traitent des unités de mesure secondaires  :

{% embed url="https://github.com/OCA/sale-workflow/tree/13.0/sale\_order\_secondary\_unit" %}



