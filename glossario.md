# Glossário de Redes e Cibersegurança

Termos básicos pra consultar sempre que precisar.

## Redes — Fundamentos

**Host**
- Qualquer dispositivo conectado na rede (PC, celular, servidor, impressora)
- É o aparelho que está na rede

**Servidor**
- A máquina que guarda e entrega informação quando o cliente pede
- Cliente pede, servidor serve
- Ex: o servidor do YouTube guarda os vídeos e manda pra você

**Cliente**
- Quem faz o pedido (o navegador, teu dispositivo)
- O cliente SEMPRE inicia a conversa

**IP (Internet Protocol address)**
- O endereço de identificação de um dispositivo na rede
- Cada aparelho tem o seu, é como ele é encontrado
- Tem 4 octetos (ex: 192.168.1.1), cada um de 0 a 255

**IP público x privado**
- Privado = usado DENTRO da rede local (casa, empresa). NÃO vai pra internet
- Público = o endereço que a internet usa pra te achar
- Faixas privadas: 10.x / 172.16.x / 192.168.x

**Gateway**
- O IP do roteador — a "porta de saída" da rede pra internet
- Todo o tráfego passa por ele pra chegar na internet
- Analogia: a portaria do prédio

**DNS (Domain Name Service)**
- Traduz o nome do site (google.com) pro IP (o número)
- Funciona como um GPS: você dá o nome, ele dá as "coordenadas" (IP)
- Existe porque a gente decora nomes, mas o computador só entende IP

**MAC address**
- A identidade única de cada placa de rede (fixa de fábrica)
- O "nome de nascença" do aparelho
- IP muda, MAC não

**Protocolo**
- As regras de como duas máquinas conversam
- Define comandos, formato e respostas
- Ex: HTTP é um protocolo

## Web

**HTTP**
- Protocolo da web (regras entre navegador e servidor)
- Conversa ABERTA, sem criptografia

**HTTPS**
- O mesmo que HTTP, mas CRIPTOGRAFADO (S = Secure)
- Conversa trancada, protegida no caminho
- O cadeado no navegador
- (Criptografado, não "privado" — não confundir com IP privado)

**Stateless**
- "Sem memória": o servidor não lembra dos pedidos anteriores
- Vale pra HTTP e HTTPS
- Por isso sites usam cookies/tokens pra lembrar do login

**GET**
- Método/pedido pra BUSCAR algo do servidor
- Cliente pede com GET, servidor responde
- O pedido mais comum da web

**Comandos de rede (CMD)**
- ping = descobre IP e testa se está online
- tracert = mostra o caminho (saltos) até o servidor
- ipconfig = mostra minhas infos de rede (IP, gateway, máscara)
