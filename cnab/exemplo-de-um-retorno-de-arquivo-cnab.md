# Exemplo de um Retorno de Arquivo CNAB

O exemplo abaixo está usando os dados de demo, assim você pode fazer o mesmo processo para testes e validar se tudo está de acordo como esperado, acesse a tela:

Faturamento &gt; Pagamentos &gt; Import batch file

![](../.gitbook/assets/image%20%28126%29.png)

Infome o Diario usado e carregue o arquivo CNAB \( arquivo usado está na pasta de tests do modulo \) em seguida clique em Import file:

![](../.gitbook/assets/image%20%28193%29.png)

![](../.gitbook/assets/image%20%28189%29.png)

Caso o programa encontre uma linha dentro do Odoo que possua om mesmo campo Nosso Número e o mesmo Diário que está sendo usado na importação o programa irá abrir a tela de Entreda de Diários:

![](../.gitbook/assets/image%20%28175%29.png)

Veja que como o nome do arquivo diz esse caso é de um Valor Menor do que o que existe dentro do Odoo por motivo de Desconto e Abatimento:

![](../.gitbook/assets/image%20%28137%29.png)

Clicando no botão "Lançamentos reconciliados" é possível ver as conciliações:

![](../.gitbook/assets/image%20%28131%29.png)

![](../.gitbook/assets/image%20%28186%29.png)

Porém nesse exemplo como a opção de Automatic Recociliation payments returns no Diário não está marcada é preciso Lançar a Entrada:

![](../.gitbook/assets/image%20%28117%29.png)

![](../.gitbook/assets/image%20%28190%29.png)

E nesse caso também será necessário informar na respectiva Fatura/Nota esses lançamentos:

![](../.gitbook/assets/image%20%28139%29.png)

![](../.gitbook/assets/image%20%28197%29.png)

Se todas parcelar que estavam pendentes forem associadas o status dessa Fatura também será alterado para "Pago":

![](../.gitbook/assets/image%20%28143%29.png)

Veja que agora os Lançamentos Reconciliados irão aparecer com Número de Correspondencia:

![](../.gitbook/assets/image%20%28196%29.png)

![](../.gitbook/assets/image%20%28191%29.png)

Veja que na Entrada de Diário existe uma Aba que informa o Log do Retorno CNAB que criou essa entrada:

![](../.gitbook/assets/image%20%28179%29.png)

![](../.gitbook/assets/image%20%28114%29.png)

![](../.gitbook/assets/image%20%28177%29.png)

![](../.gitbook/assets/image%20%28108%29.png)

![](../.gitbook/assets/image%20%28172%29.png)

O Log de Retorno do CNAB também pode ser acessado via tela em:

Faturamento &gt; Pagamentos &gt; CNAB Return Log

![](../.gitbook/assets/image%20%28119%29.png)

Caso  a opção de Automatic Recociliation payments returns no Diário esteja marcada a Entrada de Diário já será Lançada e não será necessário associar os Pagamentos na Fatura, veja o exemplo agora com um caso de Valor Recebido Maior:

![](../.gitbook/assets/image%20%28118%29.png)

![](../.gitbook/assets/image%20%28110%29.png)

![](../.gitbook/assets/image%20%28180%29.png)

![](../.gitbook/assets/image%20%28181%29.png)

![](../.gitbook/assets/image%20%28169%29.png)

![](../.gitbook/assets/image%20%28176%29.png)

![](../.gitbook/assets/image%20%28111%29.png)

