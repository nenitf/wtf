---
title: "Utilização normal diária do Git"
summary: "Utilização comum do Git"
date: 2020-07-29T10:32:31-03:00
toc: true
tags: ["git"]
draft: false
---

Git um Sistema de Controle de Versão Distribuído (DVCS). Ele registra mudanças feitas em um ou mais arquivos ao longo do tempo de forma que você possa recuperar versões específicas. Cada "estado" do arquivo é salvo através de *commits*, cujo possuem *hashes* (identificadores únicos) e mensagens.

## Estados de arquivos
Um arquivo no git podem estar em 1 dos 4 estágios:
* `untracked`: não versionado no commit anterior;
* `not staged`: sofreu mudanças desde o ultimo commit e ainda não foi selecionado para o próximo commit;
* `staged`: sofreu mudanças e foi selecionado para o próximo commit;
* `commited`: não foram modificados desde o ultimo commit;

## Fluxos de trabalho


{{< gravizo "Fluxo de desenvolvimento" >}}
  digraph G {
    node [shape=box]
    init [label="git init"];
    clone [label="git clone <url>"];
    work [label="cria/deleta/modifica arquivos"];
    add [label="git add <arquivo>"];
    commit [label="git commit -m '<mensagem de commit>'"];
    push [label="git push origin HEAD"];

    init -> work;
    clone -> work;
    commit -> work;
    push -> work;

    work -> add;
    add -> commit -> push;
  }
{{< /gravizo >}}

### Individual

É mais simples versionar o código quando está trabalhando sozinho em um projeto, portanto essa seção abordará o escopo de comandos mínimos necessários para essa situação.
Abaixo uma figura no fluxo de trabalho explicado na seção:


---

### Gitflow

- [Instruções Gitflow](https://danielkummer.github.io/git-flow-cheatsheet/index.pt_BR.html)
- [Post original Gitflow](https://nvie.com/posts/a-successful-git-branching-model/)
- [Transcrição do cli do gitflow para o git comum](https://www.atlassian.com/br/git/tutorials/comparing-workflows/gitflow-workflow)

<!-- github flow? -->

