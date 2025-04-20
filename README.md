# Laboratório Azure - Criação de Máquina Virtual

Repositório criado como parte do desafio da DIO para documentar a experiência de criação e configuração de uma máquina virtual na plataforma Microsoft Azure.

Aqui você encontrará:
- Resumos dos principais conceitos
- Passo a passo detalhado da criação da VM
- Dicas práticas e boas práticas
- Soluções para problemas comuns

🚀 Vamos nessa!

resumos/conceito-de-maquina-virtual.md
O que é uma VM

Diferença entre VM e bare metal

Casos de uso comuns

# 🧠 Conceito de Máquina Virtual (VM)

## 💻 O que é uma Máquina Virtual?

Uma **máquina virtual (VM)** é um ambiente computacional virtualizado que simula um computador físico. Ela roda em cima de um hardware real (host), por meio de um software chamado **hipervisor**, que permite executar múltiplas VMs de forma isolada e segura.

Cada VM possui:
- Sistema operacional próprio (Windows, Linux, etc.)
- CPU virtual, memória, disco e rede
- Capacidade de rodar aplicações como se fosse um computador físico

As VMs são amplamente utilizadas em **nuvens públicas**, como o Microsoft Azure, para hospedar aplicações, executar testes, criar ambientes de desenvolvimento e muito mais.

---

## 🆚 Diferença entre VM e Bare Metal

| Característica       | VM (Virtual Machine)                | Bare Metal (Servidor Físico)         |
|----------------------|-------------------------------------|--------------------------------------|
| **Virtualização**     | Sim                                | Não                                  |
| **Isolamento**        | Compartilha hardware com outras VMs| Hardware dedicado                    |
| **Performance**       | Boa, mas com overhead de virtualização | Máxima performance, sem overhead    |
| **Flexibilidade**     | Alta – pode criar e apagar rapidamente | Baixa – hardware fixo               |
| **Custo**             | Normalmente menor, modelo sob demanda | Maior custo inicial ou aluguel      |

**Resumo**:  
- **VMs** são ideais para flexibilidade, escalabilidade e custo-eficiência.  
- **Bare Metal** é melhor para workloads que exigem performance extrema ou controle total do hardware.

---

## 🛠️ Casos de Uso Comuns para VMs

- **Ambientes de desenvolvimento e teste**  
  → Criação rápida de máquinas para validar código ou experimentar novas tecnologias.

- **Hospedagem de aplicações e sites**  
  → Rodar servidores web, bancos de dados e APIs.

- **Ambientes de treinamento e aprendizado**  
  → Criar laboratórios virtuais para simulação de cenários.

- **Infraestrutura sob demanda**  
  → Escalar servidores conforme a demanda, sem precisar comprar hardware.

- **Execução de softwares legados**  
  → Rodar aplicações que exigem versões antigas de sistema operacional.

---

As máquinas virtuais são um pilar essencial da computação em nuvem moderna, oferecendo agilidade, escalabilidade e eficiência para empresas e desenvolvedores.

# 🧩 Principais Serviços do Microsoft Azure para Máquinas Virtuais

## 💻 Azure Virtual Machines

O serviço **Azure Virtual Machines** permite a criação de máquinas virtuais escaláveis e sob demanda, com diversos sistemas operacionais (Windows, Linux) e tamanhos de instância.

### Principais recursos:
- Escolha de imagem do sistema operacional (pré-definida ou personalizada)
- Tamanhos variados para diferentes necessidades (CPU, RAM, disco)
- Opções de alta disponibilidade e balanceamento de carga
- Integração com backup, monitoramento e segurança

As VMs são cobradas por hora de uso ou por segundo (dependendo do sistema), e podem ser pausadas quando não estiverem em uso para economia de custos.

---

## 📦 Azure Resource Groups

Um **Resource Group** (Grupo de Recursos) é um contêiner lógico que agrupa todos os recursos relacionados a uma aplicação ou projeto no Azure. Ele facilita a organização, gerenciamento e automação dos recursos.

### Por que usar?
- Agrupa VM, rede, disco, IP, etc. em um único local
- Permite aplicar políticas, permissões e tags em grupo
- Facilita a exclusão em massa (excluir o grupo = excluir tudo dentro)

**Exemplo**: Criar um grupo `projeto-web` com a VM, IP público, disco e rede associados.

---

## 🌐 Azure Networking: VNet e Subnet

### 🔷 Virtual Network (VNet)
A **VNet** é a rede privada no Azure que conecta suas VMs e outros recursos, similar a uma rede local tradicional.

### 🔹 Subnet
Dentro de uma VNet, você pode dividir em **Subnets** para organizar e isolar os recursos (por exemplo, separar banco de dados de aplicação).

### Benefícios:
- Controle de IPs internos e externos
- Regras de segurança com **NSG (Network Security Groups)**
- Comunicação segura entre VMs, com possibilidade de VPN ou conexão híbrida

---

## 💾 Azure Storage – Discos Gerenciados

As VMs do Azure utilizam **Discos Gerenciados** como armazenamento do sistema operacional e dados.

### Tipos de discos:
- **Standard HDD**: baixo custo, uso leve
- **Standard SSD**: bom desempenho, custo intermediário
- **Premium SSD**: alto desempenho, ideal para produção
- **Ultra Disk**: máxima performance para cargas críticas

### Vantagens:
- Redundância automática (LRS, ZRS)
- Snapshots para backup
- Criptografia integrada
- Redimensionamento flexível

---

Esses serviços são a base para criar, configurar e escalar máquinas virtuais no Azure com segurança, performance e organização.

# 🧱 Tipos de Máquinas Virtuais no Azure e Casos de Uso

O Microsoft Azure oferece diversas **famílias de VMs**, cada uma otimizada para diferentes cargas de trabalho. Escolher o tipo certo garante melhor desempenho e economia de custos.

---

## 🔠 Séries de VMs no Azure

### 🟦 Série B – Uso Geral e Econômico

**Características**:
- Ideal para cargas de trabalho com uso intermitente de CPU
- Acumula créditos de CPU para uso em picos

**Casos de uso**:
- Ambientes de desenvolvimento/teste
- Aplicações leves
- Servidores de baixo tráfego

---

### 🟨 Série D – Uso Geral (Desempenho balanceado)

**Características**:
- Equilíbrio entre CPU, memória e disco
- Boa performance para a maioria das aplicações

**Casos de uso**:
- Servidores de aplicação
- Sites corporativos
- APIs REST

---

### 🟥 Série E – Otimizada para Memória

**Características**:
- Proporção maior de memória por CPU
- Boa para processamento de dados e cache

**Casos de uso**:
- Bancos de dados em memória
- Serviços de cache (Redis, Memcached)
- Análise de dados com uso intensivo de RAM

---

### 🟩 Série F – Otimizada para Computação

**Características**:
- Alta performance de CPU por núcleo
- Menos memória comparado a outras séries

**Casos de uso**:
- Processamento de lote
- Simulações
- Compilação de código e renderizações

---

### ⚙️ Outras Séries Avançadas

- **Série L** – Otimizada para armazenamento (I/O intenso)
- **Série H** – Alto desempenho para computação científica (HPC)
- **Série N** – Otimizada para GPU (IA, renderização, machine learning)

---

## 📌 Dicas para Escolher a VM Certa

- Comece com a **série B** para testes e aprendizado
- Use **série D** para aplicações mais robustas
- Escolha **série E ou F** conforme a carga (memória ou CPU)
- Monitore o uso de recursos e ajuste o tamanho conforme necessário

---

Selecionar o tipo ideal de VM é uma etapa crucial para garantir **desempenho, estabilidade e economia** em seus projetos no Azure.

# 🛠️ Passo a Passo: Criando uma Máquina Virtual no Azure

Este guia mostra como criar uma máquina virtual no Microsoft Azure utilizando o portal web. Ideal para quem está começando a explorar a nuvem!

---

## 🔑 Pré-requisitos

- Conta no [Microsoft Azure](https://portal.azure.com)
- Acesso ao portal Azure
- Assinatura ativa (pode usar o crédito gratuito de R$ 1.000 da conta gratuita)

---

## 📌 Etapas para Criar a VM

### 1. Acesse o portal Azure

👉 Vá para [portal.azure.com](https://portal.azure.com) e faça login.

---

### 2. Crie um **Resource Group**

- No menu lateral, clique em **"Grupos de recursos"**
- Clique em **“Criar”**
- Nomeie o grupo (ex: `lab-vm-grupo`)
- Escolha a região (ex: `Brazil South` ou `East US`)
- Clique em **“Revisar + Criar”** e depois em **“Criar”**

---

### 3. Crie a Máquina Virtual

- No menu lateral, clique em **"Máquinas virtuais"**
- Clique em **“Criar” → “Máquina virtual do Azure”**

#### Aba: **Básico**
- **Assinatura**: escolha sua assinatura ativa
- **Grupo de Recursos**: selecione o grupo que criou
- **Nome da VM**: ex: `lab-vm`
- **Região**: mesma do grupo
- **Imagem**: escolha o SO (ex: Ubuntu 20.04 LTS ou Windows Server)
- **Tamanho**: selecione um básico (ex: `B1s`)
- **Usuário admin**: defina um nome de usuário e senha ou chave SSH
- Clique em **“Próximo”** até a aba "Revisar + Criar"

---

#### Aba: **Rede**
- Deixe o padrão ou personalize a rede virtual e a subnet
- Certifique-se de que a opção "IP público" esteja **ativada**
- Ative a porta de acesso remoto:
  - Para Linux: porta **22 (SSH)**
  - Para Windows: porta **3389 (RDP)**

---

### 4. Finalize a criação

- Clique em **“Revisar + Criar”**
- Verifique se todas as configurações estão corretas
- Clique em **“Criar”**
- Aguarde alguns minutos enquanto o Azure provisiona a VM

---

## 🌐 Acesse a VM

- Após criada, vá até **"Máquinas Virtuais"** no menu
- Clique na sua VM → **"Conectar"**
- Escolha o tipo de conexão:
  - **SSH** (Linux)
  - **RDP** (Windows)

Siga as instruções fornecidas para conectar usando terminal (Linux) ou o aplicativo de Conexão de Área de Trabalho Remota (Windows).

---

## 🧹 Dica importante: Economize créditos!

Ao terminar os testes, você pode:
- **Parar (Deallocated)** a VM para não ser cobrado
- Ou **excluir** o resource group para apagar tudo de uma vez

---

## 🖼️ Imagens de configuração da VM

- Configuração básica da VM
  https://1drv.ms/i/c/944d146266640393/EdCjJ8mnhrNPqHAniXTIgpIBEPXlFOY598k2HCHGCVaDrA?e=f3ExpQ
  https://1drv.ms/i/c/944d146266640393/ES_7xKzjwyZEuhIYAb2jbjAB5h-D9NFgfgGQMv8jhz1L9Q?e=B3BYz5
  https://1drv.ms/i/c/944d146266640393/EVPRqi3qeE9Klry_QAcVxSIBgSlZwpRIPSwzV2GLHADZlA?e=fz0HOg
- Aba Discos
  https://1drv.ms/i/c/944d146266640393/EW3_849P6jJAryVg8K8-g1IB1FbMyWnQkzoPPnuFFv6PwQ?e=ucS0oh
- Aba Gerenciamento
  https://1drv.ms/i/c/944d146266640393/EWtL4DX70g5Hp2HBsWkQjgYBgnO0JBBVetF4Pulyi--oXg?e=J2LPaP
- Aba Revisão
  [https://1drv.ms/i/c/944d146266640393/EWtL4DX70g5Hp2HBsWkQjgYBgnO0JBBVetF4Pulyi--oXg?e=J2LPaP](https://1drv.ms/i/c/944d146266640393/EU6R-sNKWcdMptqwQM4UgkgB2hjk8cmvTb2Pjpk8E44MWQ?e=G9wm0X)
- Implatação em Andamento
  https://1drv.ms/i/c/944d146266640393/EWkB1X12mKFPl9G5z_mPcKEB83-W6e8ky4qZDqCC7UIoBA?e=ENX3dL
- VM Criada
  https://1drv.ms/i/c/944d146266640393/ESorBfwojW1LjZNjrMRVWYEBdbphPg9ypPGgazoGduePFg?e=KUP0j1




