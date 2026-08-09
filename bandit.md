# Bandit (OverTheWire) — Senhas e Progresso

## Level 0 → Level 1
- Objetivo: achar a senha do próximo nível, guardada no arquivo "readme"
- Comandos usados:
  - `ls` → listou os arquivos (achei o readme)
  - `cat readme` → mostrou o conteúdo, com a senha no final
- Senha do Level 1: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR

## Level 2 → Level 3
- Entrei no Level 2
- Lição: cuidado com l(minúsculo), I(maiúsculo) e 1(número) - se confundem no terminal

## Level 2 → Level 3
- Arquivo com nome "--spaces in this filename--" (espaços E traços nas pontas)
- Aspas resolvem espaços, ./ resolve os traços do início
- Comando: cat "./--spaces in this filename--"
- Senha do Level 3: 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME

## Level 3 → Level 4
- Tinha uma PASTA chamada "inhere" (a senha estava dentro dela)
- cd inhere → entrei na pasta (cd = change directory, entrar em pasta)
- ls -a → revelou arquivo oculto "...hiding-from-you" (começa com ponto = escondido)
- cat ./ + nome → li o arquivo oculto
- Senha do Level 4: xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq

### Comandos novos aprendidos
- cd = entrar numa pasta
- ls -a = ver arquivos ocultos

## Level 4 → Level 5
- Vários arquivos (-file00 a -file09), só UM tinha a senha (resto era lixo binário)
- file ./* → mostrou o tipo de cada arquivo
- Achei o -file07 como "ASCII text" (os outros eram "data"/binário)
- cat 

## Level 5 → Level 6
- Senha estava em UMA subpasta entre 20 (maybehere00 a 19)
- Pistas: arquivo de 1033 bytes, legível, não executável
- find . -size 1033c → buscou pelo tamanho em todas as subpastas
- Achei em maybehere07/file2
- cat ./maybehere07/file2 → li a senha
- Senha do Level 6: pXa26xhMWaC2SvDotA4r9EgZkulOeSBW

### Comando novo (IMPORTANTE)
- find = busca arquivos por critérios em todas as subpastas
- find . -size 1033c → busca por tamanho (1033 bytes

## Level 6 → Level 7
- Senha escondida no SISTEMA INTEIRO (não na pasta)
- Pistas: dono bandit7, grupo bandit6, tamanho 33 bytes
- find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
- Achei em /var/lib/dpkg/info/bandit7.password
- cat + caminho completo → li a senha
- Senha do Level 7: Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3

### Conceitos novos (importantes)
- find / = busca a partir da raiz (sistema todo)
- -user / -group / -size = critérios de busca (podem ser combinados)
- 2>/dev/null = joga mensagens de erro no "buraco negro" (limpa a tela)
- caminho completo (começa com /) = endereço absoluto de um arquivo

## Level 7 → Level 8
- Senha dentro de data.txt (arquivo ENORME, milhares de linhas)
- Senha estava do lado da palavra "millionth"
- cat não resolve (despeja tudo, vira borrão)
- grep millionth data.txt → achou só a linha com a palavra
- Senha do Level 8: VR1ljMayciFxbnUokuQmJFw6QC9VKtub

### Comando novo (MUITO importante)
- grep = procura uma PALAVRA dentro de um arquivo, mostra só a linha
- Estrutura: grep [palavra] [arquivo]
- É tipo o Ctrl+F (localizar), mas no terminal
- Diferença: find busca ARQUIVOS, grep busca TEXTO dentro de arquivos
