# Comandos Linux — Consulta Rápida

Comandos que aprendi na prática (Bandit). Consultar sempre que precisar.

## Navegação e visualização

**`ls`**
- Lista o que tem DENTRO da pasta atual (arquivos e subpastas)
- Sempre o PRIMEIRO comando: "acende a luz" pra ver o que tem antes de agir

**`ls -a`**
- Lista TUDO, incluindo arquivos ocultos (os que começam com ponto)
- O `-a` vem de "all" (todos)

**`cd`**
- Entra numa pasta (change directory)
- Ex: `cd inhere` → entra na pasta inhere
- Muda tua POSIÇÃO (te move pra dentro da pasta)
- É pra PASTA, não pra arquivo

## Ler arquivos

**`cat`**
- Lê o conteúdo de um arquivo e mostra na tela
- Ex: `cat readme` → mostra o que tá escrito no readme
- É pra ARQUIVO, não pra pasta
- Não muda tua posição, só mostra o conteúdo

## Identificar e buscar

**`file`**
- Mostra o TIPO de um arquivo (texto? binário? imagem?)
- Ex: `file arquivo` → diz se é "ASCII text", "data", etc
- Útil pra achar qual arquivo é legível entre vários

**`find`**
- Busca arquivos por critério, varrendo pasta atual E subpastas
- Ex: `find . -size 1033c` → acha arquivo de exatamente 1033 bytes
  - `.` = a partir desta pasta
  - `-size` = o critério é tamanho
  - `1033c` = 1033 bytes (o "c" = bytes/character)
- Um dos comandos mais poderosos do Linux

## Coringas (wildcards)

**`*` (asterisco)**
- Representa "TODOS os arquivos" (coringa)
- Ex: `file ./*` → aplica o file em todos os arquivos de uma vez
- Transforma "um" em "todos"

## Truques importantes

**`./` (ponto barra)**
- Significa "nesta pasta aqui"
- Usa quando o nome do arquivo confunde o terminal (começa com traço)
- Ex: `cat ./-` → lê arquivo chamado "-" (o ./ evita a confusão)

**Aspas `"..."`**
- Usa pra arquivo com ESPAÇOS no nome
- Ex: `cat "spaces in this filename"` → o terminal entende como UM arquivo só

**TAB (autocompletar)**
- Digita o começo do nome e aperta TAB → completa sozinho
- Evita erro de digitação em nomes difíceis

**`man [comando]`**
- Mostra o manual de um comando (todas as flags e o que faz)
- Ex: `man ls` → manual do ls
- Não precisa decorar flags, consulta aqui

## Lógica geral
1. `ls` primeiro → ver o que tem
2. Depois decide: `cat` (ler arquivo) ou `cd` (entrar em pasta)
3. Se procura algo específico → `find`
