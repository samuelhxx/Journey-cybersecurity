# Anotações - Curso de Redes

## Aula 1
- Aula introdutória sobre o que o curso vai cobrir
- Problema real mostrado: duas redes Wi-Fi se interferindo no estúdio
- O celular conectava na rede de outro andar em vez da mais próxima
- Vou aprender a diagnosticar e resolver esse tipo de problema

## Aula 2 e 3
- Aula 2: análise de redes próximas com programa gratuito
  - Mostra canais em atrito (interferência) e potência de cada rede
  - Isso é diagnóstico de rede
- Aula 3: compra e configuração de novos roteadores
  - Resolução de interferência trocando e configurando equipamentos
- Conceito: entender a rede por dentro é base para protegê-la depois
  
## Redes — Aulas 4, 5 e 6

### Aula 4 — Evolução das Redes
- Como as redes surgiram e evoluíram

### Aula 5 — Classificação das Redes
- Modelo cliente-servidor
- Servidor: fornece o serviço (ex: YouTube)
- Cliente: consome o serviço (minha máquina)

### Aula 6 — Tipos de Redes
- Tipos de servidor: dados, impressão, web, etc.
- Cada tipo guarda coisas diferentes = alvos diferentes em segurança

### Ligação com cyber
- Todo ataque a site é um cliente falando com servidor de forma inesperada
- Foi o que fiz com o dirb na primeira sala do TryHackMe

## Aula 7 e 8 — Endereçamento IP

### Estrutura do IP
- IP tem 4 octetos separados por ponto (ex: 192.168.0.1)
- Cada octeto vai de 0 a 255
- Computador lê em 0 e 1 (binário), a gente lê em decimal

### Classes de IP (primeiro octeto)
| Classe | Faixa |
|--------|-------|
| A | 0 a 127 |
| B | 128 a 191 |
| C | 192 a 223 |
| D | 224 a 239 |
| E | 240 a 255 |

- A classe define quantos IPs cabem na rede
- Classe A: redes gigantes / Classe B: dezenas de milhares / Classe C: redes pequenas
- Ex: 179 é classe B

### Tipos de comunicação
- **Unicast** — um para um
- **Broadcast** — para todos
- **Multicast** — para um grupo selecionado
- **Anycast** — para qualquer um, o mais próximo

### IPs privados (redes internas)
- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

São privados por convenção internacional. Roteadores da internet descartam pacotes dessas faixas. Por isso todo mundo pode usar os mesmos IPs internamente sem conflito.

O /8, /12, /16 é a máscara de rede (define o tamanho da faixa) → aprofunda na aula 12.

### IPs especiais
- **127.0.0.0** — loopback / localhost. Fala com a própria máquina.
- **169.254.0.0** — IP de emergência. Aparece quando falha o DHCP.

### Estrutura de uma rede
- **Endereço de rede** — primeiro IP, identifica a rede. Não é usado por máquina.
- **Hosts** — IPs do meio. Os dispositivos de verdade (PC, celular, impressora).
- **Broadcast** — último IP, fala com todos os hosts de uma vez.

### Conceitos que ficaram pra depois
- Fixo x dinâmico (DHCP)
- Cálculo de sub-redes → aula 12
- Binário na prática → curso Bases Numéricas (Dias 4 e 5)
