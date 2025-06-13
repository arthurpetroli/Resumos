Todo projeto possui uma estrutura que é composta pelas seguintes etapas:

1- Iniciação: Onde é feito o termo de abertura do projeto com as especificações e informações do cliente e da equipe de desenvolvimento. Nessa etapa será feita uma análise e documentação com uma visão mais macro de todo o processo para que essas informações sejam utilizadas como recursos nas etapas seguintes.

2- Planejamento: Essa etapa, inclui a definição do escopo do projeto (o que deve ser feito), cronograma, definição de tecnologias utilizadas, equipe de desenvolvimento, papéis (quando se trata principalmente de metodologias ágeis), definição e sequência de atividades que serão realizadas baseado no escopo, a estimativa de custos, os riscos que podem ter, o orçamento disponível, entre outros fatores.

3- Execução: Agora é hora de colocar em prática tudo o que foi definido no planejamento. Onde será executado e documentado todo processo.

4- Controle: É onde os líderes do projeto precisam fazer o gerenciamento do andamento das atividades com a expectativa do cronograma. Geralmente essa etapa anda junto com a Execução, pois é necessário identificar algum tipo de desvio entre o que foi planejado e o que está sendo executado, evitando atrasos na entrega ou possíveis desperdícios.

5- Finalização: É nessa etapa que serão feitas as validações e entregas finais de operação e documentação para o cliente final. Durante todo o projeto, pequenas entregas e validações vão sendo feitas, mas no final é necessário fazer a validação para entrega final.

---

## Ciclo de vida de desenvolvimento

O ciclo de vida de um processo de desenvolvimento é o conjunto de processos, atividades e etapas que são seguidas dentro de um projeto de desenvolvimento de software. Ele indica quando e como o projeto começa e a forma como ele deve ser conduzido até ser finalizado e entregue ao cliente.

Independente da metodologia utilizada, dentro do processo de desenvolvimento temos 3 etapas principais:

1- Definição (onde vamos entender o que precisa ser desenvolvido e definir as etapas que devem ser seguidas);

2- Desenvolvimento (onde serão desenvolvidas e testadas todas as funcionalidades definidas anteriormente)

3- Operação/ Manutenção (é quando o sistema começa a ser utilizado pelo cliente e se forem detectadas falhas ou necessidade de implementação, deve ser corrigido/implementado imediatamente pela equipe)

---

Requisitos são as necessidades do sistema ou funções que ele deve desempenhar. Eles podem ser classificados em 2 tipos: Funcionais e Não Funcionais.

Requisitos Funcionais: São todas as funcionalidades ou características esperadas pelo cliente que podem atender às demandas de um processo, como por exemplo: realizar um cadastro de um produto, realizar pagamentos, fazer reservas de produtos e agendamento de serviços, etc. Eles atendem às regras de negócio estabelecidas pela empresa nos processos.

Requisitos Não Funcionais: Define a forma como o sistema deve realizar determinadas atividades e como ele irá prover os requisitos funcionais de forma eficiente, como por exemplo: Ele deve ser multiplataforma ou ser utilizado apenas no sistema operacional Linux; Utilizará uma stack específica de tecnologias Javascript; Será hospedado em um servidor específico; Medidas de segurança para garantir a integridade do sistema, etc.

---

Quando utilizamos metodologias ágeis de desenvolvimento, o pensamento é diferente. As etapas que seguimos não são tão diferentes, mas elas são tratadas de forma diferente. Nesse contexto, os princípios são: colaboração e comunicação entre os envolvidos no projeto (equipe e cliente). A ideia é responder de forma rápida e eficiente a possíveis mudanças para aumentar o valor e qualidade do produto final. Então na primeira etapa, não necessariamente teremos todos os requisitos definidos em documentações extensas, mas teremos uma visão geral e definição do máximo de requisitos possíveis, mas não acaba por aí. Como as metodologias ágeis preveem que haja entregas menores com validação do cliente, é possível que nessas pequenas entregas os requisitos estejam mais claros ou sejam alterados para atender melhor as necessidades.

No contexto de desenvolvimento ágil, temos um recurso que se chama “User Stories” ou Histórias do Usuário, que também representa os requisitos do sistema, mas de uma forma diferente. Elas são explicações curtas, informais e mais gerais sobre um recurso de software, escrito a partir da perspectiva do usuário final ou do cliente, por exemplo: “Como cliente, gostaria de realizar meu cadastro na plataforma, onde eu possa comprar os produtos da loja”. Veja que ela possui uma estrutura, apesar de simples, precisa conter: O tipo de usuário, o que ele quer e para que. Essa estrutura não é obrigatória, mas ajuda muito. Cada equipe pode ter sua estrutura própria.

---

## Ferramentas para análise de requisitos

![[Pasted image 20250613155632.png]]

A UML (Unified Modeling Language, ou Linguagem de Modelagem Unificada) é uma linguagem de notação, ou seja, ela proporciona uma forma muito específica de escrever, comunicar e ilustrar, que vão trazer visões diferentes do sistema baseadas nos requisitos que são levantados durante as etapas iniciais, principalmente.

É classificada como uma linguagem, pois possui símbolos e processos específicos que são utilizados para expressar determinados elementos do sistema. Existem dois tipos de diagramas dentro da UML: os diagramas estruturais e os comportamentais.

Os diagramas estruturais representam toda parte estática do sistema como: classes, métodos, interfaces, componentes, serviços, arquitetura do sistema, entre outros.

Os diagramas comportamentais representam a parte dinâmica, que é composta pela interação entre elementos ou o fluxo de ações que podem ser feitas dentro do sistema, troca de dados e de mensagens entre serviços e componentes, entre outros.

A UML conta com 21 diagramas diferentes, como: Diagrama de casos de uso, de classes, de atividades, de sequencia, entre outros. A utilização desses diagramas dentro do projeto vão ajudar a manter uma padronização de comunicação entre a equipe, não só na etapa de desenvolvimento, mas na documentação dele.

Outra ferramenta que podemos utilizar, é a User Story, como foi citado nas aulas anteriores, que podem ajudar a entender aquilo que o cliente precisa.

---

## Diagrama de Casos de Uso

Os elementos que utilizamos nesse diagrama são:

Ator: Representa os usuários do sistema, aqueles que irão interagir diretamente com as funcionalidades representadas.

Selecione uma imagem

Casos de Uso: São as funcionalidades, utilizadas pelos atores. Representam as possibilidades de ações dentro do sistema.

Temos algumas ligações que estão em linha pontilhada, com a marcação “Include” e “extend”, isso significa que no caso do “include”, é uma ação obrigatória, o que significa no nosso exemplo que todos os atores precisam fazer login, obrigatoriamente.

No caso do “extend”, significa que ela pode acontecer ou não. No nosso exemplo, ao remarcar uma consulta, a pessoa que será recepcionista, pode enviar ou não, um email de confirmação. Pode ser que o paciente não tenha email ou não queira receber.

![[Pasted image 20250613154548.png]]

---

## Diagrama de Atividades

​Nesse diagrama, temos uma visão macro dos processos e subprocessos. Dessa forma podemos identificar possíveis falhas e corrigir a tempo. Isso vai nos ajudar a tomar decisões melhores com relação ao fluxo da aplicação. Ele pode ser utilizado nas diferentes fases do projeto, com diferentes objetivos. Na etapa de análise de requisitos, ele nos ajuda apresentando diferentes fluxos de processos que vão guiar algumas decisões sobre o fluxo do sistema. Mas ele também pode ser utilizado em outras etapas para demonstrar outros pontos da aplicação ou da regra de negócio.

É bem parecido com um fluxograma, então você vai ver elementos muito parecidos, mas ele possui outras ferramentas também.

![[Pasted image 20250613154616.png]]

---

## Construindo um MER

![[Pasted image 20250613154645.png]]

---
## Transformando os requisitos em tasks

​Depois que os requisitos são levantados, precisamos criar uma lista de atividades a serem realizadas e transformar isso em um cronograma para começar a executar as tarefas. A regra principal é quebrar em partes menores para que possam ser atingíveis e mensuráveis

Vamos voltar no nosso diagrama de casos de uso e no diagrama de classes para começar a extração das tasks:

Diagrama de Casos de Uso

Selecione uma imagem

Diagrama de Atividades

Selecione uma imagem

Vamos começar com um brainstorming, extraindo algumas funcionalidades que percebemos aqui.

Agora que já temos as funcionalidades que serão implementadas, vamos começar a criar um cronograma de 1 semana para desenvolvimento dessas tasks. Nós colocamos na coluna de To-do, aquelas atividades que serão desenvolvidas na semana e a ideia é que no final da semana, todas estejam na coluna Complete.​

![[Pasted image 20250613155014.png]]

![[Pasted image 20250613155131.png]]
