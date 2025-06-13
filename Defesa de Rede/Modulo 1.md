Primeiro o analista de cibersegurança deve identificar:
- **Ativos**: qualquer coisa de valor para uma organização que deve ser protegida, como os dados.
- **Vulnerabilidade**: Uma fraqueza em um sistema ou em seu design que pode ser explorada.
- **Ameaças**: qualquer perigo potencial para um ativo.


As organizações precisam identificar onde os ativos de informações essenciais estão armazenados e como o acesso é obtido a essas informações. Os ativos de informação variam, assim como as ameaças contra eles. Por exemplo, uma empresa de varejo pode armazenar informações de cartão de crédito do cliente. Uma empresa de engenharia armazenará projetos e softwares sensíveis à concorrência. Um banco armazenará dados de clientes, informações de conta e outras informações financeiras confidenciais. Cada um desses ativos pode atrair diferentes atores de ameaças que têm diferentes níveis de habilidade e motivações.

### Classificação dos ativos

Uma empresa pode adotar um sistema de rotulagem, de acordo com o valor, a confidencialidade e a importância das informações.

- **Etapa 1**: Determinar a categoria de identificação de ativos adequada
	- Ativos de informações 
	- Ativos de software
	- Ativos físicos
	- Serviços

- **Etapa 2**: Estabeleça a responsabilização, identificando o proprietário de todos os ativos de informações e de softwares de aplicativos
	- Identificar o proprietário de todos os ativos de informações
	- Identificar o proprietário de todo o software de aplicação

- **Etapa 3**: Determinar os critérios de classificação
	- Confidencialidade 
	- Valor 
	- Tempo
	- Direitos de acesso 
	- Destruição

- **Etapa 4**: Implemente um esquema de classificação
	- Adotar uma maneira uniforme de identificação de informações para assegurar a proteção uniforme


Os padrões do ativo identificam produtos de hardware e software específicos usados e suportados pela empresa.

### Estágios do ciclo de vida dos ativos

- **Aquisição**: A empresa compra os ativos de acordo com as necessidades identificadas nos dados coletados para justificar a compra.
- **Implantação**: O ativo é ,montado e inspecionado para verificar se há falhas ou outros problemas. A equipe realiza testes e instala tags ou códigos de barras para fins de rastreamentos.
- **Utilização**: Essa é a fase mais longa do ciclo. O desempenho do ativo é verificado continuamente. Atualizações, correções de patches, compras de novas licenças e auditorias de conformidade fazem parte do estágio de utilização.
- **Manutenção**: A manutenção ajuda a prolongar a vida produtiva de um ativo. Os funcionários podem modificar ou atualizar o recurso.
- **Eliminação**: Ao fim da vida produtiva do ativo, ele deve ser descartado. Todos os dados devem ser apagados do recurso. O descarte pode incluir a desmontagem de um ativo para peças. Quaisquer peças que possam causar riscos ambientais devem ser descartadas de acordo com as diretrizes locais.

### Identifique vulnerabilidades

A identificação de ameaças fornece a uma organização uma lista de prováveis ameaças para um ambiente específico. Ao identificar ameaças, é importante fazer várias perguntas:

- Quais são as possíveis vulnerabilidades de um sistema?
- Quem pode querer explorar essas vulnerabilidades para acessar ativos de informações específicos?
- Quais são as consequências se as vulnerabilidades do sistema forem exploradas e os ativos forem perdidos?

A identificação da ameaça para um sistema de banca electrónica incluiria:

- **Compromisso interno do sistema** - O atacante usa os servidores de e-banking expostos para invadir um sistema bancário interno.
- **Dados roubados do cliente** - Um atacante rouba os dados pessoais e financeiros dos clientes bancários do banco de dados do cliente.
- **Transações falsas de um servidor externo** - Um invasor altera o código do aplicativo de e-banking e faz transações personificando um usuário legítimo.
- **Transações falsas usando um PIN de cliente roubado ou cartão inteligente** - Um invasor rouba a identidade de um cliente e conclui transações mal-intencionadas da conta comprometida.
- **Ataque insider no sistema** - Um funcionário do banco encontra uma falha no sistema a partir do qual montar um ataque.
- **Erros de entrada de dados** - Um usuário insere dados incorretos ou faz solicitações de transação incorretas.
- **Destruição do data center** - Um evento cataclísmico danifica gravemente ou destrói o data center.

Identificar vulnerabilidades em uma rede requer uma compreensão dos aplicativos importantes que são usados, bem como das diferentes vulnerabilidades desse aplicativo e hardware. Isso pode exigir uma quantidade significativa de pesquisa por parte do administrador de rede.

### Identifique as Ameaças

As organizações devem usar uma abordagem de defesa profunda para identificar ameaças e proteger ativos vulneráveis. Essa abordagem usa várias camadas de segurança na borda da rede, na rede e nos pontos de extremidade da rede.

A figura exibe uma topologia simples de uma abordagem de defesa em profundidade:

- **Roteador de borda** - A primeira linha de defesa é conhecida como um roteador de borda (R1 na figura). O roteador de borda tem um conjunto de regras especificando qual tráfego ele permite ou nega. Ele passa todas as conexões que se destinam à LAN interna para o firewall.
- **Firewall** - A segunda linha de defesa é o firewall. O firewall é um dispositivo de ponto de verificação que executa filtragem adicional e rastreia o estado das conexões. Ele nega o início de conexões de redes externas (não confiáveis) para a rede interna (confiável), enquanto permite que usuários internos estabeleçam conexões bidirecionais com as redes não confiáveis. Ele também pode executar autenticação de usuário (proxy de autenticação) para conceder aos usuários remotos externos acesso a recursos de rede interna.
- **Roteador interno** - Outra linha de defesa é o roteador interno (R2 na figura). Ele pode aplicar regras de filtragem finais no tráfego antes de ser encaminhado para seu destino.


### A Cebola Alcachofra da segurança

- Cebola de segurança
	- Uma analogia comum usada para descrever uma abordagem de defesa em profundidade é chamada de “cebola de segurança”. Como ilustrado na figura, um ator de ameaça teria que descascar as defesas de uma rede camada por camada de uma maneira semelhante a descascar uma cebola. Somente depois de penetrar cada camada, o ator da ameaça alcançaria os dados ou o sistema de destino.
	![[Pasted image 20250317173557.png]]

- Alcachofra de segurança
	- O cenário em mudança da rede, como a evolução das redes sem fronteiras, mudou essa analogia para a “alcachofra de segurança”, que beneficia o ator de ameaça.

	 Conforme ilustrado na figura, os atores da ameaça não precisam mais descascar cada camada. Eles só precisam remover certas “folhas de alcachofra”. O bônus é que cada “folha” da rede pode revelar dados confidenciais que não estão bem protegidos.

	 Por exemplo, é mais fácil para um agente de ameaça comprometer um dispositivo móvel do que comprometer um computador ou servidor interno protegido por camadas de defesa. Cada dispositivo móvel é uma folha. E folha após folha, tudo leva o hacker a mais dados. O coração da alcachofra é onde os dados mais confidenciais são encontrados. Cada folha fornece uma camada de proteção enquanto fornece simultaneamente um caminho para o ataque.

	 Nem todas as folhas precisam ser removidas para chegar ao coração da alcachofra. O hacker arranca a armadura de segurança ao longo do perímetro para chegar ao “coração” da empresa.
	![[Pasted image 20250317173844.png]]

### Estratégias de Defesa em Profundidade

- **Sobreposição**: Uma abordagem em camadas oferece a proteção mais abrangente porque, mesmo que os criminosos cibernéticos penetrem em uma camada, eles ainda precisam enfrentar várias outras defesas. Idealmente, cada camada deve ser mais complicada de superar!
  A defesa em profundidade não fornecerá um escudo cibernético impenetrável, mas ajudará a empresa a minimizar riscos, mantendo-se um passo à frente dos criminosos virtuais.
- **Limitação**: Limitar o acesso aos dados e às informações reduz a possibilidade de uma ameaça. Uma empresa deve restringir o acesso para que os usuários tenham apenas o nível de acesso necessário para fazer o seu trabalho.
- **Diversidade**: As camadas devem ser diferentes para que, se uma camada for penetrada, a mesma técnica não funcionará em todas as outras, o que comprometeria todo o sistema. Uma empresa pode usar diferentes algoritmos de criptografia ou sistemas de autenticação para proteger os dados em diferentes estados.
- **Ofuscação**: Uma empresa não deve revelar informações que os criminosos virtuais podem usar para descobrir a versão do sistema operacional em execução em um servidor ou o tipo de equipamento que ele usa. Ocultar certos tipos de informação dificulta ataques de criminosos virtuais a um sistema.
- **Simplicidade**: Se os funcionários não entenderem como configurar uma solução complexa corretamente, pode ser tão fácil quando em uma solução mais simples para os criminosos virtuais comprometerem esses sistemas. Para manter a disponibilidade, uma solução de segurança deve ser simples, do ponto de vista de dentro da empresa, mas complexa do ponto de vista externo.


## Gerenciamento de configurações

Por exemplo, os responsáveis pela implantação de estações de trabalho do Windows para usuários devem instalar os aplicativos necessários e definir as configurações do sistema de acordo com uma configuração documentada. Essa é a configuração de linha de base para as estações de trabalho Windows nessa empresa.

- Os recursos de configuração documentados podem incluir o seguinte:
	- Mapas de rede, diagramas de cabeamento e rede, especificações de configuração da aplicação
	- Convenções de nomenclatura padrão usadas para computadores
	- Esquema IP para rastrear endereços IP

- O reforço do sistema operacional é uma parte importante para garantir que os sistemas tenham configurações seguras. A configuração de arquivos de log junto com a auditoria, a alteração de nomes de conta e senhas e a implementação de políticas de conta e controle de acesso no nível de arquivo são usados para criar um sistema operacional seguro.


## Arquivos de log
Um log registra todos os eventos que ocorrem. Entradas de log compõem um arquivo de log e uma entrada de log contém todas as informações relacionadas a um evento específico. Registros precisos e completos são muito importantes na segurança digital.

Por exemplo, um log de auditoria rastreia as tentativas de autenticação do usuário e um log de acesso fornece todos os detalhes sobre as solicitações para arquivos específicos de um sistema. O monitoramento dos logs do sistema pode determinar como um ataque ocorreu e se as defesas implantadas foram bem-sucedidas.

Com o aumento do número de arquivos de log gerados para fins de segurança do computador, a empresa deve considerar um processo de gerenciamento de logs. O gerenciamento de dados do log de segurança do computador deve determinar os procedimentos para o seguinte:

- Gerando arquivos de log
- Transmissão de arquivos de log
- Armazenamento de arquivos de log
- Análise de dados
- Descartando dados de log


## Registros do sistema operacional e registros de segurança do aplicativo

- Logs do sistema operacional
	 O sistema operacional registra eventos de registro que estão vinculados a ações relacionadas ao sistema operacional. Eventos do sistema incluem o seguinte:
	- Solicitações do cliente e respostas do servidor, como autenticações de usuário bem-sucedidas
	- Informações de uso que contêm o número e o tamanho das transações em um determinado período de tempo

- Segurança de aplicaçoes
	- As empresas usam software de segurança pela rede ou pelo sistema para detectar atividade mal-intencionada. Esse software gera um log de segurança para fornecer dados de segurança do computador. Os logs são úteis para a realização de análise de auditoria e para a identificação de tendências e de problemas no longo prazo. Os logs também permitem que uma empresa forneça documentação que mostre que está em conformidade com as leis e os requisitos regulatórios.


## Analisadores de protocolo
Os packet analyzers (ou analisadores de pacotes) interceptam e registram o tráfego de rede.

O packet analyzer captura cada pacote, mostra os valores de vários campos no pacote e analisa o conteúdo. Um sniffer pode capturar o tráfego em redes com e sem fio.

Packet analyzers executam as seguintes funções:

- Log de tráfego
- Análise de problemas de rede
- Detecção de uso indevido da rede
- Detecção de tentativas de invasão da rede
- Isolamento do sistema explorado



## Políticas de Negócios
![[Pasted image 20250317175727.png]]

## Política de Segurança
![[Pasted image 20250317180057.png]]


## Políticas de BYOD

![[Pasted image 20250317180437.png]]
![[Pasted image 20250317180445.png]]
