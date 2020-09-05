# Detect Connected USB Flash Drive [![OS](https://img.shields.io/badge/OS-Windows-blue.svg?style=for-the-badge)](https://www.microsoft.com/windows/)

Detecção automatizada da unidade USB em que o pendrive está conectado.

## Menu

- [Como fazer](#como-fazer)
- [Motivação](#motivação)

---

## Como fazer

**1.** Baixe o arquivo ``.detect-pendrive`` deste repositório.

**2.** Renomeie .detect-**pendrive** com o nome do seu pendrive ou o que preferir, sem espaços ou acentos, como por exemplo:

~~~
.detect-sandisk
~~~

**Obs.:** Há diferença no uso de letras maiúsculas e minúsculas. Para evitar problemas, adote um padrão: TODAS LETRAS MAIÚSCULAS, ou todas lestras minúsculas.

**3.** Salve o arquivo na raiz do pendrive.

**4.** Copie o código abaixo e cole no seu script ``*.bat``. 

~~~cmd
set SEARCH=detect-pendrive

FOR %%I in (C,D,E,F,G,H,I,J,K,L,M,N,O,P,Q,R,S,T,U,V,W,X,Y,Z) DO (IF EXIST %%I:\.%SEARCH% SET PENDRIVE=%%I)
~~~

**5.** Na variável ``SEARCH``, altere detect-**pendrive** para o nome que você deu ao arquivo no passo **[2](#2)**.

**6.** Ao executar o script, a unidade em que o pendrive está conectado será armazenada na variável ``%PENDRIVE%``.

## Passos adicionais

Recomenda-se ocultar o arquivo salvo na raiz do pendrive, pois ao ficar visível corre o risco de ser deletado por engano.

Por isso, assim que finalizar os passo anteriores, execute o seguinte comando:

~~~cmd
attrib +s +h "UNIDADE:\.detect-pendrive"
~~~

**Obs.:** Altere UNIDADE para a letra da unidade a qual seu pendrive está conectado. Altere detect-**pendrive** para o nome dado ao arquivo anteriormente.

---

## Motivação

Repositório criado para finalidade de estudos. 

O código é útil para automatizar tarefas que envolvam o pendrive, seja para abrir um arquivo recorrente, executar um programa portátil ou salvar dados no mesmo.