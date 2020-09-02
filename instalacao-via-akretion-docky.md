---
description: Instalando o Odoo usando docker-compose via Akretion Docky
---

# Instalação via Akretion Docky

## 📋 Pré-requisitos de instalação

Para fazer a instalação do [Docky](https://github.com/akretion/docky) você precisa ter em seu ambiente o Docker CE instalado em seu ambiente, após a instalação:

### Instalação do Docky

Para instalar o docky basta instalar :

```text
$ pip install docky
```

{% hint style="info" %}
Caso você já tenha feito a instalação antes, certifique-se que tem a versão atualizada adicionando o argumento --upgrade no comando acima.
{% endhint %}

Caso queira saber mais informações sobre funcionalidades avançadas do docky acesse a documentação do projeto 👉[aqui](https://github.com/akretion/ak/blob/master/README.md).

### Instalação do AK

Para automatizar tarefas básicas do seu projeto docky você pode instalar a ferramenta [AK](https://github.com/akretion/ak).

```text
$ pip install ak
```

{% hint style="info" %}
Caso você já tenha o ak instalado, certifique-se que tem a versão atualizada adicionando o argumento --upgrade no comando acima.
{% endhint %}

Caso queira saber mais informações sobre como funciona o ak acesse a documentação do projeto 👉[aqui](https://github.com/akretion/ak/blob/master/README.md).

## 📑 Instalando através de um template Odoo Brasil

Existe um template para a criação de um docky já com todas as dependencias

## 💡 Configurando o Odoo e suas dependências

Once you're strong enough, save the world:

{% code title="specs.yaml" %}
```yaml
odoo:
  remotes:
    origin: https://github.com/oca/ocb
  merges:
    - origin 12.0

account-payment:
    modules: []
    src: https://github.com/oca/account-payment 12.0

bank-payment:
    modules: []
    src: https://github.com/oca/bank-payment 12.0

currency:
    modules: []
    src: https://github.com/oca/currency 12.0

server-tools:
    modules: []
    src: https://github.com/oca/server-tools 12.0

server-env:
    modules: ['server_environment']
    src: https://github.com/oca/server-env 12.0

l10n-brazil:
    src: https://github.com/OCA/l10n-brazil 12.0
```
{% endcode %}

## 📡 Configurações de Rede

bla bla bla

## 🚀 Executando e Acessando o Odoo

Para fazer a instalação do [Docky](https://github.com/akretion/docky) você precisa ter em seu ambiente o Docker CE instalado em seu ambiente, após a instalação:

```text
$ docky run
```

{% hint style="info" %}
Super-powers are granted randomly so please [submit an issue](https://github.com/akretion/docky/issues) if you're not happy with yours.
{% endhint %}

Após executar o docky run será criado os containers da sua aplicação e depois entrará no terminal do container principal, para executar o Odoo você deve executar o comando:

```text
$ odoo
```

```bash
2020-04-20 15:42:54,060 2365 INFO ? odoo: Odoo version 12.0 
2020-04-20 15:42:54,061 2365 INFO ? odoo: Using configuration file at /etc/odoo.cfg 
2020-04-20 15:42:54,063 2365 INFO ? odoo: addons paths: ['/data/odoo/addons/12.0', '/odoo/links', '/odoo/local-src', '/odoo/src/odoo/addons', '/odoo/src/addons', '/odoo/external-src/account-payment', '/odoo/external-src/bank-payment', '/odoo/external-src/currency', '/odoo/external-src/server-tools', '/odoo/external-src/l10n-brazil', '/odoo/external-src/account-financial-reporting', '/odoo/external-src/server-ux', '/odoo/external-src/reporting-engine'] 
2020-04-20 15:42:54,065 2365 INFO ? odoo: database: odoo@db:5432 
2020-04-20 15:42:54,409 2365 INFO ? odoo.addons.base.models.ir_actions_report: Will use the Wkhtmltopdf binary at /usr/local/bin/wkhtmltopdf 
2020-04-20 15:42:55,092 2365 INFO ? odoo.service.server: HTTP service (werkzeug) running on 0.0.0.0:8069 
2020-04-20 15:42:55,240 2365 INFO odoo-brasil odoo.modules.loading: loading 1 modules... 
2020-04-20 15:42:55,257 2365 INFO odoo-brasil odoo.modules.loading: 1 modules loaded in 0.02s, 0 queries 
2020-04-20 15:42:55,448 2365 INFO odoo-brasil odoo.modules.loading: updating modules list 
2020-04-20 15:42:55,461 2365 INFO odoo-brasil odoo.addons.base.models.ir_module: ALLOW access to module.update_list on [] to user __system__ #1 via n/a
```

