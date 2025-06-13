### ~={red}Como Proteger a rede e os dispositivos=~
#### ~={green}Proteger seus dispositivos de computação=~
- **Ative o firewall**:  Você deve usar pelo menos um tipo de firewall (firewall de software ou de hardware em um roteador) para proteger seu dispositivo contra acesso não autorizado. O firewall deve estar ativado e atualizado constantemente para impedir que hackers acessem seus dados pessoais ou da empresa.

- **Instalar antivírus e antispyware**:  Usar um software antivírus para fornecer outra camada de proteção. Este software, que geralmente inclui antispyware, foi projetado para verificar a presença de vírus em seu computador e nos e-mails recebidos e excluí-los. Manter seu software atualizado protegerá seu computador de qualquer novo software malicioso que surgir.

- **Gerencie o sistema operacional e navegador**:  Para proteger seu computador e seus dados, você deve definir as configurações de segurança em seu computador e navegador para nível médio ou superior. Você também deve atualizar regularmente o sistema operacional do seu computador, incluindo o navegador da web, e baixar e instalar os patches de software e atualizações de segurança mais recentes dos fornecedores.

- **Configurar proteção por senha**:  Todos os seus dispositivos de computação, incluindo PCs, laptops, tablets e smartphones, devem ser protegidos por senha para evitar acesso não autorizado.

#### ~={green}Segurança de rede sem fio em casa=~
As redes sem fio permitem que dispositivos habilitados para Wi-Fi, como laptops e tablets, se conectem à rede por meio de um identificador de rede predefinido, conhecido como identificador de conjunto de serviço (SSID). Embora um roteador sem fio possa ser configurado para não transmitir o SSID, isso não deve ser considerado segurança adequada para uma rede sem fio.

Esta vulnerabilidade pode ser explorada por ataques de reinstalação de chave (KRACKs) por invasores. Em termos simples, os invasores interrompem a criptografia entre um roteador wireless e um dispositivo sem fio, dando-lhes acesso aos dados da rede. Ela afeta todas as redes WiFi modernas e protegidas.

Para mitigar essa situação, você deve:

- Atualizar todos os dispositivos sem fio, como roteadores, laptops e dispositivos móveis, assim que as atualizações de segurança estiverem disponíveis
- Usar uma conexão com fio para todos os dispositivos com uma placa de interface de rede com fio (NIC)
- Use um serviço confiável de rede virtual privada (VPN) ao acessar uma rede sem fio.

#### ~={green}Riscos públicos de Wi-Fi=~
Quando você está longe de casa, pode acessar suas informações online e navegar na Internet por meio de redes sem fio públicas ou pontos de acesso wi-fi. No entanto, há alguns riscos envolvidos, o que significa que é melhor não acessar ou enviar nenhuma informação pessoal ao usar o Wi-Fi público.


#### ~={green}Diretrizes de Senha=~
O Instituto Nacional de Padrões e Tecnologia (NIST) dos Estados Unidos publicou requisitos de senha aprimorados. Os padrões do NIST destinam-se a aplicações governamentais, mas também podem servir de padrão para outros setores.

Essas diretrizes visam atribuir a responsabilidade de verificação de usuário aos provedores de serviços e garantir uma experiência melhor para os usuários em geral. Eles afirmam:

- As senhas devem ter no mínimo oito caracteres, mas não mais que 64 caracteres.
- Senhas comuns e facilmente adivinhadas, como ‘senha’ ou ‘abc123’ não devem ser usadas.
- Não deve haver regras de composição, como ter que incluir letras maiúsculas e minúsculas e números.
- Os usuários devem poder ver a senha ao digitar, para ajudar a melhorar a precisão.
- Todos os caracteres e espaços devem ser permitidos.
- Não deve haver dicas de senha.
- Não deve haver período de expiração de senha.
- Não deve haver autenticação baseada em conhecimento, como fornecer respostas a perguntas secretas ou verificar o histórico de transações.

---

### ~={red}Manutenção de dados=~

#### ~={green}O que é criptografia?=~
Criptografia é o processo de converter informações em um formato no qual pessoas não autorizadas não possam lê-las. Somente uma pessoa confiável, autorizada com a chave secreta ou uma senha pode descriptografar os dados e acessá-los em sua forma original.

#### ~={green}Como você criptografa seus dados?=~
O EFS (Encrypting File System, Sistema de Criptografia de Arquivos) é uma característica do Windows que pode criptografar dados. Ele está diretamente vinculado a uma conta de usuário específica e somente o usuário que criptografa os dados poderá acessá-los depois de criptografados usando EFS.

- Etapa 1:  Selecione um ou mais arquivos ou pastas.
- Etapa 2:  Clique com o botão direito nos dados selecionados e vá para ‘**Propriedades**.’
- Etapa 3:  Localize e clique em “**Avançado**”.
- Etapa 4:  Marque a caixa de seleção ‘**Criptografar conteúdo para proteger os dados**’.
- Etapa 5:  Os arquivos e pastas criptografados com EFS são exibidos em verde, conforme mostrado aqui.

#### ~={green}Faça backup de seus dados=~
Ter um backup pode evitar a perda de dados insubstituíveis. Para fazer backup dos dados corretamente, você precisará de um local de armazenamento adicional para os dados e deve copiar os dados para esse local regularmente.
- Rede residencial 
- Local secundário
- A nuvem

## ~={orange}Importante: =~ 
Quando você move um arquivo para a lixeira e o exclui permanentemente, o arquivo fica inacessível apenas pelo sistema operacional. Qualquer pessoa com as ferramentas forenses corretas ainda pode recuperar o arquivo devido a um traço magnético deixado no disco rígido.


#### ~={green}Como você exclui os dados permanentemente?=~
Para apagar dados para que não sejam mais recuperáveis, eles devem ser substituídos por uns e zeros várias vezes, usando ferramentas projetadas especificamente para fazer exatamente isso. O SDelete da Microsoft afirma ter a capacidade de remover arquivos confidenciais completamente. Shred para Linux e Secure Empty Trash para Mac OS X afirmam fornecer um serviço semelhante.
### Basic Usage

1. **Delete a Single File Securely:**
    
    `sdelete64 -p 3 filename.txt`
This command will securely delete `filename.txt` by overwriting it 3 times.

2. **Delete All Files in a Directory Securely:**
    
    `sdelete64 -p 3 -s C:\path\to\directory`
This command will securely delete all files within the specified directory, overwriting each file 3 times.

3. **Wipe Free Space on a Drive:**
    
    `sdelete64 -z C:`
This command will zero out the free space on the C: drive, making it harder to recover deleted files.


A única maneira de ter a certeza de que os dados ou arquivos não sejam recuperáveis é destruir fisicamente o disco rígido ou o dispositivo de armazenamento. Muitos criminosos se valeram de arquivos considerados impenetráveis ou irrecuperáveis!

---

### ~={red}Quem é o dono dos seus dados?=~

#### ~={green}Compreensão dos termos=~
Os Termos de Serviço incluirão várias seções, desde direitos e responsabilidades do usuário a isenções de responsabilidade e termos de modificação de conta.
- A política de uso de dados descreve como o provedor de serviços coletará, usará e compartilhará seus dados.
- As configurações de privacidade permitem controlar quem vê informações sobre você e quem pode acessar seus dados de perfil ou de conta.
- A política de segurança descreve o que a empresa está fazendo para proteger os dados obtidos de você.

#### ~={green}Antes de se inscrever=~
Quais fatores você deve considerar antes de se inscrever em um serviço on-line?
- Você já leu os Termos de Serviço?
- Quais são os seus direitos em relação aos seus dados?
- Você pode solicitar uma cópia de seus dados?
- O que o provedor pode fazer com os dados dos quais você fez upload?
- O que acontece com seus dados depois que você fecha sua conta?

---

### ~={red}Como proteger a privacidade on-line=~

#### ~={green}Autenticação de dois fatores=~
Além de seu nome de usuário e senha ou número de identificação pessoal (PIN), a autenticação de dois fatores requer um segundo token para verificar sua identidade. Pode ser:

- Objeto físico, como um cartão de crédito, telefone celular ou fob (chave de segurança)
- Varredura biométrica, como impressão digital ou reconhecimento facial e de voz
- Código de verificação enviado por SMS ou e-mail.

#### ~={green}Autorização Aberta=~
Autorização Aberta (OAuth) é um protocolo padrão aberto que permite que você use suas credenciais para acessar aplicativos de terceiros sem expor sua senha.

#### ~={green}Privacidade de e-mail e navegador da Web=~
Esses problemas podem ser minimizados ativando o modo de navegação privada em seu navegador. A maioria dos navegadores da web mais comumente usados têm seus próprios nomes para o modo de navegação privada:
- **Microsoft Internet Explorer**: Navegação InPrivate
    
- **Google Chrome**: Anônimo
    
- **Mozilla Firefox**: Janela privativa
    
- **Safari**: Navegação Privada

Quando o modo privado está ativado, os cookies, arquivos salvos em seu dispositivo para indicar quais sites da Web visitados, são desativados. Portanto, todos os arquivos temporários da Internet são removidos e o histórico de navegação é excluído quando você fecha a janela ou o programa. Isso pode ajudar a evitar que outras pessoas colham informações sobre suas atividades online e tentem induzi-lo a comprar algo com anúncios direcionados.

Mesmo com a navegação privada habilitada e os cookies desabilitados, as empresas estão constantemente desenvolvendo novas maneiras de identificar as impressões digitais dos usuários para rastrear seu comportamento online. Por exemplo, alguns dispositivos intermediários, como roteadores, podem reunir informações sobre o histórico de navegação de um usuário na web.

---

