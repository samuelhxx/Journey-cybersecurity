## Curso de Linux — Partições do pendrive
- Partição = divisão de um disco/pendrive em partes separadas
- O Etcher cria partições especiais ao gravar o Linux
- Pra reusar o pendrive normal: remover as partições e formatar
- Conceito volta na instalação real do Linux (definir partições do disco)
- Em cyber: útil pra forense (analisar discos) e administração
## Curso de Linux — Aulas 4.2, 5 e 6.1

### Aula 4.2 — Pendrive de instalação
- Criar pendrive de instalação com o Etcher (grava o Linux no pendrive)
- Live USB: dá pra testar o Linux rodando do pendrive, sem instalar
- Zerar/remover partições do pendrive depois de usar
- (Não fiz na prática - instalação real fica pra quando montar o laboratório em VM)

### Aula 5 — Conhecendo o ambiente Mint
- Linux Mint = uma distribuição (versão) do Linux, amigável pra iniciante
- Área de trabalho, menus, organização do sistema
- Familiarização com como o Mint é organizado (diferente do Windows, mesma lógica)

### Aula 6.1 — Instalação básica de programas no Mint
- Central de Programas (visual, tipo loja de apps) - instala clicando
- Forma mais fácil pra iniciante, sem terminal

### Conceito: Repositório
- Grande "armazém oficial" de programas online
- O Linux busca os programas de lá pra instalar
- Programas verificados e seguros,

## Curso de Linux — Aula 6.2 (Instalação avançada de programas)

### Os 4 modos de instalar programa no Linux (Mint)
1. Central de Programas — visual, tipo loja de apps (mais simples)
2. Synaptic — gerenciador visual completo (pesquisa no repositório, mais controle)
3. apt / apt-get — pelo terminal, busca no repositório online
4. dpkg — instala arquivo .deb baixado do site do fabricante

### Repositório
- "Armazém oficial" de programas online
- O apt busca os programas de lá
- Programas verificados e seguros

### Comandos do apt (terminal)
- sudo apt install [programa] → instala (busca no repositório)
- sudo apt remove [programa] → remove
- sudo apt update → atualiza a LISTA de programas do repositório
- sudo apt upgrade → atualiza os programas já instalados
- apt search [nome] → procura programa
- apt moo → easter egg (vaquinha em ASCII, só brincadeira)

### apt x apt-get
- apt-get = comando antigo/original (mais técnico, usado em scripts)
- apt = versão moderna e simplificada (uso diário)
- Fazem a mesma coisa

### dpkg (instalar arquivo .deb externo)
- .deb = arquivo instalador do Linux (tipo o .exe do Windows)
- Usado pra programa baixado direto do site (ex: VS Code)
- Comando: sudo dpkg -i arquivo.deb  (o -i = install)
- APONTAR o arquivo certo: ou entra na pasta com cd, ou dá o caminho completo
  - Ex: cd Downloads → sudo dpkg -i code.deb
  - Se der erro de dependência: sudo apt install -f (conserta o que faltou)

### apt x dpkg (a diferença)
- apt = busca no repositório online e instala ("me traz o programa")
- dpkg = instala arquivo .deb que já está na máquina ("instala esse arquivo aqui")

### sudo e root (MUITO importante pra cyber)
- $ no terminal = usuário normal (precisa de sudo pra tarefas de admin)
- # no terminal = root/administrador (poder total, não precisa de sudo)
- sudo = "fazer como admin" temporariamente (pede senha)
- root = controle total da máquina
- Em cyber: sempre observar se você é $ ou #; escalação de privilégio = virar root

### Famílias de Linux e instalação
- Debian/Ubuntu/Mint (a minha) → dpkg, apt, arquivos .deb
- Red Hat/Fedora → rpm, dnf, arquivos .rpm
- Arch → pacman
- Kali Linux (cyber) é família Debian → usa apt/dpkg igual meu Mint (o que aprendo serve!)

### Ferramentas instaladas na prática
- htop = mostra processos em tempo real (tipo Gerenciador de Tarefas do Windows)
- VS Code = editor de código
