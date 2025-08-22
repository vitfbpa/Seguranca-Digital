# DNS, DNS Reverso & DDNS 

# DevSecOps

**DevSecOps** representa a união entre Desenvolvimento (Dev), Segurança (Sec) e Operações (Ops) em um fluxo contínuo e colaborativo, priorizando automação, monitoramento e proteção desde o início do ciclo de desenvolvimento do software.

---

# DNS (Domain Name System)

- **Camada**: 7 (Aplicação)
- **Porta padrão**: 53
- **Protocolo**: UDP (Camada 4 - Transporte)  
  - Em algumas situações, utiliza TCP (ex: transferências de zona)

## Exemplos de Servidores DNS

- **8.8.8.8** – Servidor DNS público do Google
- **200.132.59.59** (Primário) – DNS da UFN
- **200.132.59.60** (Secundário) – DNS da UFN
- **200.132.59.110** – Endereço IP do site oficial da UFN
- **Proxy/Firewall**: 200.132.59.110.2 *(confirmar se o IP está correto – possível erro de digitação)*

---

## Exemplo de Consulta DNS

**Objetivo**: Um dispositivo deseja acessar `www.ufn.edu.br`

### Dados da Estação:

- **Endereço IP**: 10.104.16.3  
- **Máscara de sub-rede**: 255.255.255.192  
- **Gateway padrão**: 10.104.16.1  
- **Servidores DNS configurados**:
  - Primário: 10.21.19.14
  - Secundário: 10.21.19.15

### Fases do Processo:

1. **ARP** – Descobre o endereço MAC do gateway ou do servidor DNS.
2. **ICMP** – Pode ser usado para testar conectividade (ex: comando `ping`).
3. **Consulta DNS** – A estação envia uma requisição pela porta 53/UDP.
4. **Resposta DNS** – O servidor responde com o IP do domínio requisitado (`www.ufn.edu.br` → 200.132.59.110).

---

## Perguntas úteis para diagnóstico de rede:

- **"Quem eu sou?"**  
  → Determina o endereço IP da própria máquina.

- **"É meu vizinho?"**  
  → Avalia se o IP de destino está na mesma sub-rede, com base na máscara.

---

# DDNS (DNS Dinâmico)

- Permite atualizar automaticamente os registros DNS de hosts com IPs dinâmicos.
- Frequentemente utilizado por redes domésticas ou pequenos servidores sem IP fixo.

---

# DNS Reverso

- Utiliza registros do tipo **PTR**.
- Permite identificar o **nome de domínio** associado a um determinado **endereço IP**.
- Exemplo: `200.132.59.110` → consulta PTR → resposta: `www.ufn.edu.br`

---

# Entidades de Registro de Domínios

- **Registro.br** – Entidade responsável pela gestão dos domínios ".br"
- **Terra** – Pode atuar como provedor de DNS ou hospedagem de sites

---
