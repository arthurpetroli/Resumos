O protocolo IP não garante que todos os pacotes enviados serão recebidos, ele não é capaz de gerenciar e recuperar pacotes não entregues ou corrompidos.

* Unidade máxima de transmissão (MTU) - é o tamanho máximo da PDU que cada meio consegue transportar. Isto é feito entre a camada de enlace e a de rede, onde é definido um tamanho máximo para o pacote. Se o pacote for maior que a MTU, ele é fragmentado, essa fragmentação acaba causando latência (pacotes IPv6 não são fragmentados pelo roteador).

#### Pacote IPv4

* Tempo de vida (TTL) - Possui um valor binário de 8 bits indicando a vida útil de um pacote. Este valor é diminuído a cada vez que o pacote passa por um roteador, se ele chegar a 0 o pacote é descartado e uma mensagem ICMP é enviada ao endereço IP de origem.

* Endereço IP de origem e destino - 32 bits cada.

#### Gateway padrão

Dispositivo de rede (switch ou roteador) que pode rotear o trafego para outras redes. Em uma rede local este dispositivo é o roteador, ele possui um endereço IP local e os demais hosts da rede possuem o endereço IP do roteador como gateway padrão.

#### Tabela de roteamento do Roteador

O roteador possui uma tabela de roteamento que contém informações sobre as redes que ele conhece. Quando um pacote chega ao roteador, ele verifica o endereço de destino do pacote e consulta a tabela de roteamento para determinar para qual interface o pacote deve ser encaminhado.

* Roteamento estático - configurações de rotas configuradas manualmente, a rota deve ser reconfigurada se houver alterações na topologia ou a rota não estiver disponível

    ```
        ip route <ip-local> <broadcast> <ip-rota>
    ```

* Roteamento dinâmico - roteadores aprendem automaticamente as redes remotas, eles compartilham informações de roteamento com outros roteadores, dessa forma eles podem escolher o melhor caminho para as redes de destino

---
## MAC e IP

Quando o endereço IP de destino estiver em uma rede remota, o endereço MAC de destino será o endereço do gateway padrão.

## ARP

Um dispositivo utiliza o protocolo ARP para determinar o endereço MAC de destino de um dispositivo local quando conhece o endereço IPv4.

A tabela ARP é uma tabela armazenada na memória RAM do dispositivo (cache ARP), ela é usada para encontrar o endereço MAC que é mapeado para o endereço IPv4 do quadro.

* Se o endereço IPv4 destino do pacote estiver na mesma rede que o endereço IPv4 origem, o dispositivo pesquisará o endereço IPv4 destino na tabela ARP.

* Se o endereço IPv4 destino do pacote estiver em uma rede diferente do endereço IPv4 origem, o dispositivo pesquisará o endereço IPv4 do gateway padrão na tabela ARP.

As entradas da tabela ARP tem um timestamp, se um dispositivo não receber um quadro de um outro antes que o tempo expire, essa entrada então será removida da tabela e se nenhum dispositivo responder à requisição ARP, o pacote será descartado.

Caso o IPv4 de destino não estiver na mesma rede o ARP request será enviado com endereço para o MAC de destino do roteador (gateway padrão)

Obs: o IPv6 usa protocolo NPP para determinar o endereço MAC de um dispositivo