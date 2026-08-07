# Anotações - TryHackMe

## Trilha: Pre Security

### Sala: Offensive Security Intro (Dia 1)
- Primeira sala prática concluída
- 4 tarefas, 32 pontos
- Primeiro contato com hacking ético na prática
- Aprendi o que é segurança ofensiva
## TryHackMe - Offensive Security Intro
- Comando usado: dirb
- O que faz: procura páginas e pastas escondidas em um site
- Testando nomes comuns automaticamente
- Achei uma página oculta do banco falso e acessei a conta 8881
- Conceito: segurança ofensiva = atacar para achar falhas
  
## TryHackMe — Defensive Security Intro

- Cenário: alerta na ferramenta de análise (SIEM)
- Padrão: várias tentativas de acesso em página de admin
- Ação: identifiquei o ID do atacante e bloqueei o acesso ao sistema
- Isso é trabalho de Analista SOC + resposta a incidente (DFIR)

### Conexão com a sala anterior
- Dia 1: eu era o atacante (dirb no BankFake)
- Hoje: eu era quem detectou e bloqueou esse tipo de ataque
- Mesmo cenário, dois lados

## Seção 1 — Introdução à Cibersegurança (COMPLETA)

### Careers in Cyber
- Panorama das carreiras da área
- Meu resultado no teste de perfil: Analista de Segurança
- Área com mais vagas de entrada no Brasil
- Decisão real fica pro mês 7, depois de experimentar cada lado

- ## Seção 2 — Fundamentos de Computador

### Peças do PC
- Nomes dos componentes e onde cada um vai na montagem

### Processo de inicialização (boot) — 5 etapas
1. Press power button — botão de ligar dá o sinal para a CPU
2. Firmware starts — firmware (BIOS/UEFI) na placa-mãe é o primeiro a rodar
3. POST — Power-On Self-Test, testa o hardware (memória, teclado, etc.)
4. Seleção do boot device — escolhe de onde dar boot (HD, SSD, USB)
5. Start bootloader — carrega o bootloader, que inicia o sistema operacional

- Conteúdo denso, registrado para revisar. Vai fixar por repetição ao longo do curso.
- Gancho com cyber: firmware e bootloader são alvo de malware avançado (rodam antes do sistema e do antivírus). Assunto de forense/malware mais à frente.

## Seção 2 — Tipos de Computador

- **Desktop** — computador fixo, de mesa. Comum em escritórios. Alvo de ataque interno.
- **Laptop** — portátil. Mobilidade é a vantagem e o risco (roubo, Wi-Fi público). Costuma ter criptografia de disco.
- **Smartphone** — computador de bolso. Guarda muita informação sensível (banco, fotos, mensagens). Grande alvo de ataque.
- **Servidor** — a máquina que "serve" os clientes (modelo cliente-servidor). Fica ligado 24h. Alvo mais valioso: dominar o servidor = acesso aos dados de todos os clientes.
- **Embarcados / IoT** — computadores dentro de outras coisas (Alexa, câmera, roteador, geladeira inteligente, sensores). Sistema simples embutido. Porta de entrada fácil porque muita gente não protege.

### Ligação com cyber
- Cada tipo de dispositivo é uma porta diferente para ataque
- O atacante escolhe a porta mais fraca (geralmente IoT esquecido, não o PC protegido)
- Preciso saber quais dispositivos existem numa rede para entender por onde ela pode ser atacada

## Seção 2 — Client-Server Basics (Noções Cliente-Servidor)

### Conceito
- Cliente = quem pede (navegador). Servidor = quem entrega (guarda o site)
- O cliente SEMPRE inicia o pedido
- Request (pedido) e Response (resposta) = a conversa entre os dois

### Termos importantes
- **IP address** (Internet Protocol address) = o endereço de um servidor
- **Port** (porta) = identifica um serviço específico rodando no servidor
- **DNS** (Domain Name Service) = traduz o nome do site (ex: site.com) para o IP. Funciona tipo um GPS
- **Protocolo** = as regras de como cliente e servidor se comunicam

### HTTP e HTTPS
- HTTP = protocolo da web (o "idioma" entre navegador e servidor)
- HTTPS = o mesmo, com S de Secure (criptografado, protegido)
- É "stateless" = sem memória, cada pedido é independente
- Sites usam cookies/tokens de sessão pra "lembrar" do login (importante em cyber: alvo de ataque)

### Métodos HTTP
- GET = buscar/pegar um recurso (o mais comum)
- POST = enviar dados / PUT = atualizar / DELETE = apagar

### Prática (F12 → Network)
- Inspecionei requisições GET reais, ao vivo
- Campos: Scheme (http/https), Host, Filename, Address (IP), Status
- Status 200 = sucesso / 304 = não mudou, usa cache
- No laboratório o Address era 127.0.0.1 (site rodando na própria máquina)
- Testei no site real da AS Construction: 29 requests pra montar 1 página
  - Cada peça (logo, css, js) é um GET separado
  - Site hospedado no GitHub Pages

### Ligação com cyber
- A aba Network é ferramenta de reconhecimento web
- Revela tecnologias, arquivos e comportamento do site
- Primeiro passo antes de testar a segurança de uma aplicação (vou aprofundar no PortSwigger)


## Seção 2 — Virtualização

### Conceitos
- Virtualização = um computador físico age como vários computadores separados
- Hipervisor = o software "gerente" que cria e controla as VMs (ex: VirtualBox, VMware)
- Máquina Virtual (VM) = computador virtual inteiro dentro do real, com sistema próprio
- Container (Recipiente) = caixa isolada e leve pra UM aplicativo, compartilha o sistema do host
- Imagem de container = a "receita/modelo" pra criar containers
- Portas de rede = pontos de entrada numerados que apps usam pra falar pela rede

### VM x Container
- São independentes por natureza
- Na prática, às vezes rodam juntos (containers dentro de VM) pra somar vantagens

### Benefícios (destaque pra cyber)
- Teste SEGURO pra cibersegurança (laboratório isolado)
- Economia de custo, uso melhor de recursos, portabilidade, escalabilidade

### Próximo: Cloud (nuvem)
- Nuvem é construída em cima de virtualização + containers + automação

## Seção 2 — Computação em Nuvem (Cloud)

### Tipos de nuvem
- Pública = compartilhada por várias empresas, via internet (AWS, Google Cloud)
- Privada = só de uma empresa, mais controle e segurança
- Híbrida = mistura das duas

### Modelos de serviço (analogia da pizza)
- IaaS = alugar peças básicas (servidor, armazenamento), monta você mesmo → farinha e forno
- PaaS = ambiente pronto pra criar apps, sem gerenciar servidor → massa pronta
- SaaS = software pronto pra usar, sem instalar (Gmail, Zoom) → pizza pronta
- EC2 = serviço da Amazon pra criar computadores na nuvem (exemplo de IaaS)

### Benefícios
- Escalabilidade, pague pelo que usa, alta disponibilidade, acesso global

### Ligação com cyber
- Cloud Security é uma das 4 especializações (a que mais cresce e melhor paga)
- Nuvem mal configurada = causa de muitos vazamentos famosos
- Proteger ambientes cloud (AWS, Azure) é área quente do mercado
