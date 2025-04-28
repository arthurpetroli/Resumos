# ~={red}Aula1=~
**Sistemas Distribuídos**: São uma rede de computadores que se comunicam através de mensagens e é apresentado como um sistema único aos usuários. Eles fazem uso de middlewares para manter o sistema homogêneo, ou seja, independente do dispositivo que o host acessar ou como é feita a comunicação, o sistema será o mesmo. O processamento das tarefas é dividido entre vários hosts dando a impressão de um sistema único.
1. Não possuem relógio físico para sincronização dos processos.
2. Não possuem memoria compartilhada.
3. São heterogêneos (computadores heterogêneos mas sistemas em si homogêneo) e autônomo.

Propriedades:
1. Escaláveis.
2. Portabilidade (executar em diferentes aparelhos).
3. Interoperabilidade (se comunica com diferentes distribuidores).
4. Heterogeneidade (software e hardware distintos).
5. Transparentes (ocultamento dos detalhes de comunicação, tanto em onde esta o serviço quanto como é feito).

Middlewares: camada de software entre SO e as aplicações responsável por realizar comunicação entre hosts de forma transparente pois oculta detalhes do SO e da rede.

-----------------------
# ~={red}Aula2=~
IPC (Interprocess Communication) processos se comunicam através de canais
Exemplos:
1. Pipes: permite comunicação entre processos pai e filho (mesmo host) através de um canal **unidirecional**.
2. Filas de mensagens: processos enviam mensagens para a fila e demais processos leem e processam elas.
3. Memória compartilhada: diferentes processos acessam a mesma área de memória permitindo troca de informações rápida porém exige mais cuidados para manter consistência e integridade dos dados.
4. Sockets: utilizam protocolos de rede (TCP ou UDP) para transmitir as mensagens, eles são um canal de comunicação **bidirecional** e é identificado com uma porta (>1024).
5. Sinais: interrupções de software enviadas a um processo indicando que um evento ocorreu, o processo interrompe sua execução e processa o sinal, ela ocorre de forma **assíncrona e unidirecional**.

-------------------------
# ~={red}Aula3=~
Computação Paralela: O processador executa varias tarefas ao mesmo tempo, essas tarefas são divididas em partes, processadas separadamente e depois os resultados juntados. Esses sistemas utilizam **memória compartilhada.** Exemplo: Grids e Clusters.

Computação concorrente: tarefas executadas em sistemas com processadores com um núcleo onde eles simulam paralelismo, uma parte da tarefa é executada no processador e depois em outro tempo de clock a outra parte é processada.

Taxonomia de Flynn
	- Arquitetura SISD (Single Instruction Single Data): Executa uma instrução por vez para cada dado enviado, pode ser comp concorrente. Ex: Arduino.
	- Arquitetura SIMD (Single Instruction Multiple Data): Utiliza paralelismo, instrução é executada enquanto um programa é executado paralelamente e com dados síncronos, cada processador executa uma mesma instrução. Ex: Processadores atuais.
	- Arquitetura MIMD (Multiple Instruction Single Data): Execução paralela, cada processador executa uma instrução independente como se fossem um SIMD e com dados diferentes. Ex: Sistemas distribuídos, Clusters e Servidores.
	- Arquitetura MISD (Multiple Instruction Single Data): Execução paralela, executa múltiplas instruções ao mesmo tempo com um único dado.

-------------------
# ~={red}Aula4=~
**Processos**: são instancias de programas sendo executados por uma ou mais threads.
	- Execução sequencial: processo esta em execução.
	- Execução concorrente: processo executa com outro processo um de cada vez.
	- Execução paralela: processo executa junto com outro processo mas sem interrupção.

**Threads**: são instancia de um processo/programa em execução, um programa pode ter uma ou varias threads, elas pertencem a um processo e compartilham seus recursos.
Threads compartilham a mesma heap de um processo (memória dinâmica global do processo: variáveis locais, argumentos e retornos). As threads também possuem um contador próprio (PC)
permitindo que sua execução seja independente das demais threads.
Ciclo de vida de uma Thread:
1. Novo: thread foi criada mas não startada (:.
2. Pronto/Executável: thread foi inicializada e está executando.
3. Espera: estado que uma thread fica quando outra está executando (wait), ela só volta a executar quando a outra thread envia uma notificação alertando que pode voltar ao estado executável.
4. Espera sincronizada: thread entra em espera (sleep) por um tempo determinado.
5. Bloqueada: thread entra neste estado quando uma tarefa não pode ser executada ainda ou está aguardando dados (E/S).

Em um SO, é mais fácil criar e lidar com varias threads em um processo do que criar um processo. As threads são utilizadas para controlar os recursos compartilhados de um processo (execução concorrente), isso dispensa o uso de IPCs para compartilhamento de dados.

------------------
# ~={red}Aula5=~
Arquitetura Cliente/Servidor: cliente envia request ao servidor que responde a estes requests, o servidor também pode fazer requests e o cliente responder. Arquitetura centralizada com servidor provendo os serviços e pouco escalável.

Arquitetura Peer-To-Peer: todos os agentes da rede atuam como cliente e como servidores, ora provendo serviços ou requisitando. Arquitetura descentralizada e muito escalável.

Arquitetura em camadas:
	- 2-Camadas: tanto servidor quanto cliente ficam com a logica da aplicação (Control) para reduzir a latência das requisições, apesar disso ser uma desvantagem, ele agrupa a logica MVC tanto para cliente quanto para servidor.
	- 3-Camadas: distribui a logica MVC, logica da aplicação (Control) e armazenagem (Model) ficam no servidor para distribuir melhor a carga na camada interna do serviço, assim o cliente só fica com a View, permitindo que o Control seja modificado sem interromper os serviços dos clientes.

------

# ~={red}Aula6=~
DTH (Hash Table Distribuída): Pares (chaves, valor) com predecessor e sucessor (fila circular).
	- DTH normal: O(N)
	- DTH com atalhos: Alem do predecessor e do sucessor, os pares guardam atalhos. O(logN)

------

# ~={red}Aula7=~
Protocolo TCP: possui handshake o que gerente conexão e entrega dos pacotes de forma ordenada, controle de fluxo e sem perda dos pacotes.

Protocolo UDP: não possui handshake e não garante entrega dos datagramas o que pode gerar perda e eles não são ordenados, sem controle de fluxo e envio/recebimento individual dos datagramas.

Socket: canal de comunicação bidirecional do IPC entre mesmos hosts ou diferentes
  - Socket Unicast: comunicação ponto a ponto pelo TCP/UDP.
  - Socket Multicast: comunicação entre vários hosts com mesmo IP pelo UDP.

Sockets no protocolo UDP funcionam um pouco diferente, como ele não possui handshake o endereço IP de destino é colocado nos datagramas e enviados(pipes). O cliente quando cria o datagrama especifica nele o IP e a Porta de destino, o mesmo é extraído no servidor (datagrama de origem) e enviado novamente com os dados de origem extraídos. Dentro do código o cliente não insere o IP e a Porta manualmente, eles são inseridos de forma transparente pelo próprio datagrama.

Serviços é um grupo que acessa recursos e recursos podem ser quaisquer tipos.

------

# ~={red}Aula8=~
Sistemas Distribuídos devem ser tolerantes a falhas e permanecer operantes quando falhas parciais ocorrem. Eles devem seguir:
 - Confiabilidade: propriedade na qual o sistema permanece funcionando por um longo período de tempo sem apresentar falhas, ela é medida pelo intervalo de tempo que ele fica sem falhas.
 - Disponibilidade: tempo medido que o sistema se mantem operacional.
 - Segurança de uso (safety): garante que os dados estejam seguros em caso de falha, leitura(usuários comuns) ACID.
 - Segurança de acesso (security): garante que o acesso aos dados esteja restrito (seguro), apenas usuários cadastrados podem acessar e alterar as informações.
 - Capacidade de manutenção: é a possibilidade de manutenção do sistema sem que ele seja interrompido.

Padrão de falhas:
 - Falta/Defeito(fault): é um bug interno e estático no serviço, geralmente um erro no código(software) ou erro físico(hardware).
 - Erro(error): é a diferença da saída esperada e da obtida, ocorre durante a execução do defeito e dinâmico.
 - Falha(failure): quando o sistema não cumpre sua função esperada, é um comportamento externo e obtido no resultado final.

Tipos de Falhas:
 - Falha por queda: serviço é interrompido de forma inesperada tornando o acesso indisponível.
 - Falha de omissão: servidor não recebe mensagens corretamente ou falha ao enviar respostas.
 - Falha de temporização: servidor responde muito rápido ou demora muito para responder.
 - Falha de desempenho: demora no processamento da mensagem e no envio da resposta.
 - Falha de resposta: A resposta enviada pelo servidor está incorreta, podendo ser o valor da resposta em si ou o serviço solicitado pela mensagem não é reconhecido e uma outra ação é tomada.
 - Falha arbitraria/Bizantinas: pior tipo de falha e que não pode ser detectada sua causa, pode gerar saídas inesperadas ou comunicação insegura.
 - Falhas seguras: O proprio servidor anuncia um erro e entra em estado inoperante.

Redundância: técnica usada para mascarar uma falha do sistema (reaplicação de um servico). Exemplo: RAID(Redundant Array of Independent Disks)
 - Redundância de informação: uma informação extra é adicionada aos dados transmitidos para garantir sua entrega ou que os erros possam ser corrigidos.
 - Redundância de tempo: ação é realizada novamente caso uma falta ocorra.
 - Redundância física: a falha de outros componentes é compensada pela adição de outros que assumem o papel do anterior.

Modelos de Segurança:
 - Autenticação: Controle de quem acessa os dados. Usuários passam por uma autenticação para provarem quem eles são.
 - Autorização: Define quais recursos/operações os usuários são permitidos acessar(permissão de acesso).
 - Registro: Registro das operações realizadas/acessadas pelos usuários (Logs).

Segurança compartilhada:
- Parte provedor assegura.
- Disponibilidade
- Confiabilidade
- Tratamento de falhas
- Parte usuário deve realizar
- Controle de acesso
- Manutenção de senhas
- Credenciais: usuário e senha
- Certificado digital(CA)
- Assinatura virtual

Ciclo de vida circular identificando as falhas do sistema:
- Planejamento: definir as falhas que você ira monitorar.
- Fazer: implementar tratamento com base no que planejou.
- Verificar: verificar constantemente se o serviço esta rodando.
- Agir: caso aconteça uma falha sempre fazer uma manutenção.