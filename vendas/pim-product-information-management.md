---
description: Gestão avançada e centralizada dos Produtos
---

# PIM - Product Information Management

Módulos desenvolvidos principalmente pela [Akretion](http://akretion.com/pt_BR) junto com a [ACSONE](http://acsone.eu/), como parte do projeto de e-commerce open-source [Shopinvader](http://shopinvader.com) : [https://github.com/shopinvader/odoo-pim/](https://github.com/shopinvader/odoo-pim)

## Objetivo

✨ Juntar no mesmo aplicativo a gestão de todas as informações dos produtos.

![](../.gitbook/assets/image%20%2851%29.png)

## Atributos e Conjuntos de Atributos de produtos

🗄️ A funcionalidade principal dos módulos de PIM é de permitir criar e organizar quantos **Atributos de produtos** forem necessários, sem prejudicar a velocidade do acesso às informações.

Ao criar um Atributo de produto, você cria um novo campo disponível em todos os produtos do mesmo **Conjunto de Atributo** e visível na aba "_Atributos_" do formulário do produto :

![Atributos de um produto do Conjunto de Atributo &quot;M&#xF3;vel&quot;](../.gitbook/assets/image%20%2852%29.png)

### Criação de um Atributo

Um _Atributo_ pode ser um campo pre-existante no Odoo \(_Nativo_\) ou um novo campo criado de zero \(_Custom_\), e pode ser de qualquer tipo \(booleano, texto, seleção múltipla...\) :

![](../.gitbook/assets/image%20%2845%29.png)

{% hint style="info" %}
Um Atributo do tipo "Binário" é uma imagem ou um arquivo.
{% endhint %}

🗂️ ****Um Atributo pertence obrigatoriamente a um **Grupo de Atributo** \(quando forem exibidos na ficha do produto, todos os atributos do mesmo Grupo serão apresentados juntos\) e pode presente em vários **Conjuntos de Atributo**s \(por exemplo, o atributo "_Consumo de Energia_" pode ser apresentado ambós no Conjunto de Atributo "_Geladeira_" e "_Computador_"\).

⚡ Selecionar a opção "**Serializado**" vai aumentar a velocidade do acesso ao banco de dados em bancos grandes \(com centenas de atributos\). Todos os atributos "_Serializados_" serão juntados no mesmo objeto JSON em uma coluna só da tabela SQL dos produtos no banco do dados, o que permite engordar desnecessariamente as tabelas com centenas de colunas vazias a maioria do tempo.

### Os Atributos do tipo _Seleção_ e _Seleção múltipla_

📚 As **Opções** possíveis de um Atributo de _Seleção_ ou de _Seleção múltipla_ **podem ser criadas** de zero ou podem apontar para certos **Objetos do mesmo tipo**, existentes no Odoo \(quer dizer, Objetos do mesmo "_Modelo_" Odoo\).

Para que essas Opções sejam objetos existentes no Odoo, basta escolher o **Modelo relacionado** e selecionar alguns objetos desse Modelo, que seja manualmente pelo botão "_Selecionar Opções de Atributo_" ou definindo um "_Domínio_" seguindo a [sintaxe própria a Odoo](http://www.erpish.com/odoo/how-to-use-domains-to-filter-data-records-in-odoo/).

![](../.gitbook/assets/image%20%2850%29.png)

### Completude de um produto

🌡️É possível dizer se as informações de um produto estão **completas ou não**, graça à seleção de Atributos da lista "**Completude**" do _Conjunto de Atributo_ desse produto :

![](../.gitbook/assets/image%20%2844%29.png)

Para cada elemento da lista Completude, é necessário definir qual é a "Taxa de Completude" trazida pelo preenchimento do elemento no registro de um produto.

{% hint style="info" %}
A soma de todas as Taxas de Completude deve obrigatoriamente ser 100.
{% endhint %}

Por exemplo aqui, apenas os campos "_Países de destinação possíveis_" e "_Descrição Técnica_" estão preenchidos, então "_apenas 25% das informações do produto_" estão registradas :

![](../.gitbook/assets/image%20%2848%29.png)

A lista dos Atributos "_a serem preenchidos_" aparecendo no topo da aba dos Atributos.

{% hint style="warning" %}
É possível que as informações calculadas a partir do preenchimento de um atributo ou a partir do Conjunto de Atributo selecionado não apareçam direitamente quando preencher um campo.

🔄 Nesses casos, é bom lembrar de **atualizar o seu navegador** para sincronizar as informações exibidas com as informações registradas de verdade no banco de dados.
{% endhint %}







  




