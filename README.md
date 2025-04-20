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

