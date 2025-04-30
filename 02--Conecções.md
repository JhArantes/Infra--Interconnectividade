
# 🌐 Infraestrutura e Interconectividade de Redes – Conceitos Técnicos Avançados

> Documentação técnica sobre redes de computadores, com foco em endereçamento IP, roteamento, comutação, protocolos e arquitetura de redes.  
> *Autor: João Henrique Arantes*  
> *Última atualização: Abril/2025*

---

## 1. 🧠 Endereçamento IP – IPv4 e IPv6

### 🔹 IPv4 (Internet Protocol version 4)
- Endereços de **32 bits**, divididos em **4 octetos** (ex: `192.168.0.10`).
- Define identificadores únicos para cada host em uma rede.

#### 📌 Classes de IP:
| Classe | Faixa de IP                | Uso típico         |
|--------|----------------------------|--------------------|
| A      | 1.0.0.0 a 126.255.255.255  | Redes muito grandes |
| B      | 128.0.0.0 a 191.255.255.255| Redes médias        |
| C      | 192.0.0.0 a 223.255.255.255| Redes pequenas      |

#### 📌 Endereços Reservados:
- `127.0.0.1` → Loopback (localhost)
- `169.254.x.x` → APIPA (endereços automáticos sem DHCP)
- `192.168.x.x`, `10.x.x.x`, `172.16.0.0 – 172.31.255.255` → Faixas privadas

### 🔹 Máscara de Sub-rede (Subnet Mask)
Define o **tamanho da rede** e a quantidade de hosts possíveis.

Exemplo:
```
255.255.255.0 = /24 (CIDR)
→ Permite 254 hosts válidos (de 192.168.0.1 a 192.168.0.254)
```

**Fórmula de cálculo:**
```
2^(bits restantes) - 2
```

### 🔹 IPv6
Criado para substituir o IPv4, com **endereços de 128 bits**.

Vantagens:
- Endereçamento expandido
- Autoconfiguração
- Segurança nativa via IPsec

**Exemplo de endereço IPv6:**
```
FE80::202:17FF:FE2B:A21E
```

---

## 2. 🚪 Gateway Padrão e Roteamento

- O **gateway padrão** é o dispositivo que conecta a rede local a outras redes (geralmente um roteador).
- Se um dispositivo tenta acessar um IP fora de sua sub-rede, os dados são enviados ao gateway.

Os **roteadores operam na camada 3** do modelo OSI e usam **tabelas de roteamento** para determinar o melhor caminho para os pacotes.

---

## 3. 🔄 Switching e VLANs

### 🖧 Switch
Dispositivo de **camada 2 (enlace)** que utiliza endereços **MAC** para encaminhar quadros de dados dentro de uma LAN.

### 🔀 Tipos de Switching:
- **Store and Forward**: Lê o quadro inteiro antes de encaminhar.
- **Cut Through**: Encaminha assim que lê o destino.
- **Fragment Free**: Verifica os primeiros 64 bytes.

### 📦 VLANs (Virtual LANs)
Segmentam logicamente uma rede física, criando domínios isolados de broadcast.

---

## 4. 🧱 Modelo OSI – Camadas da Arquitetura de Rede

| Camada | Função                         | Exemplos                |
|--------|--------------------------------|--------------------------|
| 7      | Aplicação                      | HTTP, FTP                |
| 6      | Apresentação                   | SSL, TLS                 |
| 5      | Sessão                         | NetBIOS, RPC             |
| 4      | Transporte                     | TCP, UDP                 |
| 3      | Rede                           | IP, ICMP                 |
| 2      | Enlace (Data Link)             | Ethernet, Switch         |
| 1      | Física                         | Cabos, sinais, Wi-Fi     |

---

## 5. 🔌 Conectividade e Serviços de Rede

### 📍 DHCP – *Dynamic Host Configuration Protocol*
Atribui endereços IP de forma automática aos dispositivos:

```
Discover → Offer → Request → ACK
```

### 🌐 DNS – *Domain Name System*
Resolve nomes de domínio para IPs, por exemplo:
```
www.google.com → 142.250.190.36
```

### 🔁 NAT – *Network Address Translation*
Permite que dispositivos com **endereços privados** acessem a internet utilizando um **único IP público**.

---

## 6. 🏠 LAN e Arquitetura Física

### 🔸 LAN (Local Area Network)
Rede local usada em ambientes como escritórios e residências.

### 🔸 Topologia Estrela
Cada dispositivo conectado a um switch central — **modelo mais comum e eficiente**.

### 🔸 Cabeamento
- **Cat5e/Cat6**: para redes Ethernet convencionais
- **Fibra óptica**: para maior velocidade e menor latência

### 🔸 Arquitetura Hierárquica:
- **Core Layer**: Alta velocidade e roteamento
- **Distribution Layer**: Controle e políticas de rede
- **Access Layer**: Conecta dispositivos finais (PCs, laptops, etc.)

---

## 7. ⚙️ Comandos Essenciais no Packet Tracer (CLI)

```bash
enable                    # Acessa o modo privilegiado
configure terminal        # Entra no modo de configuração global
interface fa0/1           # Seleciona a interface FastEthernet 0/1
ip address 192.168.0.1 255.255.255.0  # Define IP e máscara
no shutdown               # Ativa a interface
show ip interface brief   # Mostra o status das interfaces
ping 192.168.0.10         # Testa a conectividade com outro host
```

---

## ✅ Conclusão

O domínio da infraestrutura de redes vai além da configuração de dispositivos: envolve compreender como os dados trafegam, como os dispositivos se comunicam e como manter essa comunicação segura, eficiente e escalável.

Compreender conceitos como endereçamento IP, VLANs, roteamento, switching e serviços como DHCP, DNS e NAT é essencial para projetar, gerenciar e evoluir ambientes de rede modernos.

Ferramentas como o **Cisco Packet Tracer** permitem aplicar esses conceitos na prática, com simulações realistas que preparam estudantes e profissionais para desafios do mundo real. Ao dominar essas ferramentas e fundamentos, você se posiciona como um elemento-chave para garantir a **conectividade e a performance** de qualquer infraestrutura de TI.
