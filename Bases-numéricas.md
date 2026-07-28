# Anotações — Bases Numéricas

## Aula 1 (Notação Posicional)

### Expoentes
- "Elevado a" = quantas vezes multiplica o número por ele mesmo
- 10 elevado a 1 = 10
- 10 elevado a 2 = 100
- 10 elevado a 3 = 1000
- No 10: o expoente = quantidade de zeros
- REGRA: qualquer número elevado a 0 = 1

### Ordem do cálculo
- Resolve o expoente PRIMEIRO, depois multiplica
- Ex: 7 × 10² → 10² = 100 → 7 × 100 = 700

### Notação posicional (decimal)
- Cada casa vale uma potência de 10
- Unidade = 10⁰ = 1
- Dezena = 10¹ = 10
- Centena = 10² = 100
- Unidade de milhar = 10³ = 1000
- A posição carrega o peso; o dígito diz "quantos" daquele peso
- Ex: 3705 = (3×1000)+(7×100)+(0×10)+(5×1)

## Aula 2 (Binário)

### Régua de valores (decorar)
16 - 8 - 4 - 2 - 1 ... (dobra sempre: 32, 64, 128)

### Contagem em binário
- Só


## Bases Numéricas — Aula 2 (Binário

### Régua de valores (decorar)
16 - 8 - 4 - 2 - 1 ... (dobra sempre: 32, 64, 128)

### Binário → Decimal
- Escreve os pesos embaixo, da direita pra esquerda
- Soma SÓ as casas que têm 1 (onde tem 0, ignora)
- Ex: 1011 = 8+2+1 = 11

### Decimal → Binário (método da subtração)
- Começa pela MAIOR casa que cabe no número
- Pergunta "cabe ou não cabe?" em cada casa
- Se cabe: marca 1 e subtrai. Se não: marca 0
- Ex: 12 → 8 cabe (sobra 4) → 4 cabe (sobra 0) → 1100

### Decimal → Binário (método da divisão)
- Divide por 2 sucessivamente, anota os restos
- Lê os restos de baixo pra cima

### Regra do zero
- Zero à esquerda (na frente) não vale nada, pode tirar
- Ex: 01100 = 1100
- Zeros do meio e do fim FICAM (valem posição)

## Aula 3 — Octal e Hexadecimal

### As bases e seus algarismos
- Binário (base 2): 0 e 1
- Octal (base 8): 0 a 7 (8 algarismos)
- Decimal (base 10): 0 a 9 (10 algarismos)
- Hexadecimal (base 16): 0 a 9 e A,B,C,D,E,F
  - A=10, B=11, C=12, D=13, E=14, F=15

### Decimal → Octal / Hexadecimal (método da divisão)
- Divide pela base, anota os restos, lê de baixo pra cima
- Octal: divide por 8 / Hexadecimal: divide por 16
- No hexa, se o resto der 10+, vira letra (10=A ... 15=F)

### Conversão entre bases (método das potências)
- Passa pelo decimal no meio
- Ex: binário 1100 → decimal (8+4=12) → hexadecimal (C)
- Ex: hexadecimal F → decimal (15) → binário (1111)

### Notação
- 0x na frente = marca que indica hexadecimal (ex: 0xFF)
- O "0" do 0x não é valor, é só rótulo

- ## Aula 4 — Macete de conversão (agrupamento de bits)

### Binário → Octal (grupos de 3)
- Agrupa os bits de 3 em 3, da direita pra esquerda
- Cada grupo de 3 bits vira um algarismo de 0 a 7
- Se faltar bit no último grupo, completa com zero à esquerda

### Binário → Hexadecimal (grupos de 4)
- Agrupa os bits de 4 em 4, da direita pra esquerda
- Cada grupo de 4 bits vira um símbolo de 0 a F
- Se faltar bit no último grupo, completa com zero à esquerda

### Por que funciona
- É muito mais rápido que dividir ou usar potências
- É o método que profissionais usam no dia a dia

