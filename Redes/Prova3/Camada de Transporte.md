A **camada de transporte** em redes é responsável por estabelecer a comunicação lógica entre **aplicativos** que estão sendo executados em hosts distintos, fornecendo serviços como confiabilidade, multiplexação (uso de portas), controle de fluxo e, quando necessário, controle de congestionamento.

## ~={red}Cabeçalho=~
![[Pasted image 20250223175032.png]]

---
## ~={red}1. Visão Geral da Camada de Transporte=~

1. **Comunicação Lógica Entre Aplicativos**
    
    - A camada de transporte lida com a comunicação entre **processos** (aplicações) em máquinas diferentes. É aqui que ocorre a **multiplexação** e **demultiplexação** por meio de números de portas.
    - Cada mensagem que sai da camada de aplicação (dados de um aplicativo) é dividida em segmentos (no caso do TCP) ou datagramas (no caso do UDP), com adição de cabeçalhos específicos.
2. **Identificação de Aplicativos**
    
    - **Números de porta** de origem e destino (0–65535) identificam unicamente cada processo na origem e no destino.
    - Serviços bem conhecidos usam portas específicas (ex.: 80 para HTTP, 443 para HTTPS, 53 para DNS), enquanto clientes tipicamente usam portas dinâmicas (1024–65535).
3. **Big-Endian vs. Little-Endian**
    
    - Nos cabeçalhos de protocolos de transporte (TCP e UDP), os valores (como o número da porta) são representados em **big-endian** (byte mais significativo primeiro).
    - Internamente, computadores x86 costumam usar **little-endian**, mas convertem para big-endian antes de colocar os dados na rede.

---

## ~={red}2. Transmission Control Protocol (TCP)=~

1. **Orientado a Conexão e Confiável**
    
    - Antes de enviar dados, TCP realiza um **handshake de 3 vias (three-way handshake)** para estabelecer a conexão.
    - Oferece serviços como **controle de fluxo**, **controle de congestionamento**, verificação de **integridade** (checksum) e **retransmissão** em caso de perda de pacotes.
2. **Cabeçalho TCP**
    
    - Contém campos como **Porta de Origem** e **Porta de Destino**, **Número de Sequência (Sequence Number)**, **Número de Confirmação (Acknowledgment Number)**, **Tamanho da Janela (Window)**, **Flags** (SYN, ACK, FIN etc.), e **Checksum**.
    - **Flags TCP**:
        - **SYN**: Inicia a conexão.
        - **ACK**: Indica que o campo Acknowledgment Number é válido (confirma o recebimento de dados).
        - **PSH**: Solicita entrega imediata dos dados à aplicação.
        - **FIN**: Finaliza a conexão.
        - **RST**: Reinicia a conexão em caso de erro.
        - **URG**: Dados urgentes (pouco usado).
3. **Estabelecimento da Conexão (Three-Way Handshake)**
    
    1. **SYN** (cliente → servidor): Cliente envia número de sequência inicial.
    2. **SYN + ACK** (servidor → cliente): Servidor confirma o SYN do cliente e envia seu próprio número de sequência.
    3. **ACK** (cliente → servidor): Cliente confirma o SYN do servidor.
    
    - Nesse processo, negociam-se parâmetros como **MSS (Maximum Segment Size)** e **Window Scale**.
4. **Transmissão de Dados**
    
    - Após a conexão estabelecida, o TCP envia segmentos numerados que são **confirmados** (ACK) pelo destinatário.
    - Em caso de perda ou atraso, o emissor pode **retransmitir** os segmentos.
    - O **campo Window** faz parte do **controle de fluxo**, indicando quantos bytes o receptor é capaz de receber.
5. **Encerramento de Conexão**
    
    - Para encerrar a conexão, são trocadas mensagens com as flags **FIN** e **ACK**. Pode haver um **time-wait** para garantir que todos os segmentos tenham sido processados.
6. **Controle de Fluxo**:
    
    - Evita sobrecarregar o receptor enviando dados além do que ele pode processar.
    - **Janela Deslizante (Go-Back-N)**: O emissor pode enviar vários segmentos dentro do tamanho de janela anunciado; aguarda ACKs antes de avançar o envio de novos segmentos.
7. **Controle de Congestionamento**
    
    - Ajusta dinamicamente a taxa de envio para evitar congestionamento no caminho da rede.
    - **TCP Tahoe**, **TCP Reno**, **TCP New Reno** e **TCP CUBIC** são variações com estratégias de crescimento de janela diferentes (slow start, congestion avoidance, fast retransmit, fast recovery etc.).
    - **Slow Start**: Inicia com uma janela pequena, aumentando exponencialmente até atingir um limiar (threshold).
    - **Congestion Avoidance**: Crescimento linear da janela após atingir o threshold.
    - **Fast Retransmit / Fast Recovery**: Possibilita retransmissão rápida ao detectar múltiplos ACKs duplicados, sem aguardar o timeout completo.
8. **SACK (Selective Acknowledgment)**
    
    - O receptor informa **quais blocos** de dados chegaram corretamente, permitindo que o emissor retransmita apenas os segmentos perdidos (e não todo o conjunto).
    - Reduz a quantidade de retransmissão desnecessária.

---

## ~={red}3. User Datagram Protocol (UDP)=~

1. **Sem Conexão e Sem Confiabilidade**
    
    - UDP não faz handshake prévio nem oferece garantias de retransmissão, ordenação ou controle de congestionamento.
    - Menor overhead, ideal para aplicações que precisam de velocidade e podem lidar com eventuais perdas (ex.: streaming de áudio/vídeo ao vivo, DNS).
2. **Cabeçalho UDP**
    
    - Muito simples (8 bytes): contém **Porta de Origem**, **Porta de Destino**, **Tamanho** do datagrama e **Checksum** (opcional para IPv4, obrigatório para IPv6).