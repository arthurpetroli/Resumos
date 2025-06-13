### ~={red}Analisando um ataque cibernético=~
#### ~={green}Tipos de Malware=~
Abreviação de “Malicious Software” (software mal-intencionado), o malware é qualquer código que pode ser usado para roubar dados, ignorar controles de acesso, causar danos  ou comprometer um sistema.

Tipos: 
- **Spyware**
    
    - O spyware monitora sua atividade on-line e pode registrar todas as teclas que você pressiona no teclado, bem como capturar quase todos os dados, incluindo informações pessoais confidenciais, como detalhes bancários online.

 - **Adware**
	 - É projetado para fornecer anúncios automaticamente a um usuário, na maioria das vezes em um navegador da Web.

- Backdoor
	- É usado para obter acesso não autorizado, ignorando os procedimentos normais de autenticação para acessar um sistema.

-  Ameaças de
	- Malware projetado para manter um sistema de computador, ou os dados incluídos nele, presos até que o pagamento seja feito. O ransomware geralmente funciona criptografando os dados para que você não possa acessá-los.

- Scareware
	- Usa táticas de "medo" para induzi-lo a tomar uma ação específica. O Scareware consiste principalmente em janelas com estilo de sistema operacional que aparecem para alertar que seu sistema está em risco e precisa executar um programa específico para que ele retorne à operação normal.

- Rootkit
	- Projetado para modificar o sistema operacional para criar um backdoor, que os invasores podem usar para acessar seu computador remotamente. A maioria dos rootkits utiliza as vulnerabilidades do software para escalonar privilégios e modificar arquivos de sistema.

- Vírus
	- Tipo de programa de computador que, quando executado, se replica e se anexa a outros arquivos executáveis, como um documento, ao inserir seu próprio código. A maioria dos vírus necessita de ativação do usuário final e pode ser ativada em uma hora ou data específica.

- Cavalo de troia
	- Realiza operações mal-intencionadas mascarando sua verdadeira intenção. Pode parecer legítimo, mas é, de fato, muito perigoso. Os cavalos de troia exploram os privilégios de usuário e são encontrados com mais frequência em arquivos de imagem, arquivos de áudio ou jogos.

- Worms
	- Malware que se replica para se espalhar de um computador para outro. Ao contrário de um vírus, que requer um programa host para ser executado, os worms podem ser executados por si próprios. Além da infecção inicial do host, eles não exigem a participação do usuário e podem se espalhar rapidamente pela rede.
	- Eles exploram vulnerabilidades do sistema, têm uma maneira de se propagar e contêm código mal-intencionado (payload) para causar danos a redes ou sistemas de computador.

Independente do tipo de malware com o qual um sistema foi infectado, existem alguns sintomas comuns a serem observados. Entre eles estão:

- Um aumento no uso da unidade de processamento central (CPU), o que torna o dispositivo mais lento
- O computador congela ou trava frequentemente
- Há uma diminuição na velocidade de navegação na Web.
- Existem problemas inexplicáveis com conexões de rede.
- Arquivos modificados ou excluídos
- Há presença de arquivos, programas ou ícones de desktop desconhecidos.
- Processos ou serviços desconhecidos em execução
- Programas estão se desligando ou reconfigurando sozinhos.
- E-mails estão sendo enviados sem o conhecimento ou consentimento do usuário.

---

### ~={red}Métodos de infiltração=~

#### ~={green}Engenharia social=~
Manipulação do indivíduo para executar ações ou divulgar informações confidenciais. Os engenheiros sociais frequentemente dependem da boa vontade das pessoas para ajuda, mas também miram nos pontos fracos.
- **Pretexting**: Invasor liga para um indivíduo e mente para ele na tentativa de obter acesso a dados privilegiados.
- **Tailgating**: Invasor segue rapidamente uma pessoa autorizada até um local físico seguro.
- **Algo por algo (Quid pro quo)**: Hacker solicita informações pessoais de uma pessoa em troca de algo, como um brinde gratuito.

#### ~={green}Negação de Serviço=~
São um tipo de ataque de rede que é relativamente simples de realizar, mesmo por um invasor não qualificado. Um ataque de negação de serviço (DoS) resulta em algum tipo de interrupção de serviço aos usuários, dispositivos ou aplicações.
- **Quantidade Esmagadora de Tráfego**: Quando uma rede, host ou aplicativo recebe uma enorme quantidade de dados a uma taxa que não consegue processar. Isso causa uma desaceleração na transmissão ou resposta ou uma falha em um dispositivo ou serviço.
- **Pacotes Maliciosamente Formatados**: Quando um pacote formatado de forma mal-intencionada é enviado, o receptor não será capaz de tratá-lo.

#### ~={green}DoS Distribuída=~
Um ataque de negação de serviço distribuída (DDoS) é semelhante a um  ataque de negação de serviço (DoS), mas é proveniente de várias fontes coordenadas.
- Um invasor cria uma rede (botnet) de hosts infectados chamados zumbis, que são controlados por sistemas de tratamento.
- Os computadores zumbis examinam e infectam constantemente mais hosts, criando mais zumbis.
- Quando está pronto, o hacker instrui os sistemas controlador para fazer com que o botnet de zumbis execute um ataque de negação de serviço distribuído (DDoS).

#### ~={green}Botnet=~
Um computador bot normalmente é infectado por visitar um site, abrir um anexo de e-mail ou abrir um arquivo de mídia infectado. Uma botnet é um grupo de robôs (bots), conectados pela Internet, com a capacidade de ser controlado por um indivíduo ou grupo mal-intencionado. Ela pode ter dezenas de milhares, ou até centenas de milhares, de bots que normalmente são controlados por meio de um servidor de comando e controle.

Esses robôs podem ser ativados para distribuir malware, lançar ataques de DDoS, distribuir e-mail de spam ou executar ataques de senha de força bruta. Os cibercriminosos freqüentemente alugam botnets para terceiros para fins nefastos.

#### ~={green}Ataques On-Path=~
Os invasores no caminho interceptam ou modificam as comunicações entre dois dispositivos, como um navegador e um servidor da Web, para coletar informações ou se passar por um dos dispositivos.
- **MitM**: Um ataque de MitM acontece quando um criminoso digital assume o controle de um dispositivo sem o conhecimento do usuário. Com esse nível de acesso, o invasor pode interceptar e capturar informações do usuário antes de transmiti-las ao seu destino desejado.
- **MitMo**: Uma variação do man-in-middle, MitMo é um tipo de ataque usado para assumir o controle do dispositivo móvel de um usuário. Quando infectado, o dispositivo móvel é instruído a capturar informações confidenciais do usuário e enviá-las aos invasores.

#### ~={green}SEO Poisoning=~
O SEO visa melhorar o site de uma empresa para que obtenha maior visibilidade nos resultados dos mecanismos de pesquisa.
Mecanismos de pesquisa como o Google funcionam apresentando uma lista de páginas da Web para usuários com base em suas consultas de pesquisa. Essas páginas da Web são classificadas de acordo com a relevância de seu conteúdo.
Embora muitas empresas legítimas se especializem em otimizar sites para melhor posicioná-los, os invasores tiram proveito de termos de pesquisa populares e usam o SEO para empurrar sites maliciosos para posições mais altas nos resultados de pesquisa. Esta técnica é chamada de envenenamento de SEO.
O objetivo mais comum do envenenamento de SEO é aumentar o tráfego para sites maliciosos que podem hospedar malware ou tentar engenharia social.

#### ~={green}Ataques de senha=~
- **Password spraying**: Técnica que tenta obter acesso a um sistema ao “pulverizar” algumas senhas usadas com frequência em um grande número de contas.

- **Ataque de dicionário**: Um hacker tenta sistematicamente cada palavra de um dicionário ou uma lista de palavras usadas com frequência como senha, na tentativa de invadir uma conta protegida por senha.

- **Ataques de força bruta**: Os ataques de força bruta veem um invasor usando todas as combinações possíveis de letras, números e símbolos no espaço de senha até acertar.

- **Ataque do arco-íris**: As senhas em um sistema de computador não são armazenadas como texto sem formatação, mas como valores de hash (valores numéricos que identificam exclusivamente  os dados). Uma tabela do arco-íris é um grande dicionário de hashes pré-computados e as senhas das quais eles foram calculados.
Um ataque do arco-íris compara o hash de uma senha com os armazenados na tabela do arco-íris. Quando um invasor encontra uma correspondência, ele identifica a senha usada para criar o hash.

- **Interceptação de tráfego**: Texto sem formatação ou senhas sem criptografia podem ser facilmente lidas por outras pessoas e máquinas interceptando comunicações.

#### ~={green}Ameaças persistentes avançadas=~
Advanced Persistent Threat (APT) – uma operação multi-fase, longo prazo, furtiva e avançada contra um alvo específico. Por essas razões, um invasor geralmente não tem o conjunto de habilidades, os recursos ou a persistência para realizar APTs.
Seu principal objetivo é implantar malware personalizado em um ou mais sistemas do alvo e permanecer lá sem ser detectado.

---

### ~={red}Exploits e vulnerabilidade de segurança=~

Vulnerabilidades de hardware são frequentemente introduzidas por falhas de projeto de hardware.

#### ~={green}Vulnerabilidade de Hardware=~
- Meltdown e Spectre
	- Os invasores que exploram essas vulnerabilidades podem ler toda a memória de um determinado sistema (Meltdown), bem como os dados manipulados por outras aplicações (Spectre). As explorações de vulnerabilidade Meltdown e Spectre são conhecidas como ataques de canal lateral (as informações são obtidas com a implementação de um sistema de computador).

#### ~={green}Vulnerabilidades de Software=~
As vulnerabilidades de software geralmente são introduzidas por erros no sistema operacional ou no código do aplicativo.

**Categorias**: 
- Estouro de buffer:  Os buffers são áreas de memórias alocadas a um aplicativo. Uma vulnerabilidade ocorre quando os dados são gravados além dos limites de um buffer.
- Entrada não valida: Os programas geralmente exigem entrada de dados, mas esses dados recebidos podem ter conteúdo malicioso, projetado para forçar o programa a se comportar de maneira não intencional.
- Condições de corrida: Esta vulnerabilidade descreve uma situação em que a saída de um evento depende de saídas ordenadas ou cronometradas. Assim podem bagunçar essa ordenação
- Fragilidade nas práticas de segurança: Sistemas e dados confidenciais podem ser protegidos por meio de técnicas como autenticação, autorização e criptografia.
- Problemas de controle de acesso: O controle de acesso é o processo de controlar quem faz o quê e abrange desde o gerenciamento do acesso físico ao equipamento até ditar quem tem acesso a um recurso, como um arquivo, e o que pode ser feito com ele, como ler ou alterar o arquivo.

#### ~={green}Atualizações de software=~
O objetivo das atualizações de software é sempre estar atualizado e evitar a exploração de vulnerabilidades.

---

### ~={red}O cenário da cibersegurança=~

#### ~={green}Criptomoeda=~
A criptomoeda é o dinheiro digital que pode ser usado para comprar produtos e serviços, usando técnicas de criptografia fortes para proteger transações on-line.
- Quando uma transação ocorre entre os proprietários de duas carteiras digitais, os detalhes são registrados em um sistema de contabilidade descentralizado, assim realizado com certo grau de anonimato e é autogerenciado, sem interferência de terceiros , como bancos centrais ou entidades governamentais.
- Computadores especiais coletam dados sobre as últimas transações de criptomoeda. Essas transações são então verificadas através de um processo técnico e altamente complexo conhecido como “mineração”.
- Uma vez verificado, o razão é atualizado e copiado e disseminado eletronicamente em todo o mundo para qualquer pessoa que pertence à rede blockchain, concluindo com eficiência uma transação.

#### ~={green}Cryptojacking=~
O cryptojacking é uma ameaça emergente que se esconde no computador, telefone celular, tablet, laptop ou servidor do usuário, usando os recursos dessa máquina para "extrair" moedas criptografadas sem o consentimento ou conhecimento do usuário .