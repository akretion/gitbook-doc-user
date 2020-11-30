# Configuração do Retorno CNAB

Na implementação que usa a biblioteca BRCobranca é necessário configurar isso em:

Faturamento &gt; Configuração &gt; Diários

![](../.gitbook/assets/image%20%28170%29.png)

![](../.gitbook/assets/image%20%28149%29.png)

Nesse exemplo estamos usando os dados de demo, e será usado o Diário do Unicred:

![](../.gitbook/assets/image%20%28109%29.png)

Clique na Aba Import related infos:

![](../.gitbook/assets/image%20%28156%29.png)

 A importação do arquivo poderá ser feita pela própria tela do Diário no botão "Import batch file":

![](../.gitbook/assets/image%20%28183%29.png)

Porém como visto na parte de separação de acessos por grupo de usuários existe uma separação e o usuário comum do CNAB não possui acesso ao Diário, por isso o caminho ideal para eles é:

Faturamento &gt; Pagamentos &gt; Import batch file

![](../.gitbook/assets/image%20%28185%29.png)

![](../.gitbook/assets/image%20%28124%29.png)

Informe o local do Arquivo CNAB a ser importado e em seguida clique em Import File:

![](../.gitbook/assets/image%20%28195%29.png)

O programa irá buscar a linha a ser reconciliada pelos campos Nosso Número e o  mesmo Diário que está sendo usado na importação, se encontrado será criado a Entrada de Diário e um Log de Retorno CNAB, se não encontrar apenas o Log onde será possível ver as informações referentes aos Eventos CNAB e o arquivo usado.

                           Forma de Lançamento do Retorno

Criação de uma Entrada de Diário com os valores separados de Valor Recebido \( Valor pago - Valor da tarifa \), Valor de Desconto, Valor de Tarifa Bancaria, Valor de Abatimento e Valor de Juros Mora / Multa. Quando marcada a opção de Automatic Reconcile payment returns as linhas de Fatura relecionadas serão reconciliadas e a Entrada de Diário será movida para o status Lançado.

                          Valor Recebido diferente do Valor no Odoo

Para que a Fatura/Nota Fiscal no Odoo seja completamente reconciliada e o seu status seja alterado de "Aberto" para "Pago" é preciso que a soma dos lançamentos  criados sejam iguais ao valor em aberto da respectiva Fatura.

                                               Valor Menor

Os valores de Desconto e Abatimento informados no arquivo CNAB estão sendo lançados e adicionados na reconciliação para que o valor total fique igaul, exemplo:

       Odoo                                    Valores arquivo CNAB

Valor Odoo      \|  Valor Recebido \|  Valor Abatimento   \| Valor Desconto

    100               \|           80              \|               10                \|          10

                                                 Valor Maior

Caso comum onde devido o valor de Juros Mora/Multa faz com que os valores fiquem diferentes, exemplo:

     Odoo                                     Valores arquivo CNAB

Valor Odoo          \|   Valor recebido   \|  Valor Juros Mora/Multa

   100                   \|             110            \|              10

Nesse caso o Valor de Juros Mora/Multa é lançado de formar separada e o valor da conciliação é Valor Recebido - Valor Juros Mora/Multa \( nesse exemplo 110 - 10 = 100 \).

