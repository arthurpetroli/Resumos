O fluxo dos 32 bits do IPv4 vai da esquerda para a direita, sendo os bits da parte de host exclusivos para identificar um dentro de uma rede e a parte de rede se mantem para os demais dispositivos.

Redes maiores terão partição de hosts maiores

## ~={green}Cabeçalho=~

![[Pasted image 20250223173358.png]]

---
## ~={green}Mascara de Sub-Rede=~

Usada para identificar a parte da rede do IPv4, ela representa todos os dispositivos na mesma rede

| Mascara de Sub-Rede | Endereço de 32 bits | Comprimento |
|---------------------|---------------------|-------------|
| 255.0.0.0 | 11111111.00000000.00000000.00000000 | /8 |
| 255.255.0.0 | 11111111.11111111.00000000.00000000 | /16 |
| 255.255.255.0 | 11111111.11111111.11111111.00000000 | /24 |
| 255.255.255.128 | 11111111.11111111.11111111.10000000 | /25 |
| 255.255.255.192 | 11111111.11111111.11111111.11000000 | /26 |
| 255.255.255.224 | 11111111.11111111.11111111.11100000 | /27 |
| 255.255.255.240 | 11111111.11111111.11111111.11110000 | /28 |
| 255.255.255.248 | 11111111.11111111.11111111.11111000 | /29 |
| 255.255.255.252 | 11111111.11111111.11111111.11111100 | /30 |

O comprimento indica a quantidade de bits reservador para a mascara de sub-rede, /25 indica que dos 32 bits, 25 são reservados.

O primeiro endereço da rede é o endereço de rede (network) e o último é o endereço de broadcast, ambos não podem ser endereços de hosts, ex: uma rede /25 com 126 hosts, terá 128 endereços disponíveis, 126 para hosts, 1 para o endereço de rede e 1 para o endereço de broadcast.

O endereço de broadcast terá todos os bits 1 na parte do host e o de rede 0. Endereço broadcast é usado quando é necessário acessar todos os dispositivos na rede IPv4.

---
## ~={green}AND=~

Para determinar o endereço de rede de um host IPv4, é feito AND lógico bit a bit entre o endereço IPv4 e a máscara de sub-rede, quando se usa AND entre o endereço e a máscara de sub-rede, o resultado é o endereço de rede.

---
## ~={green}Endereços Públicos e Privados=~

Endereços públicos são aqueles que podem ser acessados pela internet, endereços privados são aqueles que não podem ser acessados pela internet, mas podem ser acessados por uma rede local.
Endereços privados são traduzidos para endereços públicos usando a Conversão de Endereços de Rede (NAT), processo geralmente feito pelo roteador.

Prefixos de endereços privados: 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16.

### ~={orange}Endereço Loopback=~

Usado para mandar pacotes para o próprio dispositivo, o endereço é 127.0.0.1

### ~={orange}Classes de Endereços (não usado mais)=~

* Classe A: de 0.0.0.0/8 até 127.0.0.0/8, suporta redes extremamente grandes com mais de 16 milhões de hosts.
* Classe B: de 128.0.0.0/16 até 191.255.0.0/16, suporta redes grandes com até 65 mil hosts.
* Classe C: de 192.0.0.0/24 até 223.255.255.0/24 suporta redes pequenas com até 254 hosts.
* Classe D: de 224.0.0.0 a 239.0.0.0, reservado para multicast.
* Classe E: de 240.0.0.0 a 255.0.0.0, endereços experimentais.

---
## ~={green}Sub Redes=~

Sub-Redes são criadas com um ou mais bits de host sendo usados como bits de rede. A mascara de sub-rede pega emprestado alguns dos bits da parte de host para criar sub-redes. Quanto mais bits de host forem emprestados, mais sub-redes podem ser criadas, mas menos endereços de host estarão disponíveis.

Para cada bit emprestado no quarto octeto, o número de sub-redes disponível é dobrado, enquanto reduz o número de endereços de host por sub-rede.

* Linha /25 - O empréstimo 1 bit do quarto octeto cria 2 sub-redes que suportam 126 hosts cada.
* Linha /26 - O empréstimo de 2 bits cria 4 sub-redes que suportam 62 hosts cada.
* Linha /27 - O empréstimo de 3 bits cria 8 sub-redes que suportam 30 hosts cada.
* Linha /28 - O empréstimo de 4 bits cria 16 sub-redes que suportam 14 hosts cada.
* Linha /29 - O empréstimo de 5 bits cria 32 sub-redes que suportam 6 hosts cada.
* Linha /30 - O empréstimo de 6 bits cria 64 sub-redes que suportam 2 hosts cada.

O número de subredes criadas é sempre 2 elevado ao número de bits emprestados, ex: /27 = 2^3 = 8 subredes. O número de hosts por subrede é 2 elevado a 32 menos o número de bits emprestados menos 2, ex: /27 = 2^(32-27) - 2 = 30 hosts.

Exemplo pratico: criar 1000 subredes

Tendo como endereço 10.0.0.0/8, para criar 1000 subredes é necessário 10 bits emprestados, pois 2^10 = 1024 subredes, o que é suficiente para 1000 subredes. O número de hosts por subrede será 2^(32-18) - 2 = 16382 hosts.

A subrede vai de 10.0.0.0/8 até 10.255.192.0/18 pois passa a ocupar o segundo octeto por completo e dois do terceiro e o endereço de broadcast será 10.0.63.255 (todos os bits de host ativo).

O número que as subredes pulam é igual ao ultimo bit emprestado, exemplo: se o ultimo bit for 32, as subredes vão pular de 32 em 32.


### ~={green}Importante=~

- **ARP (Address Resolution Protocol)**
    
    - Em redes IPv4 sobre Ethernet, um host que quer enviar pacote local a outro IP precisa saber o **MAC** correspondente.
    - ARP resolve IPv4 → MAC enviando **ARP Request** com destino MAC = FF:FF:FF:FF:FF:FF (broadcast). O dono do IP responde com ARP Reply.
    - Cada host mantém a **tabela ARP** com o mapeamento IP↔MAC, expirada após certo tempo.
- **ICMPv4**
    
    - Usado para **diagnóstico** e mensagens de erro, como “Destination Unreachable”, “Time Exceeded”, além do “Echo Request/Reply” (ping).
    - Ferramentas como **ping** (testa acessibilidade) e **traceroute** (descobre roteadores no caminho) baseiam-se no ICMP.
- **Roteamento IPv4**
    
    - Hosts verificam a tabela de rotas locais. Se o destino está na **mesma rede**, enviam ARP e montam o quadro diretamente ao destino; se não, enviam o quadro ao **gateway (roteador)** configurado.
    - Cada roteador decrementa o TTL e encaminha o pacote para o próximo salto até chegar ao destino ou descartar (caso o TTL chegue a zero).