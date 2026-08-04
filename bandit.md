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
