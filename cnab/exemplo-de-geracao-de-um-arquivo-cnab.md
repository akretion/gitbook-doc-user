# Exemplo de Geração de um Arquivo CNAB

O exemplo abaixo está usando os dados de demo, assim você pode fazer o mesmo processo para testes e validar se tudo está de acordo como esperado, acesse a tela de Faturas de Clientes:

Faturamento &gt; Clientes &gt; Faturas

![](../.gitbook/assets/image%20%28121%29.png)

OBS.: Veja que o usuário de Demo que está configurado com o Grupo de Acesso Usuário CNAB não possui acesso e permissões para fazer alterações nas parametrizações referentes ao CNAB. No teste vou usar o caso do Unicred 400:

![](../.gitbook/assets/image%20%28184%29.png)

Ao Clicar no botão Validar como o Modo de Pagamento é uma CNAB será criada nova Ordem de Pagamento ou adicionada em uma existente que não esteja com o status Confirmado.

![](../.gitbook/assets/image%20%28132%29.png)

O status será alterado para Aberto e na Aba Vencimentos irá ser criadas as linhas referentes as Parcelas, nesse caso em duas vezes:

![](../.gitbook/assets/image%20%28113%29.png)

Para a geração do Boleto clique no botão Imprimir Boleto: 

![](../.gitbook/assets/image%20%28201%29.png)

Será adcionado um anexo logo abaixo da Fatura:

![](../.gitbook/assets/image%20%28136%29.png)

Ao clicar será mostrado o arquivo clique nele para visualizar ou para baixar o arquivo:

![](../.gitbook/assets/image%20%28152%29.png)



![](../.gitbook/assets/image%20%28133%29.png)

![](../.gitbook/assets/image%20%28202%29.png)

OBS.: Veja que o Digito do Nosso Número é criado automaticamente por ser algo calculado, não é informado dentro do Odoo. 

Ao clicar na linha de Vencimento você poderá ver as informações referentes ao CNAB:

![](../.gitbook/assets/image%20%28141%29.png)

![](../.gitbook/assets/image%20%28210%29.png)

Logo abaixo na tela da Fatura é possível observar que foram adicionadas mensagens referentes:

![](../.gitbook/assets/image%20%28145%29.png)

Para ver a Ordem de Pagamento acesse:

Faturamento &gt; Pagamentos &gt; Ordens de Débito

![](../.gitbook/assets/image%20%28163%29.png)

![](../.gitbook/assets/image%20%28130%29.png)

![](../.gitbook/assets/image%20%28147%29.png)

Ao clicar em uma linha veja que existem informações referentes ao CNAB que serão usadas para gerar a Linha de Pagamento Bancario

![](../.gitbook/assets/image%20%28188%29.png)

A Confirmação da Ordem de Pagamento deve variar de acordo com o fluxo de envio do arquivo CNAB para o Banco portanto isso depende de cada empresa, enquanto estiver em Rascunho todas as novas Faturas Validadas que possuem o mesmo Modo de Pagamento serão adicionadas na mesma Ordem de Pagamento, quando se desejar gerar o arquivo clique em Confirmar pagamentos:

![](../.gitbook/assets/image%20%28123%29.png)

Veja que serão criadas as Linhas de pagamento Bancario na Aba de mesmo nome:

![](../.gitbook/assets/image%20%28178%29.png)

![](../.gitbook/assets/image%20%28157%29.png)

E para gerar o arquivo clique em Gerar Arquivo

![](../.gitbook/assets/image%20%28206%29.png)

IMPORTANTE: A implementação foi feita para permitir que seja possível usar mais de uma biblioteca para o CNAB assim é necessário instalar o modulo que a implementa, caso não esteja instalado irá aparecer uma mensagem de erro nesse momento, nesse caso estamos usando a biblioteca BRCobranca.

![](../.gitbook/assets/image%20%28122%29.png)

Clique em cima do arquivo para Baixa-lo, após enviar o arquivo ao Banco é importante que o status da Ordem de Pagamento seja alterado de "Arquivo Gerado" para "Arquivo Enviado com sucesso", essa informação é fundamental para o caso de um Pagamento por Fora do CNAB\( quando o cliente por algum motivo paga o valor da parcela por outra via e se torna necessário informar o Banco para solicitar a Baixa do Título \), por isso clique em cima do nome da ordem para voltar a ela e fazer essa atualização:

 

![](../.gitbook/assets/image%20%28125%29.png)

![](../.gitbook/assets/image%20%28167%29.png)

![](../.gitbook/assets/image%20%28146%29.png)





