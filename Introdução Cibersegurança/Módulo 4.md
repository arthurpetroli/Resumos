### ~={red}Dispositivos de Tecnologias de segurança cibernética=~

#### ~={green}Dispositivos de segurança=~
- **Roteadores**: Principalmente utilizados para interconectar segmentos de redes, porém também oferecem filtragem de tráfego.
- **Firewalls**: Analisam o tráfego de rede e identificam comportamentos mal-intencionados.
- **Sistema de prevenção de invasão**: IPS usam conjunto de assinaturas de tráfego que bloqueiam tráfego e ataques mal-intencionados.
- **VPN**: Permite usar túnel criptografado segura em computadores móveis e se conectam com segurança.
- **Antivírus e Antimalware**: Usam assinaturas ou análises comportamentais das aplicações para identificar e bloquear a execução de códigos mal-intencionados.


#### ~={green}Firewalls=~
Em redes de computadores, um firewall é projetado para controlar ou filtrar quais comunicações são permitidas dentro e quais são permitidas fora de um dispositivo ou rede.
- **Firewall de camada de rede**: Filtra comunicação com base no IP origem e destino.
- **Firewall da camada de transporte**: Filtra comunicação com base nas portas de dados de origem e destino.
- **Firewall da camada de aplicação**: Filtra comunicação de acordo com um aplicativo.
- **Firewall sensível ao contexto**: Filtra comunicação com base no usuário, dispositivo, função, tipo de aplicativo e perfil de ameaça.
- **Servidor proxy**: Filtra solicitações de conteúdo da web.
- **Servidor proxy reverso**: Protegem, ocultam, descarregam e distribuem o acesso aos servidores web.
- **Network address translation(Nat) firewall**: Oculta ou marcara os endereços privados dos hosts da rede.
- **Firewall baseado em host**: Filtra portas e chamadas de serviço do sistema.


#### ~={green}Varredura de portas=~
Na rede, cada aplicativo em execução em um dispositivo recebe um identificador ou número de porta. Esse número da porta é usado em ambas as extremidades da transmissão para que os dados certos sejam passados ao aplicativo correto. A varredura de portas é um processo de sondar um computador, servidor ou outro host de rede em busca de portas abertas. Ele pode ser usado maliciosamente como uma ferramenta de reconhecimento para identificar o sistema operacional e os serviços em execução em um computador ou host, ou pode ser usado sem causar danos por um administrador de rede para verificar as políticas de segurança da rede.


#### ~={green}Sistemas de detecção e prevenção de intrusos=~
Sistemas de detecção de intrusão (IDSs) e sistemas de prevenção de intrusão (IPSs) são medidas de segurança implantadas em uma rede para detectar e prevenir atividades maliciosas.

- **IDS**: Um IDS pode ser um dispositivo de rede dedicado ou uma das várias ferramentas em um servidor, firewall ou até mesmo um sistema operacional de computador host, como Windows ou Linux, que faz a varredura de dados em um banco de dados de regras ou assinaturas de ataque, em busca de tráfego malicioso. 
  Se uma correspondência for detectada, o IDS registrará a detecção de registro e criará um alerta para um administrador de rede. Ele não tomará nenhuma ação e, portanto, não impedirá que os ataques aconteçam. O trabalho do IDS é detectar, registrar e relatar.

- **IPS**: Um IPS pode bloquear ou negar tráfego com base em uma regra positiva ou correspondência de assinatura. Um dos sistemas mais conhecidos de IPS/IDS é o Snort. A versão comercial do Snort é o Sourcefire da Cisco. A Sourcefire pode realizar análise de tráfego e porta em tempo real, registro, pesquisa e correspondência de conteúdo, bem como detectar sondas, ataques e executar varreduras de porta.


#### ~={green}Detecção em tempo real=~
A detecção de ataques em tempo real requer a verificação ativa de ataques usando firewall e dispositivos de rede IDS/IPS. A detecção de malware de cliente e servidor de próxima geração com conexões a centros de ameaças globais online também deve ser usada.
DDoS é uma das maiores ameaças de ataque que requer detecção e resposta em tempo real. Para muitas organizações, ataques DDoS que ocorrem regularmente prejudicam os servidores da Internet e a disponibilidade da rede.


#### ~={green}Proteção contra Malware=~
AMP é um software cliente/servidor que pode ser implantado em host endpoints, como um servidor autônomo ou em outros dispositivos de segurança de rede. Ele analisa milhões de arquivos e os correlaciona com centenas de milhões de outros artefatos de malware analisados para comportamentos que revelam um APT. Isso proporciona uma visão geral de ataques, de campanhas e de distribuição de malware.
- **Equipe de SOC**: Coleta dados mais precisos e úteis.
- **Equipe de resposta a incidentes**: Tem acesso a informações forenses confiáveis que permite analisar e entender comportamentos suspeitos com mais rapidez.
- **Equipe de inteligência de ameaças**: Melhora proativamente a infraestrutura de segurança da empresa.
- **Equipe de engenharia da infraestrutura de segurança**: Capaz de consumir e agir com base nas informações de ameaças com mais rapidez.

#### ~={green}Práticas recomendadas de segurança=~
- Executar avaliação de risco
- Criar uma politica de segurança
- Medidas de segurança física
- Medidas de segurança para recursos humanos 
- Realizar e testar backups 
- Manter patchs e atualizações de segurança
- Empregar controles de acesso
- Teste regularmente a resposta a incidentes
- Implementar uma ferramenta de monitoramento, análise e gerenciamento de rede
- Implementar dispositivos de segurança de rede
- Implementar uma solução de segurança de endpoints abrangente
- Educar os usuários
- Criptografar dados

---

### ~={red}Abordagem comportamental a segurança cibernética=~

#### ~={green}Segurança baseada em comportamento=~
A segurança baseada em comportamento é uma forma de detecção de ameaças que envolve a captura e análise do fluxo de comunicação entre um usuário na rede local e um destino local ou remoto. Quaisquer alterações nos padrões normais de comportamento são consideradas anomalias e podem indicar um ataque.
- **Honeypots**: Um honeypot é uma ferramenta de detecção baseada em comportamento que atrai o invasor apelando para seu padrão previsto de comportamento malicioso. Quando o invasor estiver dentro do honeypot, o administrador de rede poderá capturar, registrar e analisar o comportamento dele para que possa construir uma defesa melhor.

- **Arquitetura da Solução Cisco Cyber Threat Defense**: Esta arquitetura de segurança usa detecção e indicadores baseados em comportamento para fornecer maior visibilidade, contexto e controle. O objetivo é saber quem está realizando o ataque, que tipo de ataque ele está realizando e onde, quando e como o ataque está ocorrendo. Essa arquitetura de segurança usa muitas tecnologias de segurança para atingir esse objetivo.

#### ~={green}NetFlow=~
A tecnologia NetFlow é usada para coletar informações sobre os dados que fluem através de uma rede, incluindo quem e quais dispositivos estão na rede, e quando e como os usuários e dispositivos acessam a rede.

O NetFlow é um componente importante na análise e detecção baseada em comportamento. Switches, roteadores e firewalls equipados com NetFlow podem relatar informações sobre a entrada, saída e passagem de dados pela rede.


#### ~={green}Teste de penetração=~
Conhecido como pen testing, é o ato de avaliar um sistema de computador, uma rede ou uma empresa em busca de vulnerabilidades de segurança. Um pen test procura violar sistemas, pessoas, processos e códigos para descobrir vulnerabilidades que podem ser exploradas.

- Planejamento: O pen tester coleta o máximo de informações possível sobre um sistema ou rede de destino, suas vulnerabilidades e exploits potenciais para usar contra ele.
- Varredura: O pen tester realiza o reconhecimento ativo para investigar um sistema ou rede de destino e identificar possíveis pontos fracos que, se explorados, podem dar acesso ao invasor
	- Varredura de porta para identificar possíveis pontos de acesso em um sistema de destino
	- verificação de vulnerabilidades para identificar possíveis vulnerabilidades exploráveis de um determinado alvo
	- estabelecer uma conexão ativa com um destino (enumeração) para identificar a conta de usuário, de sistema e de administrador.

- Obter acesso: O pen tester tentará obter acesso a um sistema de destino e detectar o tráfego de rede, usando vários métodos para explorar o sistema.
	-  lançar um exploit com um payload no sistema
	- violar barreiras físicas a ativos
	- engenharia social
	- explorando vulnerabilidades de sites
	- explorando vulnerabilidades ou configurações incorretas de software e hardware
	- violar a segurança dos controles de acesso
	- quebrar Wi-Fi com criptografia fraca.

- Manter acesso: O pen tester manterá o acesso ao alvo para descobrir quais dados e sistemas estão vulneráveis à exploração. É importante que não sejam detectados, normalmente usando backdoors, cavalos de Troia, rootkits e outros canais encobertos para ocultar sua presença.

- Análise e geração de relatórios: O pen tester fornecerá feedback por meio de um relatório que recomenda atualizações de produtos, políticas e treinamento para melhorar a segurança de uma empresa.

#### ~={green}Redução do impacto=~
Embora a maioria das empresas hoje esteja ciente das ameaças de segurança comuns e se esforce consideravelmente para evitá-las, nenhum conjunto de práticas de segurança é infalível.
- Comunicar o problema
- Ser sincero e responsável
- Forneça os detalhes
- Encontre a causa
- Aplicar lições aprendidas
- Verificar e verificar novamente
- Eduque

#### ~={green}O que é gerenciamento de risco?=~
O gerenciamento de riscos é o processo formal de identificação e avaliação contínuas dos riscos para reduzir o impacto das ameaças e vulnerabilidades. Você não pode eliminar completamente o risco, mas pode determinar níveis aceitáveis ponderando o impacto de uma ameaça com o custo de implementação de controles para mitigá-la. O custo de um controle nunca deve ser maior que o valor do ativo que você está protegendo.
- Defina o risco
- Classifique o Risco
- Responda ao risco
- Monitore o risco


#### ~={green}Cartilha de segurança=~
Uma das melhores maneiras de se preparar para uma violação de segurança é evitá-la. As empresas devem fornecer orientação sobre:
- como identificar os riscos de segurança digital para sistemas, ativos, dados e recursos
- a implementação de proteções e treinamento de pessoal
- um plano de resposta flexível que minimiza o impacto e os danos em caso de violação de segurança
- as medidas e os processos de segurança que precisam ser implementados após uma violação de segurança.

#### ~={green}Ferramentas para prevenção e detecção de incidentes=~
Um sistema Security Information and Event Management (SIEM) coleta e analisa alertas de segurança, logs e outros dados históricos e em tempo real de dispositivos de segurança na rede para facilitar a detecção precoce de ataques cibernéticos.

Um sistema de Data Loss Prevention (DLP) é projetado para impedir que dados confidenciais sejam roubados ou escapem de uma rede. Ele monitora e protege os dados em três estados diferentes: dados em uso (dados sendo acessados por um usuário), dados em movimento (dados que viajam pela rede) e dados inativos (dados armazenados em uma rede ou dispositivo de computador).


## ~={orange}Módulo 5=~
![[Pasted image 20250307170718.png]]![[Pasted image 20250307170927.png]]