# Routes d'approvisionnement

Les _Routes_ sont des objets Odoo qui regroupent un ensemble de _Règles_. Ces _Règles_ permettent de créer des _Opérations_ sur les stocks automatiquement, suivant certaines conditions.

Par exemple, pour créer une Livraison automatiquement lors de la confirmation d'une Commande de Vente, Odoo va regarder la Route associée à l'entrepôt sélectionné dans la Commande de Vente.

Au moment de la confirmation de la Vente, Odoo regarde si il y a une Route qui indique _"comment envoyer les produits à un client depuis cet entrepôt"_. Il y en a justement une par défaut pour chaque entrepôt :&#x20;

![Entrepôt](<.gitbook/assets/image (241).png>)

![Route de livraison de l'entrepôt](<.gitbook/assets/image (245).png>)

La _Règle_ associée à cette _Route_ dit simplement de créer des mouvements de stock depuis l'emplacement principal de l'entrepôt en question vers "l'emplacement virtuel des Clients". Exactement ce que l'on souhaite quand on livre un produit à un client.

{% hint style="info" %}
**Différence entre les Ventes et les Achats**

Quand on crée une Commande d'Achat (BC) manuellement, Odoo **ne regarde pas la route** qui dirait "comment recevoir le produit acheté dans un certain entrepôt". Il regarde simplement le "**type d'Opération**" associé à l'achat et crée une Réception ayant les caractéristiques du "type" sélectionné, par exemple :&#x20;


{% endhint %}

![Type d'Opération "Réception dans l'entrepôt"](<.gitbook/assets/image (251).png>)

{% hint style="info" %}
**Les Types d'Opérations**

Un Type d'Opération donne les **caractéristiques générales** d'une Opération : son emplacement d'origine, son emplacement de destination, le code à utiliser pour nommer l'Opération et d'autres infos d'affichage des champs de l'Opération.

Une Règle d'une Route va notamment être associée à un "Type d'Opération" pour indiquer quelles vont être les caractéristiques de l'opération créée automatiquement depuis le déclenchement de la règle :


{% endhint %}

![La Règle associée à la Route de Livaison de notre entrepôt](<.gitbook/assets/image (248).png>)

## Routes associées aux produits

En dehors des Routes associées aux Entrepôts, il existe aussi des Routes "associées à certains produits" comme la Route _"Réapprovisionner le sous-traitant sur demande" :_&#x20;

![](<.gitbook/assets/image (244).png>)

Ces Routes associées à des produits ne sont pas prises en compte lors de la confirmation d'une Vente, mais seulement **lorsqu'un certain mouvement de stock de ce produit est réalisé.**

Par exemple, on peut lire que les Règles associées à cette Route indiquent (pour chaque entrepôt) qu'il faut "déclencher une autre règle" quand un composant est demandé dans un Ordre de Fabrication d'un Sous-traitant :&#x20;

![](<.gitbook/assets/image (250).png>)

Pour trouver cette règle à déclencher, Odoo regarde si il existe une Route qui décrit comment acheminer les produits de notre entrepôt vers les sous-traitants. Il y en a justement une :

![](<.gitbook/assets/image (243).png>)

La Règle associée à cette Route indique qu'il faut simplement "Prendre le stock" de notre entrepôt et le livrer au sous-traitant directement :&#x20;

![](<.gitbook/assets/image (247).png>)

## Déclencher un Achat ou une Production depuis une Vente

Routes "Make To Order" associée au produit :&#x20;

![](<.gitbook/assets/image (246).png>)

Règle = Prendre dans le stock, si pas disponible déclencher une autre Règle :&#x20;

![](<.gitbook/assets/image (242).png>)

Si pas de stock pour ce produit, Odoo regarde les Routes possibles pour acheminer ce produit dans l'emplacement souhaité. Il faut donc que notre article soit assoié à au moins 2 Routes, par exemple :&#x20;

&#x20;

![](<.gitbook/assets/image (249).png>)

La Règle associée à la Route "Acheter" déclenchera la création d'une Commande d'Achat la quantité souhaitée... à réceptionner dans l'entrepôt souhaité :&#x20;

![](<.gitbook/assets/image (252).png>)



## Des Routes plus complexes

Doc officielle d'Odoo :&#x20;

[https://www.odoo.com/documentation/14.0/applications/inventory\_and\_mrp/inventory/routes/concepts/use-routes.html](https://www.odoo.com/documentation/14.0/applications/inventory\_and\_mrp/inventory/routes/concepts/use-routes.html)
