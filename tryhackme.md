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

