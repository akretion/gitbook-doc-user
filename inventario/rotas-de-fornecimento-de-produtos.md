---
description: >-
  Opções principais e básicas para aumentar a quantidade de um produto estocável
  no seu estoque.
---

# Rotas de fornecimento de produtos

Com os módulos principais de Odoo \(_Venda_, _Compra_, _Inventário_ e _Manufatura_\) aparece 3 opções de "Rotas" na ficha de cada produto. Uma rota é uma maneiras de aumentar o estoque do produto até uma certa quantidade :

![](../.gitbook/assets/image%20%28220%29.png)

{% hint style="info" %}
Obviamente, para se tratar de "quantidade de produto", o produto deve ser de **tipo "Produto"** \(e não "Consumível" nem "Serviço"\) para poder seguir o seu estoque.
{% endhint %}

Antes de tudo é muito importante entender que existe uma diferença entre as rotas que determinam **COMO** será realizado o ajuste de estoque e as rotas que determinam **QUANDO** será realizado esse ajuste.

As opções "_Comprar_" e "_Fabrico_" determinam **COMO será aumentado** a quantidade do produto :

* A opção "_Comprar_" indica que o produto vai ter que ser **comprado** \(pela criação automática de uma _Solicitação de Cotação_ no menu de _Compra_\)
*  A opção "_Fabrico_" indica que o produto vai ter que ser **fabricado** \(pela criação automática de um _Ordem de Produção_ no menu de _Manufatura_\)

A opção "_Obter para Encomenda_" \(tradução de _Make to Order - MTO_ em inglês\) determina **QUANDO será aumentado** a quantidade do produto :

* Se for selecionada, o aumento da quantidade do produto \(que seja por _Solicitação de Cotação_, _Ordem de Produção_ ou qualquer outra maneira\) será acionado **quando uma venda desse produto for confirmada**.
* Se não for selecionada quer dizer que a opção padrão "_Obter para Estoque_" \(tradução de _Make to Stock - MTS_\) está ativa. Nesse caso o aumento da quantidade do produto será acionado **quando o estoque do produto passar embaixo de uma certa quantidade** mínima, definida no objeto _Regra de Recompra_ ligado ao produto :

![](../.gitbook/assets/image%20%28219%29.png)

![](../.gitbook/assets/image%20%28218%29.png)

{% hint style="warning" %}
Apesar do que o nome pode sugerir uma _Regra de Recompra_ não ativa necessariamente uma "**compra**" do produto para chegar na quantidade desejada.

Pode ativar também uma "**fabricação**" do produto ou qualquer outra maneira de fornecimento definida pela Rota que indica "COMO" será aumentada essa quantidade de produto.
{% endhint %}

## "Comprar" vs "Fabrico"

Para que a rota "_Compra_" seja operacional, necessita pelo menos **informar um fornecedor** na aba "Compra" do produto :

![](../.gitbook/assets/image%20%28214%29.png)

Do outro lado, para que a rota "_Fabrico_" seja operacional é necessário definir pelo menos uma "_**Lista de Material**_" associada ao produto :

![](../.gitbook/assets/image%20%28213%29.png)

E essa _Lista de Material_ deve ser do tipo "_**Fabricar este produto**_" para realmente criar um objeto _Ordem de Produção_ quando o aumento de estoque for ativado :

![](../.gitbook/assets/image%20%28221%29.png)

Se a _Lista de Material_ for do tipo "_Kit_", o sinal de aumento de quantidade do meu produto final vai apenas acionar outros sinais para aumentar as quantidades relacionadas de cada componente do _Kit_.

## "Obter para Encomenda" \(MTO\) vs "Obter para Estoque" \(MTS\)

Com os módulos básicos de Odoo você tem que escolher se o aumento de quantidade de produto será acionado por uma venda \(MTO\) desse produto **ou** pela _Regra de Recompra_ do produto indicando uma quantidade mínima para segurar \(MTS\).

Se por engano você tiver ambos a rota "Obter para Encomenda" selecionada é uma Regra de Recompra definida para o seu produto, Odoo vai até seguir as duas rotas **sem nenhuma otimização** : um aumento de quantidade será acionado depois de uma venda do produto \(independentemente da quantidade no estoque\) e um outro aumento de quantidade será acionado quando o estoque do produto passar embaixo da quantidade mínima definida na _Regra de Recompra_ \(independentemente da quantidade que for vendida\).

Para uma gestão otimizada desses ajustes de estoque, a Akretion desenvolveu [o módulo **"stock\_mts\_mto\_rule"**](https://github.com/OCA/stock-logistics-warehouse/tree/12.0/stock_mts_mto_rule) que permite acionar um aumento de quantidade de produto quando uma venda for confirmada **apenas se a quantidade desse produto não estiver presente no estoque :**

{% embed url="https://github.com/OCA/stock-logistics-warehouse/tree/12.0/stock\_mts\_mto\_rule" %}

\*\*\*\*



