O modelo OSI (Open Systems Interconnection) é um modelo conceitual que padroniza a comunicação entre sistemas de redes. Ele é dividido em ~={red}**sete camadas**=~, cada uma com funções específicas:

| Camada 1 | Física          |
| -------- | --------------- |
| Camada 2 | Enlace de dados |
| Camada 3 | Rede            |
| Camada 4 | Transporte      |
| Camada 5 | Sessão          |
| Camada 6 | Apresentação    |
| Camada 7 | Aplicação       |

- 1- ~={blue}**Física**=~ – Transmissão de ~={green}Bits=~ brutos pelo meio físico onde há questões elétricas e mecânicas.
- 2- ~={blue}**Enlace de Dados**=~ – Identificar o inicio e o fim de ~={green}Quadros=~ dentre os bits para obter os dados e controle de erro.
- 3- ~={blue}**Rede** =~– Responsável pelo encaminhamento de ~={green}Pacotes=~ da origem ao destino.
- 4- ~={blue}**Transporte** =~– Dividir a mensagem inteira em ~={green}Segmentos=~ para que seja entregue até o destino final.
- 5- ~={blue}**Sessão**=~ – Gerenciamento de diálogo do sistema de comunicação entre os dispositivos finais.
- 6- **~={blue}Apresentação=~** – Tradução, criptografia e compressão de dados.
- 7- **~={blue}Aplicação=~** – Interface direta com o usuário (ex.: HTTP, FTP, SMTP).

###  Dispositivos intermediários

• ~={orange}**Repetidor/Hub**=~: recebe sinais/bits da camada física e os regera

• ~={orange}**Switch e Bridge**=~: atua no quadro/frame da tecnologia da camada
de enlace, geralmente faz análise de erros (ex: CRC), transmite na
interface de saída onde está o endereço físico de destino
– OBS: pode reestruturar o quadro dependendo da tecnologia (Bridges), ou
recalcular FCS/CRC ao inserir mais cabeçalhos (vlan)
– Pode atuar com funcionalidades de roteador (switch layer 3)

• **~={orange}Roteador=~**: atua no pacote IP, faz o encaminhamento com base no
endereço IP de destino. Decrementa o TTL (IPv4) ou HopLimit
(IPv6), análise de erros cabeçalho IPv4
– Podem agregar serviços extras: Firewall, NAT, QoS, VPN,...

• **~={orange}Access-Point**=~: (roteador sem fio): atuam como Bridge e/ou
Roteado


