A camada de enlace é responsável por organizar e transferir dados entre dois dispositivos que estejam fisicamente conectados, garantindo o envio confiável (ou não, dependendo do protocolo) de **quadros (frames)** no enlace de comunicação.

##### A camada de enlace é subdividida em:
- ~={cyan}**LLC (Logical Link Control)**=~, definida no padrão IEEE 802.2. Faz a interface com a camada de rede (e superiores), podendo prover serviços como controle de fluxo e identificação do protocolo de camada superior. Em muitas redes Ethernet (802.3) modernas, as funções de identificação de protocolo acabam sendo feitas pelo campo EtherType, tornando o LLC pouco adotado (ou usado apenas como “passagem”, sem recursos avançados).
- ~={cyan}**MAC (Media Access Control)**=~, que de fato implementa o formato do quadro, o controle de acesso ao meio (CSMA/CD em half-duplex Ethernet, CSMA/CA em Wi-Fi etc.) e o **endereçamento físico** (endereços MAC).

##### Papel da camada de enlace:
- ~={purple}**Framing**=~: Agrupar bits em **quadros** (frames) com cabeçalho (header) e trailer, definindo início e fim da unidade de transmissão.
- ~={purple}**Controle de Acesso ao Meio**=~: Em redes compartilhadas (half-duplex, como Ethernet clássica ou Wi-Fi), define como as estações detectam se o meio está livre ou ocupado, como lidam com colisões, etc.
- ~={purple}**Endereçamento Físico**=~: Trabalha com endereços MAC de 48 bits (ou 64 bits em algumas tecnologias), usados para identificação única de cada interface de rede.
- ~={purple}**Detecção (ou correção) de Erros**=~: Utiliza bits de verificação (CRC) no trailer do quadro para verificar possíveis erros de transmissão.


---
## ~={pink}Ethernet (IEEE 802.3)=~

##### Estrutura do Quadro Ethernet:
![[Pasted image 20250223165516.png]]

- **Endereços MAC (48 bits)**
    
    - Compostos pelos 3 bytes iniciais (OUI – Organizationally Unique Identifier) + 3 bytes restantes.
    - O byte mais à esquerda também traz bits que indicam se é **unicast/multicast** e se é endereço universal (de fábrica) ou local (alterado manualmente).
    - Exemplo de broadcast: FF:FF:FF:FF:FF:FF.

- **Half-duplex (CSMA/CD)**
    
    - Empregado em redes Ethernet mais antigas (com hubs) ou em topologias onde não é possível full-duplex.
    - Para evitar colisões, as estações “escutam” o meio (carrier sense). Se detectam colisão, enviam sinal de JAM e recomeçam a transmissão após esperar um tempo aleatório.
    - O **tamanho mínimo de quadro (64 bytes)** garante que, caso ocorra colisão, ela seja detectada a tempo por todas as estações.

- **Full-duplex**
    
    - Com switches, cada porta pode operar em full-duplex, e não é necessária detecção de colisão.
    - Há recursos como **controle de fluxo** (IEEE 802.3x), que permite enviar quadros de PAUSE para forçar o transmissor remoto a esperar.

- **Switch Ethernet (Bridge)**
    
    - Opera na camada 2, aprendendo endereços MAC de cada porta e encaminhando quadros de forma seletiva.
    - Em caso de destino desconhecido ou broadcast, encaminha para todas as portas (flooding).
    - Evita colisões em cada porta (full-duplex), mas ainda encaminha quadros de broadcast para todos.
    - Para evitar loops em topologias com ligações redundantes, utiliza o **Spanning Tree Protocol (STP)**.

- **Tipos de Comutação em Switches**
    
    - **Store-and-forward**: recebe o quadro inteiro, verifica CRC, e só então encaminha.
    - **Cut-through**: começa a encaminhar assim que identifica o MAC de destino (menor latência).


---
## ~={pink}LLC e SNAP (802.2)=~
##### Estrutura do Quadro LLC e SNAP (802.2):
![[Pasted image 20250223170137.png]]
- **IEEE 802.2 LLC**
    
    - DSAP, SSAP, Control – campos que podem oferecer (em teoria) serviços de conexão, controle de fluxo etc. Mas, na prática, muitas implementações Ethernet usam apenas o EtherType e não esse cabeçalho.
- **SNAP**
    
    - SubNetwork Access Protocol, que carrega um campo Type (similar ao EtherType).
    - Em algumas redes (ex.: 802.11 Wi-Fi), é comum ver LLC + SNAP para identificar o protocolo superior (IPv4, IPv6 etc.).



---
## ~={pink}Outras Extensões de Quadro Ethernet=~

- **802.1Q (VLAN)**
    
    - Adiciona 4 bytes após o MAC de origem: 2 bytes (TPID, geralmente 0x8100) e 2 bytes (TCI) que incluem ID da VLAN e bits de prioridade.
    - Aumenta o tamanho máximo do quadro para 1522 bytes.

-  **Jumbo Frames**
    
    - Podem chegar a 9000+ bytes de payload (quadro total > 1522). Não é um padrão oficial da IEEE; precisa ser configurado de modo consistente em toda a rede local onde se deseja usar.



---
## ~={pink}Wi-Fi (802.11)=~

-  **Half-duplex e CSMA/CA**
    
    - Não é possível detectar colisão diretamente; tenta-se evitá-la (Collision Avoidance), reservando o meio com base no tempo indicado no cabeçalho do quadro (Duration field).
    - Após a transmissão, o receptor envia um ACK confirmando que recebeu o quadro.

-  **Quadro 802.11**
    
    - Pode ser maior que Ethernet em termos de cabeçalho (existe controle de criptografia, endereços adicionais, etc.).
    - Normalmente, carrega LLC e SNAP para indicar qual protocolo de camada superior está sendo transportado.



---
## ~={pink}Domínios de Colisão e Broadcast=~

-  **Domínio de Colisão**
    
    - Em half-duplex (hubs, Ethernet antiga, redes Wi-Fi), as colisões podem se propagar. Switches segmentam domínios de colisão, pois cada porta full-duplex é isolada.

-  **Domínio de Broadcast**
    
    - Engloba todas as interfaces que recebem quadros de broadcast. Em redes Ethernet com switches (sem roteadores), toda a LAN é um único domínio de broadcast. Roteadores interrompem broadcasts, formando domínios de rede diferentes.