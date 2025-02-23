A Qualidade de Serviço (QoS) em redes é um conjunto de técnicas, modelos e protocolos voltados para garantir que determinados fluxos de tráfego recebam tratamento diferenciado e que requisitos como largura de banda, atraso (delay) e perda de pacotes sejam atendidos de forma adequada.

## ~={purple}**1. Contexto e Motivação da QoS**=~

- **Diferenças entre LAN e WAN**
    
    - **LAN (Rede Local)**: Geralmente mais barata, de alta velocidade (Gbps ou superior) e com grande número de dispositivos gerando tráfego.
    - **WAN (Rede de Longa Distância)**: Mais cara, velocidades inferiores às LANs e com função de interligar escritórios remotos e/ou fornecer acesso à Internet.
    - **Problema**: A WAN se torna o “gargalo”, pois possui capacidade limitada em relação à LAN. Em situações de congestionamento, é preciso alguma forma de priorização ou gerenciamento de pacotes para evitar degradação no desempenho.
- **Ações de QoS**: As alternativas para lidar com congestionamento na WAN podem ser aumentar a capacidade do enlace, descartar pacotes, enfileirar ou priorizar determinados fluxos. É nesse cenário que entram as técnicas de QoS, buscando atender aos requisitos de aplicações críticas.


---

## ~={purple}**2. Principais Características de Tráfego**=~

1. **Bandwidth (largura de banda)**:
    
    - Medida em bits por segundo (bps). O enlace mais lento no caminho de um pacote define a largura de banda efetiva.
2. **Delay (atraso)**:
    
    - **Atraso de Propagação**: Tempo de envio no enlace (depende da velocidade e da distância).
    - **Atraso de Serialização**: Tempo para colocar os bits de um pacote no meio físico.
    - **Atraso de Processamento**: Tempo que um equipamento (roteador, switch etc.) leva para processar o pacote.
    - Pode ser medido apenas de ida (one-way) ou de ida e volta (round-trip).
3. **Jitter (variação de atraso)**:
    
    - Diferença no tempo de chegada de pacotes sucessivos. Pacote 1 chega em 50 ms, pacote 2 em 75 ms, jitter = 25 ms.
    - Afeta especialmente aplicações de voz e vídeo em tempo real, que requerem constância no fluxo.
4. **Packet Loss (perda de pacotes)**:
    
    - Ocorre quando roteadores ou switches descartam pacotes por congestionamento, ou por erros.
    - Essencial reduzir perda para tráfegos sensíveis (p. ex. voz, vídeo).

---

## ~={purple}**3. Modelos de QoS**=~

1. **Best Effort**
    
    - Não há qualquer política de QoS; todo tráfego é tratado igualmente.
    - O tráfego Best Effort é o padrão quando os bits de marcação estão todos em 0.
2. **IntServ (Integrated Services)**
    
    - **Reserva de recursos** fim a fim, utilizando o protocolo RSVP (Resource ReSerVation Protocol).
    - Cada nó na rota precisa suportar reserva de largura de banda para cada fluxo (origem/destino).
    - **Problemas**: Falta de escalabilidade em redes grandes e alocação fixa de recursos mesmo quando não estão em uso.
3. **DiffServ (Differentiated Services)**
    
    - Em vez de reservar recursos explicitamente, a rede é configurada para **classificar** e **marcar** pacotes em diferentes classes de serviço.
    - Cada roteador executa comportamentos (“Per Hop Behavior” - PHP) baseados na marcação dos pacotes, decidindo priorização, enfileiramento, descarte etc.
    - Geralmente é mais escalável, pois não há reserva individualizada para cada fluxo.

- **QoE (Quality of Experience)**: O objetivo final é satisfazer o usuário, garantindo qualidade perceptível no uso de aplicações, resultando da aplicação efetiva de QoS.

---

## ~={purple}**4. Parâmetros Recomendados (Exemplos)**=~

- **Voz**:
    - ~80 Kbps (código G.711), atraso (One Way) menor ou igual a 150 ms, jitter menor ou igual a 30 ms e perda de pacotes menor ou igual a 1%.
- **Vídeo**:
    - Largura de banda que pode variar de 384 Kbps a mais de 20 Mbps, atraso de 200 ms a 400 ms, jitter entre 30 ms e 50 ms e perda de pacotes de 0,1% a 1%.

---

## ~={purple}**5. Funcionamento do IntServ**=~

- **RSVP**: O aplicativo sinaliza para cada roteador a necessidade de largura de banda, solicitando prioridade especial.
- **Vantagem**: Bom para redes pequenas com poucas aplicações críticas.
- **Desvantagem**: Não escala bem em grandes redes; exige suporte e configuração em cada roteador no caminho.

---

## ~={purple}**6. Funcionamento do DiffServ**=~

1. **Classificação e Marcação**
    
    - **Feita normalmente nos nós de borda** (roteadores de entrada/saída):
        - Identifica fluxos importantes e marca os pacotes em um determinado campo do cabeçalho (Layer 2 ou Layer 3).
    - **Camada 2**: Por exemplo, bits de prioridade 802.1Q/P (PCP).
    - **Camada 3**: Campos no cabeçalho IP (Type of Service no IPv4 e Traffic Class no IPv6).
    - Também se pode usar portas TCP/UDP (camada 4) ou identificação de aplicações (camada 7), desde que não criptografadas.
2. **Per Hop Behavior (PHP)**
    
    - Cada roteador verifica a marcação dos pacotes (ex.: DSCP - DiffServ Code Point) e aplica políticas de enfileiramento e descarte específicas.
    - Exemplos de valores DSCP:
        - **Default Forwarding (DF)** ou **CS0** = tráfego comum, melhor esforço.
        - **Assured Forwarding (AF)** = tenta garantir certa banda e oferece níveis de descarte diferentes (AF11, AF12, etc.).
        - **Expedited Forwarding (EF)** = voltado a serviços premium com pouca latência e jitter (por exemplo, voz).
3. **Estratégias de Fila e Descarte**
    
    - Mecanismos como _Weighted Random Early Detection (WRED)_ permitem descarte seletivo de pacotes em congestionamento, priorizando tráfegos marcados como importantes.
4. **SLA (Service Level Agreement)**
    
    - Define, entre provedor e cliente, quais classes de serviço terão prioridade, qual a banda mínima, nível de latência e perdas aceitáveis etc.
    - Os roteadores de borda podem fazer _traffic shaping_ (moldagem de tráfego), limitando ou garantindo banda conforme regras estabelecidas.