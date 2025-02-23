IPv6 possui 128 bits e são representados em hexadecimais, onde 4 bits são representados em um único hexa (16 bits em um hexteto), os 128 bits são divididos em 8 hextetos.

## ~={green}Cabeçalho=~
![[Pasted image 20250223174657.png]]

---
## ~={green}Representação do IPv6=~

* 0 a esquerda são omitidos.
* Hextetos com 0s consecutivos podem ser omitidos.
* Dois pontos duplos (::) representam múltiplos hextetos com 0s consecutivos e eles só podem ser usados uma vez.


---
## ~={green}Tipos de endereço=~

* **Unicast**: Envia pacotes para um único destinatário.
* **Multicast**: Envia pacotes para múltiplos destinatários.
* **Anycast**: Envia pacotes para o destinatário mais próximo.

**Obs: IPv6 não possui broadcast.**

### Tipos de Unicast

* Endereço de Unicast Global (GUA) - Endereços de internet roteavies e globalmente exclusivos (equivalente ao IPv4 público), ::/32 ou ::/48 reservados como prefixo global + ::/16 para sub-rede e o resto para host.

* Endereço de Unicast Link-Local (LLA) - Necessário para cada dispositivo habilitado para IPv6. Usado para comunicação local.
Link indica uma sub-rede e não são roteaveis, ou seja, se comunicam apenas com dispositivos na mesma sub-rede.
fe80::/10, 54 bits em 0 e 64 bits para host.

* Endereço de Unicast Único (ULA) - Endereços privados, não roteaveis globalmente, fc00::/7
    * São utilizados para endereçamento local em sites
    * Dispositivos que nunca precisarão de acesso a outra rede.


---
## ~={green}Comprimento de Prefixo=~

* **/64**: Prefixo padrão para redes (64 bits para rede e 64 bits para host).

## ~={green}Configuração=~

De forma automática IPv6 unicast global

* Configuração automática de endereço stateless (SLAAC)
* Com estado DHCPv6

Obs: Quando o DHCPv6 ou o SLAAC é usado, o LLA do roteador será especificado automaticamente como o endereço de gateway padrão.

Para LLA, só é necessário criar endereços de link local nos roteadores que passarão a ser usados como endereço de gateway padrão.

---
## ~={green}Endereçamento dinâmico GUA=~

No GUA o endereço é obtido dinamicamente através de mensagens ICMPv6, os roteadores enviam mensagens de anúncio de rota (RA) para todos os dispositivos na rede. Uma mensagem de resposta RA também é enviada para o dispositivo que enviou um ICMPv6 de RS (solicitação de roteador).

1 - As mensagens RS são enviadas a todos os roteadores IPv6 por hosts solicitando informações de endereçamento
2 - Mensagens RA são enviadas para todos os nós IPv6.

### RA

Uma mensagem ICMPv6 de RA inclui:
* Prefixo de rede e comprimento do prefixo - informa ao dispositivo a que rede ele pertence.
* Endereço do gateway padrão - endereço LLA IPv6 (endereço origem da mensagem).
* Endereços DNS e nome de domínio.

#### Metodo 1: SLAAC

O dispostivio cria seu próprio GUA (IPv60 com ID de interface 64 bits) sem os serviços DHCPv6, eles dependem das mensagens de RA do roteador para obter informações (prefixo/comprimento de rede, gateway e DNS).

#### Metodo 2: SCLAAC e DHCPv6 stateless

Obtem as informações a partir do RA e as demais a partir do DHCPv6. As mensagens RA usam SLAAC para criar IPv6 GUA, o LLA do roteador (endereço IPv6 de origem RA) como endereço gateway padrão e o DHCPv6 para obter o DNS e outros serviços.

#### Metodo 3: DHCPv6 stateful

As informações são obtidas apenas através do DHCPv6, o RA apenas obtem prefixo/rede e **gateway padrão**. Um servidor DHCPv6 stateful aloca e mantém uma lista dos dispositivos que recebem endereços IPv6.

### Processo EUI-64

Ao usar mensagem RA SLAAC ou DHCPv6 stateless a ID da interface pode ser gerada automaticamente, processo que usa endereço MAC de 48 bits e adiciona 16 bits.

* Identificador Organizacional Exclusivo (OUI) - Código de 24 bits do fornecedor (6 dígitos hexadecimais) atribuido pela IEEE.

* Identificador de dispositivo - Valor de 24 bits (6 dígitos hexadecimais) com um OUI em comum.

---
## ~={green}Principais tipos de endereçamentos=~

- **Global Unicast (GUA)**: roteável na Internet (começa, em geral, com 2xxx).
- **Link-Local (fe80::/10)**: válido apenas no enlace local, obrigatório em cada interface (substitui, em parte, o que ARP fazia para IPv4).
- **Unique Local (fc00::/7)**: uso privado, não roteado publicamente.
- **Multicast (ff00::/8)**: endereços para grupos específicos (equivalente ao multicast IPv4).

---
## ~={green}NDP (Neighbor Discovery Protocol)=~

- Substitui ARP e também gerencia a descoberta de roteador, verificação de alcance (Reachability).
- **Neighbor Solicitation (NS)** e **Neighbor Advertisement (NA)**: para descobrir MAC de um IPv6 específico, checar duplicatas (DAD), etc.
- **Router Solicitation (RS)** e **Router Advertisement (RA)**: um host pergunta pelos roteadores (RS); roteadores respondem com prefixos e configuração (RA). Pode-se usar SLAAC ou DHCPv6.