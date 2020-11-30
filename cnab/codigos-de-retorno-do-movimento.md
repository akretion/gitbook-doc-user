# Configuração dos Códigos de Retorno do Movimento

São os códigos usados pelo Banco para informar do que se trata a linha de retorno do CNAB ex.: Entrada Confirmada, Entrada Rejeitada, Liquidação, Protesto em Cartório, etc cada banco e CNAB podem usar um específico não existe um padrão nem no 240, por isso verifique se os Códigos de Retorno do Movimento do seu Banco e respectivo CNAB estão cadastrados no programa e se necessário crie :

Faturramento &gt; Configurações &gt; CNAB Return Move Code

![](../.gitbook/assets/image%20%28161%29.png)

![](../.gitbook/assets/image%20%28138%29.png)

Veja que apesar dos códigos 02 - Entrada Confirmada e 03 - Entrada Rejeitada serem até agora padrões nos Bancos e CNAB o código 01 - Pago \( Título protestado pago em cartório \) só é usado no banco Unicred o que mostra a falta de padrão.

Veja que tanto a criação quanto alterações nos campos estão sendo registradas, para se necessário ser feita auditoria, também é feita validação para não permitir cadastro de Códigos já existentes para o mesmo Banco e CNAB.

OBS.: Campos do tipo "Many2many" não estão registrando alterações, o "track\_visibility" não funciona, comentários no código sobre isso e possível solução seria um modulo da OCA porém hoje só existe um PR de migração para a versão 11.

Se seu caso não existir considere fazer um PR no projeto da Localização para adicionar isso nos arquivos data do modulo, assim o próximo que for usar esse Banco CNAB não irá precisar cadastra-lo.

