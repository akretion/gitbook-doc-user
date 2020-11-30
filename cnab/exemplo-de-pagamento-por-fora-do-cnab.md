# Exemplo de Pagamento Por Fora do CNAB

Caso comum onde por alguma razão o cliente pagou por Deposito, Cheque, Dinheiro, etc uma Fatura/Nota que usa CNAB e isso precisa ser registrado e removido da Ordem de Pagamento ainda não Confirmada ou enviar um nova Instrução de Movimento de Baixa ao Banco, para isso acesse o Fatura correspondente a esse pagamento:

Faturamento &gt; Cliente &gt; Fatura

![](../.gitbook/assets/image%20%28127%29.png)

Clique me Registrar Pagamento:

![](../.gitbook/assets/image%20%28168%29.png)

![](../.gitbook/assets/image%20%28107%29.png)

Caso se tente Pagar com um Diario usado por qualquer Modo de Pagamento que seja CNAB não será possível e uma mensagem de erro será mostrada: 

![](../.gitbook/assets/image%20%28194%29.png)

Por isso selecione um Diario não relacionado ao CNAB:

![](../.gitbook/assets/image%20%28158%29.png)

Ao clicar "Validar" o programa irá verificar se a Ordem de Pagamento ainda estiver no status "Provisório" a linha será apagada:

![](../.gitbook/assets/image%20%28203%29.png)

![](../.gitbook/assets/image%20%28164%29.png)

Caso a Linha esteja nos status "Confirmado" ou "Arquivo Gerado" não será possível realizar o Pagamento e uma mesnagem de erro será mostrada:

![](../.gitbook/assets/image%20%28148%29.png)

E caso a Ordem de Pagamento esteja no status "Arquivo enviado com sucesso" será criada uma nova Ordem de Pagamento ou adicionada em uma já existente porém com código de Baixa:

![](../.gitbook/assets/image%20%28140%29.png)

![](../.gitbook/assets/image%20%28112%29.png)



