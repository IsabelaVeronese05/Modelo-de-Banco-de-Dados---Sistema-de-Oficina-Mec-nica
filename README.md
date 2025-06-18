## Modelo de Banco de Dados - Sistema de Oficina Mecânica

Este projeto apresenta um modelo relacional de banco de dados para um sistema de **ordens de serviço em uma oficina mecânica**, com funcionalidades de cadastro de clientes, veículos, peças, serviços, equipes técnicas, autorizações e controle de execução.

---

## 📌 Objetivo

Desenvolver uma estrutura de banco de dados clara e funcional que permita:

- Gerenciar ordens de serviço com controle por status.
- Cadastrar veículos e seus proprietários.
- Gerenciar peças e serviços aplicados em cada análise técnica.
- Acompanhar a execução por equipes de mecânicos.
- Registrar autorizações de clientes e entregas realizadas.

---

## 🗺️ Diagrama Entidade-Relacionamento (DER)

![Captura de Tela (41)](https://github.com/user-attachments/assets/3a69e902-a38e-4e7c-bdb6-9bdea8176cd8)

---

## 🗂️ Descrição das Tabelas

### Cliente
- Cadastro de clientes da oficina.
- Inclui CPF, telefone, e-mail e endereço.

### Veículo
- Dados de veículos vinculados aos clientes.
- Inclui marca, modelo, placa e tipo.

### Ordem_de_Serviço
- Ordem de execução de reparos.
- Contém datas, valor da mão de obra e status da ordem.

### Analise_OS
- Etapas de análise técnica realizadas em uma ordem.
- Associadas a peças e serviços recomendados.

### Serviço
- Catálogo de serviços oferecidos pela oficina.

### Peça
- Peças disponíveis no estoque.
- Inclui valor, marca e descrição.

### Itens_Serviço e Itens_Peças
- Tabelas intermediárias que registram os itens utilizados em cada análise.

### Mecânico
- Profissionais da oficina.
- Contém nome, telefone e localização.

### Equipe_de_Mecânicos
- Agrupamento de mecânicos que atuam em determinada análise.

### Autorização
- Registra se o cliente autorizou a execução de um orçamento.

### Entrega
- Confirmação da entrega do veículo após o serviço.

---

## 🔗 Relacionamentos

- Cliente → Veículo: 1:N  
- Veículo → Ordem_de_Serviço: 1:N  
- Ordem_de_Serviço → Analise_OS: 1:N  
- Analise_OS → Itens_Serviço: 1:N  
- Analise_OS → Itens_Peças: 1:N  
- Itens_Serviço → Serviço: N:1  
- Itens_Peças → Peça: N:1  
- Analise_OS → Equipe_de_Mecânicos: N:1  
- Equipe_de_Mecânicos → Mecânico: N:M  
- Ordem_de_Serviço → Autorização: 1:1  
- Ordem_de_Serviço → Entrega: 1:1  

---

## 💾 Tecnologias e SGBD

- Modelado para uso com: **MySQL**.
- Ferramentas recomendadas: MySQL Workbench, DBeaver, phpMyAdmin.

---

## 📈 Exemplos de Consultas

- Buscar todas as ordens de um cliente.
- Verificar quais peças foram usadas em uma OS.
- Consultar o status atual de uma ordem.
- Listar serviços realizados por uma equipe.
- Verificar autorizações pendentes.

*(Consultas podem ser adicionadas em `sql/exemplo_consultas.sql`)*

---
## ✨ Autor

- Isabela Veronese 
- [LinkedIn](https://www.linkedin.com/in/isabela-veronese-11058a260)
