# Modo de Pagamento

O Modo de Pagamento é o cadastro onde é possível informar como uma Fatura será paga ex.: Cheque, Dinheiro, etc ou no caso de um CNAB  Boleto Banco X, por isso é onde estão os dados especificos de cada Banco e CNAB usados pela empresa para cadastrar acesse :

Faturamento &gt; Configuração  &gt; Modo de Pagamento

![](../.gitbook/assets/image%20%28128%29.png)

Clique em Criar para um novo cadastro, veja um exemplo:

![](../.gitbook/assets/image%20%28151%29.png)

O campo Nome é o que irá aparecer para os usuários selecionarem nos Pedidos de Venda, Compra e na Fatura por isso é importante identifica-lo de formar clara até mesmo informando de qual banco se trata para evitar problemas caso a empresa use ou mesmo pretenda usar outros bancos.

A definição sobre o tipo CNAB, 240 ou 400, e se é um Pagamento ou um Recebimento é feita pelo campo Método de Pagamento que é um cadastro, como são valores padrões isso já é carregado com a instalação do modulo, pode ser acessado em:

Faturamento &gt; Configurações &gt; Metodos de Pagamento

![](../.gitbook/assets/image%20%28134%29.png)

![](../.gitbook/assets/image%20%28118%29.png)

![](../.gitbook/assets/image%20%28161%29.png)

Continuando no cadastro do Modo de Pagamento, no caso CNAB é preciso usar a opção de Diário do Banco Fixo e único.

Logo em seguida você pode informar uma Taxa que será adicionada como uma nova linha nos Pedidos de Venda, Compras e Faturas, caso isso seja necessário.

![](../.gitbook/assets/image%20%28146%29.png)

Veja que existem outras opções, porém algumas não podem ser usadas e irão gerar uma mensagem de erro caso marcadas, Transações em grupo em ordens de pagamento\( pois no caso CNAB cada linha deve ser única \), campos abaixo Gerar entradas contábeis no envio do arquivo e Movimento de Publicação

![](../.gitbook/assets/image%20%28132%29.png)

Logo em seguida, caso o Metodo de Pagamento for referente ao CNAB, serão mostrados os campos referentes:

![](../.gitbook/assets/image%20%28127%29.png)

![](../.gitbook/assets/image%20%28107%29.png)

![](../.gitbook/assets/image%20%28113%29.png)

No Retorno do CNAB o programa precisa saber as Contas Contabeis que serão usadas para cada valor informado:

![](../.gitbook/assets/image%20%28131%29.png)

E como cada Banco CNAB pode usar Códigos distintos tanto para o Retorno quanto para Instrução do Movimento deverá ser informado os códigos de Retorno que irão gerar a Reconcilição \( liquidação \) e o Códigos de Instrução do Movimento para a Remessa \( envio do título \) e de Pedido de Baixa \( quando o valor é pago por fora do CNAB e a empresa precisa informar o Banco \)

OBS.: Faltando os campos de Alteração do Vencimento, Abatimento, Cancelar Abatimento e os outros campos existententes que poderão ser usados dentro do programa.

![](../.gitbook/assets/image%20%28150%29.png)

IMPORTANTE: Devido aos diversos campos que são necessários para o uso do CNAB, e como isso envolve a comunicação entre o programa e o Banco e consequentemente o próprio dinheiro e caixa da empresa, além das permissões de acesso estão sendo monitorados os principais campos do CNAB, por tanto qualquer alteração será registrada como abaixo:

 

![](../.gitbook/assets/image%20%28104%29.png)

![](../.gitbook/assets/image%20%28139%29.png)

OBS.: Campos do tipo "Many2many" não estão registrando alterações, o "track\_visibility" não funciona, comentários no código sobre isso e possível solução seria um modulo da OCA porém hoje só existe um PR de migração para a versão 11, importante resolver pois aqui se trata do campo referente aos Codigos de Retorno que devem gerar a reconciliação da Fatura.





