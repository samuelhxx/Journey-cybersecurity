# Hierarquia / Estrutura de uma Rede

Como as peças se encaixam, do mais amplo pro mais específico.

## A estrutura (do maior pro menor)

1. **Internet** — a rede mundial. Todas as redes do planeta conectadas.

2. **Rede (rede local)** — um grupo de dispositivos conectados entre si.
   - Exemplos: minha casa (rede pequena) ou uma empresa (rede grande)
   - Mesma lógica, muda só o tamanho e a quantidade de dispositivos
   - A internet é feita de milhões dessas redes conversando

3. **Roteador / Gateway** — o equipamento que conecta a rede à internet.
   - É a "porta de saída" da rede
   - Fica na fronteira entre a rede local e o mundo

4. **Host** — cada dispositivo dentro da rede.
   - PC, celular, impressora, servidor
   - São os "moradores" da rede

5. **Servidor** — é um TIPO de host (não um nível separado).
   - Um host com a função de servir/entregar informação

## Esquema visual

INTERNET (tudo)
└── REDE (minha casa, uma empresa)
└── ROTEADOR/GATEWAY (porta de saída)
└── HOSTS (os dispositivos)
├── meu PC (host agindo como cliente)
├── meu celular (host/cliente)
└── servidor (host que serve)


## Ponto-chave (o que confunde)

- **Servidor é um host**, não um nível acima nem abaixo. É um host com função de servir.
- **Cliente e servidor são PAPÉIS, não hierarquia.** O mesmo host pode ser cliente numa hora e servidor em outra.
  - Meu PC pedindo uma página = cliente
  - Meu PC compartilhando arquivo = servidor naquele momento

## Analogia do bairro

- **Rede** = o bairro
- **Gateway** = a saída do bairro pra cidade (internet)
- **Hosts** = as casas do bairro
- **Servidor** = uma casa que fornece algo (tipo a padaria)
- **IP** = o endereço de cada casa
- **DNS** = a lista telefônica que traduz nome em endereço

## Conexão com as classes de IP

- Casa = rede pequena (tipo classe C, poucos hosts)
- Empresa grande = rede maior (classe B ou A, milhares de hosts)
- Mesma lógica, escala diferente
