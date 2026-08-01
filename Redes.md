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

## Aulas 9 e 10 — Comandos de Rede e Configuração de Roteador

### ping (descobrir IP e testar conexão)
- Comando: ping + endereço do site
- Mostra o IP do servidor e o tempo de resposta
- Funciona como um "sonar": manda sinal e espera resposta
- Descoberta prática: pinguei o site da AS Construction, resposta de 7ms com 32 bytes
  - 7ms = tempo de ida e volta (rápido = boa conexão)
  - 32 bytes = tamanho do pacote de teste

### ping 127.0.0.1 (loopback / localhost)
- Testa a própria máquina ("eu estou funcionando?")
- Se responde: rede interna do PC OK, problema é pra fora
- Se não responde: problema interno na própria máquina
- Primeiro teste de diagnóstico de rede

### tracert (rastrear rota)
- Comando: tracert + endereço do site
- Mostra o CAMINHO completo até o servidor (cada roteador/salto)
- Diferente do ping (que só confirma se está online)
- Descoberta prática: rastreei o site da AS Construction e descobri que está hospedado no GitHub Pages
- Isso é reconhecimento de infraestrutura: descobrir ONDE e COMO o alvo está hospedado

### ipconfig (informações da própria máquina)
- Mostra meu IP, máscara de rede e gateway (IP do roteador)
- Meu gateway: 192.168.1.1
- Em cyber: primeiro comando pra "se localizar" na rede
- Atacante que invade uma máquina roda isso pra saber onde caiu

### Acessar painel do roteador
- Digita o gateway (192.168.1.1) na barra de endereço do navegador
- Abre a tela de configuração do roteador
- No meu caso não abriu (nem no PC nem no celular) = bloqueio da operadora

### MAC address e clonagem de MAC
- MAC = número único de cada placa de rede (identidade fixa do aparelho)
- IP muda, MAC é fixo de fábrica
- Clonar MAC = copiar a identidade de um aparelho pra outro
- Uso legítimo: manter acesso ao trocar de aparelho (antigo pro novo)
- Uso malicioso (MAC spoofing): se passar por aparelho autorizado pra entrar em rede protegida
- Mesma técnica, intenção diferente

### Comandos aprendidos (resumo)
| Comando | O que faz |
|---------|-----------|
| ping | descobre IP e testa se está online |
| tracert | mostra o caminho até o servidor |
| ipconfig | mostra minhas infos de rede |

## Aula 11 — Configurações Avançadas de Wi-Fi

### Tipos de segurança Wi-Fi (criptografia)
- WEP = mais antigo e MUITO fraco (nunca usar)
- WPA = ultrapassado
- WPA2 = padrão atual, seguro
- WPA3 = mais novo e mais forte (melhor opção)
- Regra: WEP nunca / WPA2 bom / WPA3 melhor

### Pessoal x Empresarial
- Pessoal (PSK) = uma senha única pra todos (uso em casa)
- Empresarial (Enterprise) = login individual por pessoa, servidor RADIUS (empresas)
- Empresarial é mais seguro: corta acesso de UMA pessoa sem trocar tudo

### Modos puro x misto
- Puro = aceita só uma versão (mais seguro)
- Misto = aceita duas versões (mais compatível, menos seguro)
- No misto, a rede fica tão segura quanto a versão MAIS FRACA
- Princípio: "a corrente é tão forte quanto o elo mais fraco"


### Padrões de Wi-Fi (VELOCIDADE, não confundir com segurança)
- B (antigo/lento) → G → N → AC → AX/Wi-Fi 6 (novo/rápido)
- É tipo gerações de celular (3G, 4G, 5G)
- WPA = segurança / B-G-N = velocidade (coisas diferentes!)

### Canais do Wi-Fi
- Canais = faixas de uma estrada
- Vários roteadores no mesmo canal = interferência
- Solução: programa mostra roteadores e canais → escolher canal vazio
- Esse programa é ferramenta de RECONHECIMENTO de redes sem fio (usado em pentest de Wi-Fi)

### Posicionamento do roteador
- Lugar central, alto, longe de parede grossa e eletrônicos
- É sobre desempenho físico, não segurança

### Máscara de rede
- Separa a parte REDE da parte HOST dentro do IP
- Onde tem 255 = parte da rede (fixa). Onde tem 0 = parte dos hosts (varia)
- Ex: IP 192.168.1.10 / máscara 255.255.255.0 → rede = 192.168.1, host = último número
- /24 = a mesma máscara escrita curto (255.255.255.0 = 24 bits ligados)

### Broadcast
- Último endereço da rede, fala com TODOS os hosts de uma vez
- Ex: 192.168.1.255
- Analogia: megafone (todos escutam de uma vez)

### Estrutura da rede (exemplo /24)
- Rede: 192.168.1.0 (primeiro, identifica a rede)
- Hosts: 192.168.1.1 até .254 (as máquinas usáveis)
- Broadcast: 192.168.1.255 (último)
- 256 endereços - 2 reservados (rede e broadcast) = 254 hosts

### Máscara padrão de cada classe
- Classe A → 255.0.0.0 (/8) → 1 octeto rede, 3 de host → milhões de hosts
- Classe B → 255.255.0.0 (/16) → 2 octetos rede, 2 de host → milhares de hosts
- Classe C → 255.255.255.0 (/24) → 3 octetos rede, 1 de host → 254 hosts
- A máscara define quantos octetos são rede e quantos são host
- Por isso cada classe tem sua máscara (mais host = classe mais "baixa")

## Aula 12 — Sub-redes (CONCEITO OK, cálculo PENDENTE)

### O que entendi (suficiente por agora)
- Sub-rede = dividir uma rede grande em pedaços menores
- Serve pra: separar por setor (RH, produção, convidados) e por SEGURANÇA
- Segmentação: se invadem uma sub-rede, não alcançam as outras
- Cada sub-rede tem sua própria: rede, faixa de hosts e broadcast
- Máscara define onde termina a rede e começam os hosts (255 = rede, 0 = host)
- /24 = 255.255.255.0

### O que ficou PENDENTE (aprofundar depois)
- O CÁLCULO de sub-rede à mão (octeto misto, divisão em bits)
- O vídeo gratuito não ensina o "porquê", só o curso pago
- Envolve binário aplicado, mas faltou a ponte entre binário e sub-rede
- PLANO: aprender o cálculo na faculdade (ou curso dedicado) com explicação completa
- Por agora: conceito entendido, cálculo é conteúdo avançado pra depois
