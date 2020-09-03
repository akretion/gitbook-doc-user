---
description: Situação em setembro de 2020
---

# Desenvolvimento da localização

Desde 2009, a [Akretion](https://github.com/akretion) está liderando a [comunidade dos desenvolvedores brasileiros](https://github.com/OCA/l10n-brazil/graphs/contributors) que adaptam o software Odoo de maneira livre e colaborativa à complexidade da realidade brasileira.

Tentamos resumir aqui o andamento atual desse imenso trabalho listando :

* 🟢 as funcionalidades **totalmente operacionais**, porém que necessitam uma certa parametrização para ser adaptadas com cada usuário\)
* 🟡 as funcionalidades que **necessitam ainda um pouco de desenvolvimento**, porém já sabemos "como desenvolver", a arquitetura do código atual já está pronta para receber essa funcionalidade.
* 🔴 as funcionalidades que **necessitam ainda muito desenvolvimento**. Mesmo se um trabalho já foi realizado para definir "como teria que ser desenvolvido essa funcionalidade", ainda falta escrever todo o código do módulo.

Todos os módulos citados aqui podem ser baixados e usados livremente a partir do [repositório da localização brasileira](https://github.com/OCA/l10n-brazil) no perfil github da [Odoo Community Association \(OCA\)](https://odoo-community.org/) :

{% embed url="https://github.com/OCA/l10n-brazil" %}

## 🏛️ Fiscalidade

**Módulo :** [l10n\_br\_fiscal](https://github.com/OCA/l10n-brazil/tree/12.0/l10n_br_fiscal) \| **Liderado por :** [Akretion](https://github.com/akretion)

### Cálculo dos Impostos

* 🟢 Para todos os tipos de empresas ! Simples Nacional e Normais.
* 🟢 Registro de substituições tributárias

O coração da complexidade fiscal brasileira necessário para toda a gestão dos documentos fiscais e da contabilidade ! CNAE, Perfil Fiscal, NCM, CEST, Desoneração do ICMS, Crédito do PIS/COFINS... Não falta nenhuma opção para o cálculo exato dos impostos brasileiros.

### Conciliação Bancária

* 🟢 Importação automática dos extratos bancários no Odoo clicando num botão 2 vezes por semana.
* 🟢 Conciliação automática entre os extratos e os lançamentos contábeis no Odoo. Essa funcionalidade da conciliação automática é operacional, porém necessita sempre muito trabalho de parametrização para ser adaptada com cada usuário.
* 🔴 Sincronização em tempo real dos extratos bancários com Odoo. Essa funcionalidade envolve questões de segurança extremas que demandaria um investimento muito alto.

### Documentos fiscais

* 🟢 Arquitetura pensada para receber teoricamente qualquer tipo de campo fiscal para a construção de qualquer documento fiscal
* 🟢 Emissão e Importação no Odoo das NF-e de produtos
* 🟢 Emissão e Importação no Odoo das NF-e de remessa
* 🟡 Emissão das NFS-e \(nota fiscal de serviço eletrônica\) compatível com a metade dos padrões NFS-e \(os mais famosos\).
* 🔴 Importação das NFS-e no Odoo não suportada por enquanto, sendo uma demanda muito rara dos usuários.
* 🟡 Existem protótipos para 80% dos outros documentos fiscais \(MDFE, CTE...\) porém eles necessitariam ainda um pouco de desenvolvimentos.

### Integração dos campos fiscais brasileiros com os outros módulos Odoo

* 🟢 Integração com os módulos de venda, compra, estoque e manufatura.
* 🟡 A integração com os outros módulos ainda não está realizada, porém a arquitetura do módulo [l10n\_br\_fiscal](https://github.com/OCA/l10n-brazil/tree/12.0/l10n_br_fiscal) permite a realização dessas futuras integrações muito facilmente.

### SPED : declarações tributárias e fiscais

**Módulo :** [sped-extractor](https://github.com/akretion/sped-extractor) \| **Liderado por :** [Akretion](https://github.com/akretion)

* 🟡 A Akretion desenvolveu o programa [sped-extractor](https://github.com/akretion/sped-extractor) que recupere automaticamente os milhões de campos \(dados pelos manuais em pdf da SPED\) que têm que ser preenchidos para as suas declarações tributárias e fiscais. Porém esse módulo ainda não foi usado em produção.
* 🔴 Uma vez esse programa completado precisará ainda de desenvolvimentos para gerar e mandar as declarações da SPED direitamente a partir de Odoo.

## 💳 Pagamentos

### Boleto e arquivos CNAB de recebimento e pagamento

* 🟡 Geração de Boleto de Pagamento registrado
* 🟡 Emissão dos arquivos CNAB \(240 ou 400\) de recebimento 
* 🟡 Emissão dos arquivos CNAB \(240 ou 400\) de pagamento
* 🟡 Gestão dos arquivos de retorno do Banco
* 🟡 Reconciliação dos recebimentos e dos pagamentos dados pelos arquivos de retorno com os lançamentos contábeis no Odoo

Como cada banco tem um jeito de comunicar diferente, ainda não é possível cobrar todas essas funcionalidades para todos os bancos brasileiros. Porém, o quanto mais comum o banco, o quanto mais essas funcionalidades já estão operacionais.

💬 Você pode [entrar em contato com a Akretion](https://akretion.com/pt-BR/contato) para entender melhor qual seria o custo do desenvolvimento dessas funcionalidades para o seu banco.

### Gateway de pagamento

**Módulo :** [payment\_cielo](https://github.com/OCA/l10n-brazil/pull/943) \| **Liderado por :** [KMEE](https://github.com/kmee)

* 🟡 Comunicação com os gateway de pagamento. Existe protótipos de módulos para comunicar com os gateway de pagamento mais comum como [Cielo](https://github.com/OCA/l10n-brazil/pull/943) ou Pagseguro.
* 🔴 Conciliação dos pagamentos via um gateway \(brasileiro\) com os lançamentos contábeis no Odoo.  

A Akretion desenvolveu \(principalmente com o seu time na França\) ferramentas maduras de comunicação **e conciliação** com gateways de pagamento, porém gringos como [Stripe](https://github.com/akretion/payment-gateway/tree/12/payment_gateway_stripe), [Adyen](https://github.com/akretion/payment-gateway/tree/12/payment_gateway_adyen) e [Paypal](https://github.com/akretion/payment-gateway/tree/12/payment_gateway_paypal),  e eles têm limitações de ação no Brasil.

## 📑 Relatórios contábeis

* 🟢 BP - Balanço Patrimonial.
* 🟢 DRE - Demonstrativo de Resultado do Exercício.
* 🔴 Guia de Impostos. Um protótipo está sendo desenvolvido e deve estar testável a partir de dezembro de 2020.

O BP e o DRE estão gerados no Odoo graça ao módulo [MIS-builder](https://github.com/OCA/mis-builder) da OCA desenvolvido pela empresa [ACSONE](https://github.com/acsone). É um módulo muito poderoso que permite ao próprio usuário criar os seus **relatórios contábeis personalizados**. Uma agilidade que não seria possível com o módulo nativo de relatórios do Odoo.

{% hint style="warning" %}
Quando dizer que os relatórios contábeis são disponíveis no Odoo, é importante notar que seria para uma contabilidade de **gestão** **interna**.

Seria teoricamente possível usar esses relatórios contábeis para **declarações oficiais** porém apenas depois de muitas avaliações específicas a cada empresa.
{% endhint %}

## 💰 Folha de Pagamento

**Módulos :** [l10n\_br\_hr](https://github.com/OCA/l10n-brazil/tree/12.0/l10n_br_hr), [l10n\_br\_hr\_contract](https://github.com/OCA/l10n-brazil/tree/12.0/l10n_br_hr_contract) \| **Liderados por :** [KMEE](https://github.com/kmee)

* 🟢 Campos específicos para o cadastro de empregados brasileiros
* 🟢 Campos específicos para os contratos de empregados brasileiros
* 🟢 Gestão das feiras e das folhas de tempo
* 🟢 Exportações das informações necessárias para a geração das folhas de pagamento
* 🔴 Geração das folhas de pagamento do Odoo mesmo
* 🔴 Geração do eSocial inteiro do Odoo

Como o formato das folhas de pagamento varia em cada estado, precisaria de muitos desenvolvimentos para gerá-las a partir do Odoo, enquanto a exportação das informações já permite criar as folhas por um software externo facilmente \(porém manualmente\).

Na mesma ideia, não é possível gerar o eSocial inteiro a partir do Odoo, porém é possível exportar as informações necessárias à geração do eSocial por um software externo.

## Campos específicos brasileiros

**Módulo :** [l10n\_br\_base](https://github.com/OCA/l10n-brazil/tree/12.0/l10n_br_base) \| **Liderado por :** [Akretion](https://github.com/akretion)

* 🟢 CPF, Inscrição Estadual, NCM... A integralidade dos campos específicos ao Brasil estão presente e totalmente integrados em todos os módulos do Odoo.
* 🟢 Busca do endereço automaticamente pelo CEP.

## Cálculo dos custos de entrega

**Módulo :** [delivery\_correio](https://github.com/Code-137/odoo-apps/blob/13.0/delivery_correios/) **\| Liderado por :** [Code-137](https://github.com/Code-137/)

* 🟡 Calcular o custo de entrega de um produto no Brasil inteiro.

