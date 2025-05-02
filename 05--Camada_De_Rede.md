# Infraestrutura e Interconectividade - Camadas de Rede

## Camada de Enlace (Data Link) - Modelo OSI

A Camada de Enlace é responsável pela comunicação entre dois dispositivos diretamente conectados, sendo dividida em duas subcamadas principais:

### 🔹 Camada MAC (Media Access Control)

- Responsável pelo **endereçamento físico** (MAC Address) da placa de rede.
- Atua diretamente no **hardware** da máquina.
- Garante o controle de acesso ao meio físico e a **transmissão de quadros** (frames) na rede.

### 🔹 Camada LLC (Logical Link Control)

- Responsável pelo **controle lógico da conexão** entre dispositivos.
- Atua na **identificação de protocolos** da camada de rede e no **encapsulamento em quadros**.
- Oferece serviços de detecção e correção de erros.

---

## Topologias de Rede

Existem diversas formas de organizar os dispositivos em uma rede. Essa organização pode ser **física** (cabeamento) ou **lógica** (fluxo de dados).

### 🌐 Tipos de Topologia

- **Topologia Estrela**: Dispositivos conectados a um **switch central**. É a mais utilizada atualmente.
- **Topologia Estrela Estendida**: Conexão de **várias topologias estrela** entre si.
- **Topologia de Barramento**: Todos os dispositivos conectados a um **único barramento central**.
- **Topologia em Anel**: Muito usada com **fibra ótica**. Boa para **redundância** e **alta disponibilidade**.

---

## Cibersegurança e Comunicação em Redes

- A comunicação entre dispositivos ocorre por meio de **protocolos**, **quadros** e **pacotes**.
- Os dados passam da **camada física** (bits) → **enlace** (quadros) → **rede** (pacotes).

---

## IP - Internet Protocol

O **IP** é um protocolo da **camada de rede** responsável pelo endereçamento lógico e roteamento de pacotes.

### 📦 Características:

- IP padrão: **32 bits** (IPv4) e **128 bits** (IPv6).
- Funciona **independentemente do meio físico ou lógico**.
- Semelhante ao envio de uma carta: rua, cidade, CEP, país → **endereçamento lógico**.

---

## Roteamento

### 🔧 O que é?

- Processo de **interconexão entre redes diferentes**, baseado em **endereços IP**.
- Feito por **roteadores**, dispositivos especializados com memória, CPU e sistema próprio.

### 📡 Modem vs Roteador

- **Modem** conecta à internet.
- **Roteador** distribui a conexão internamente, podendo realizar **roteamento entre redes**.

### 🛣️ Gateway

- **Porta de saída padrão** para outras redes.
- Todo dispositivo que precisa acessar a internet **passa pelo gateway**.
- É o **intermediário entre rede interna e externa**.

---

## Endereçamento IP

### 📍 Máscara de Sub-rede

- Define **quantos hosts** e **sub-redes** podem existir.
- Exemplos:

  | Classe | Máscara Padrão       | Hosts por Rede       |
  |--------|----------------------|-----------------------|
  | A      | 255.0.0.0            | ~16 milhões           |
  | B      | 255.255.0.0          | ~65 mil               |
  | C      | 255.255.255.0        | 254                   |

---

## Cálculo de Sub-rede

### Exemplo: `192.168.0.10/26`

- Conversão: `/26 = 255.255.255.192 → 11111111.11111111.11111111.11000000`
- Interpretação:

  - 2 bits para sub-redes → 2² = **4 sub-redes**
  - 6 bits para hosts → 2⁶ = **64 endereços**
  - Hosts utilizáveis: 64 - 2 (ID de rede e broadcast) = **62 por sub-rede**

### 📋 Sub-redes:

| Sub-rede | Endereço Inicial | Endereço Final | Broadcast |
|----------|------------------|----------------|-----------|
| 1        | 192.168.0.0      | 192.168.0.63   | 192.168.0.63 |
| 2        | 192.168.0.64     | 192.168.0.127  | 192.168.0.127 |
| ...      | ...              | ...            | ... |

---

> 🔐 Redes, infraestrutura e protocolos de roteamento são a base de uma internet funcional, segura e eficiente. Compreender essas estruturas é essencial para qualquer profissional de TI, Redes ou Cibersegurança.
