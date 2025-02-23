A tecnologia **FTTH (Fiber to the Home)** consiste em levar a **fibra óptica** diretamente até a residência do assinante, proporcionando conexões de alta velocidade e suporte a múltiplos serviços digitais (voz, dados, vídeo).

### ~={yellow}1. Conceito e Benefícios=~

- **Definição**: Levar a fibra óptica até o assinante final (casa/apartamento), substituindo o cabeamento metálico (cobre ou coaxial).
- **Velocidades elevadas**: Permite tráfegos em Gbps, adequados para streaming 4K/8K, realidade virtual, IoT etc.
- **Maior confiabilidade**: A fibra sofre menos interferência elétrica e oferece menos perdas de sinal.
- **Escalabilidade**: Facilita upgrades de largura de banda, pois o meio físico (fibra) suporta cada vez mais velocidades.

---

### ~={yellow}2. Evolução e Adoção=~

- **Início nos anos 1990**: Surgiu como alternativa para oferecer Internet de maior velocidade diretamente ao usuário.
- **Crescimento Global**: Muitos países investem na infraestrutura de fibra para suportar demanda crescente de serviços digitais.
- **Estatísticas**:
    - **Brasil**: Penetração de FTTH deve chegar a 75% dos domicílios até 2025.
    - **América Latina**: A fibra representa mais de 60% da banda larga doméstica em alguns países.
    - **Global**: Países como Emirados Árabes, Singapura e Hong Kong já ultrapassam 90% de cobertura FTTH.

---

### ~={yellow}3. Comparação com Tecnologias Legadas=~

1. **xDSL (ADSL, VDSL)**
    - Usa cabos de cobre, sofre interferência e perda de sinal conforme a distância.
    - Velocidades assimétricas e limitadas.

2. **Cabo Coaxial**
    - Compartilhado entre vários assinantes; congestionamento em horários de pico.
    - Evoluções (DOCSIS) melhoram, mas ainda limitadas em comparação à fibra.

3. **Fibras Ponto a Ponto**
    - Alta capacidade, mas custo de instalação/ manutenção elevado em grandes redes.

---

### ~={yellow}4. Componentes de uma Rede FTTH=~

- **OLT (Optical Line Terminal)**: Equipamento no provedor que controla a transmissão, gerencia splitters e ONUs/ONTs.
- **ONU/ONT (Optical Network Unit/Terminal)**: Dispositivo no local do assinante que converte sinal óptico em elétrico (Ethernet, Wi-Fi etc.).
- **Splitters Ópticos**: Divisores passivos que repartem a fibra vinda da OLT para múltiplos assinantes (1:16, 1:32 ou 1:64, etc.).
- **ODN (Optical Distribution Network)**: Rede passiva de cabos e splitters entre OLT e ONU.

---

### ~={yellow}5. Tecnologias Principais=~

- **GPON (Gigabit PON)**: Downstream 2.5 Gbps / Upstream 1.25 Gbps; suporta até 128 ONUs por porta.
- **EPON (Ethernet PON)**: Usa padrões Ethernet, com velocidades simétricas (1.25 Gbps).
- **XGS-PON (10-Gigabit Symmetrical PON)**: Oferece até 10 Gbps tanto em downstream quanto em upstream.

---

### ~={yellow}6. Funcionamento Básico=~

- **Downstream**: A OLT transmite dados em broadcast para todas as ONUs, mas cada ONU filtra apenas o que lhe pertence.
- **Upstream**: As ONUs usam **TDMA** (Time Division Multiple Access), enviando dados em intervalos de tempo programados pela OLT para evitar colisões.
- **DBA (Dynamic Bandwidth Allocation)**: Mecanismo que ajusta dinamicamente a alocação de banda para cada ONU, otimizando o uso dos recursos disponíveis.

---

### ~={yellow}7. Outras Variedades de FTTx=~

- **FTTR (Fiber-To-The-Room)**: Fibra até cada cômodo, garantindo velocidade e estabilidade internas.
- **FTTC (Fiber-To-The-Curb)**: Fibra até um armário de rua, depois cobre/coaxial para o assinante.
- **FTTN (Fiber-To-The-Node)**: Similar ao FTTC, mas com distância maior do armário até o assinante.
- **FTTD (Fiber-To-The-Desk)**: Fibra literalmente até a mesa ou dispositivo final.