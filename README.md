# 💰 Sistema Bancário com Context Manager e POO em Python  

Este é um **mini projeto de sistema bancário** desenvolvido para praticar **Programação Orientada a Objetos (POO)** em Python. O projeto implementa um banco simples onde clientes podem ter contas (corrente ou poupança) e realizar operações como **saques e depósitos**, seguindo boas práticas de encapsulamento e abstração.  

---

## 📌 Funcionalidades
✅ Criar clientes com nome e idade
✅ Criar contas bancárias (Corrente ou Poupança)
✅ Realizar saques e depósitos
✅ Aplicar limite extra em contas correntes
✅ Autenticar cliente e conta antes de permitir transações

---

## 🚀 Tecnologias e conceitos aplicados  

- **Programação Orientada a Objetos (POO)**  
- **Herança, encapsulamento e polimorfismo**  
- **Classes abstratas e métodos abstratos**  
- **Agregação entre classes (Cliente ↔ Conta ↔ Banco)**  
- **Autenticação de clientes e contas no banco**  
- **Uso de Context Manager para gerenciamento de recursos**  

---

## 📁 Estrutura do Projeto  
📂 context_manager_com_classes 
│── 📄 main.py # Arquivo principal para execução do sistema 
│── 📄 banco.py # Classe Banco, responsável por autenticar clientes e contas 
│── 📄 contas.py # Classes Conta, ContaPoupanca e ContaCorrente 
│── 📄 pessoas.py # Classes Pessoa e Cliente 
│── 📄 README.md # Documentação do projeto

---

## 🛠 Como executar o projeto  

1️⃣ **Clone o repositório:**  
```bash
git clone https://github.com/brunabbelini/context_manager_com_classes.git
```

2️⃣ Navegue até o diretório do projeto:
cd context_manager_com_classes

3️⃣ Execute o arquivo main.py:
python main.py

---

## 🎯 Exemplo de Uso
from banco import Banco
from pessoas import Cliente
from contas import ContaCorrente, ContaPoupanca

# Criando clientes
cliente1 = Cliente("Alice", 25)
cliente2 = Cliente("Bob", 30)

# Criando contas
conta1 = ContaCorrente(1001, 56789, saldo=500, limite=200)
conta2 = ContaPoupanca(1002, 98765, saldo=1000)

# Associando contas aos clientes
cliente1.conta = conta1
cliente2.conta = conta2

# Criando o banco e adicionando clientes e contas
banco = Banco([1001, 1002], [cliente1, cliente2], [conta1, conta2])

# Autenticando cliente e realizando operações
if banco.autenticar(cliente1, conta1):
    conta1.depositar(200)
    conta1.sacar(600)

if banco.autenticar(cliente2, conta2):
    conta2.sacar(500)


---

## 📜 Licença
Este projeto está sob a licença MIT. Sinta-se à vontade para explorar e contribuir! 😊

