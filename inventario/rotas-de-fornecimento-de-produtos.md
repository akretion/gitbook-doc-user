---
description: >-
  Opções principais e básicas para aumentar a quantidade de um produto estocável
  no seu estoque.
---

# Rotas de fornecimento de produtos

Com os módulos principais de Odoo \(_Venda_, _Compra_, _Inventário_ e _Manufatura_\) aparece 3 opções de "Rotas" na ficha de cada produto. Uma rota é uma maneiras de aumentar o estoque do produto até uma certa quantidade :

![](../.gitbook/assets/image%20%28219%29.png)

É muito importante entender a diferença entre as rotas que determinam **COMO** será realizado o ajuste de estoque e as rotas que determinam **QUANDO** será realizado esse ajuste.

As opções "_Comprar_" e "_Fabrico_" determinam **COMO será aumentado** a quantidade do produto :

* A opção "_Comprar_" indica que o produto vai ter que ser **comprado** \(pela criação automática de uma _Solicitação de Cotação_ no menu de _Compra_\)
*  A opção "_Fabrico_" indica que o produto vai ter que ser **fabricado** \(pela criação automática de um _Ordem de Produção_ no menu de _Manufatura_\)

A opção "_Obter para Encomenda_" \(tradução de _Make to Order - MTO_ em inglês\) determina **QUANDO será aumentado** a quantidade do produto :

* Se for selecionada, o aumento da quantidade do produto \(que seja por _Solicitação de Cotação_, _Ordem de Produção_ ou qualquer outra maneira\) será acionado **quando uma venda desse produto for confirmada**.
* Se não for selecionada quer dizer que a opção padrão "_Obter para Estoque_" \(tradução de _Make to Stock - MTS_\) está ativa. Nesse caso o aumento da quantidade do produto será acionado **quando o estoque do produto passar embaixo de uma certa quantidade** mínima, definida no objeto _Regra de Recompra_ ligado ao produto :

![](../.gitbook/assets/image%20%28218%29.png)

![](../.gitbook/assets/image%20%28217%29.png)

{% hint style="warning" %}
Apesar do que o nome pode sugerir uma _Regra de Recompra_ não ativa necessariamente uma "**compra**" do produto para chegar na quantidade desejada.

Pode ativar uma "**fabricação**" do produto ou qualquer outra maneira de fornecimento definida pela Rota que indica "COMO" será aumentada essa quantidade de produto.
{% endhint %}

## "Compra" vs "Fabrico"

Para que a rota "_Compra_" seja operacional, necessita pelo menos informar um fornecedor na aba "Compra" do produto :

![](../.gitbook/assets/image%20%28213%29.png)

Do outro lado, para que a rota "Fabrico" seja operacional é necessário definir uma "Lista de Material" associada ao produto :

![](../.gitbook/assets/image%20%28215%29.png)

