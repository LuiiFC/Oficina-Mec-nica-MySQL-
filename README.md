# Oficina-Mecanica-MySQL-

🛠️ Sistema de Banco de Dados – Oficina Mecânica

Este repositório contém o projeto de modelagem e implementação do banco de dados para uma Oficina Mecânica. O objetivo é criar um sistema estruturado e funcional para gerenciamento de funcionários, departamentos, vendas, dependentes, formas de pagamento, combustíveis, bombas, volumes abastecidos e outros dados operacionais.

O projeto foi desenvolvido utilizando MySQL e modelado no MySQL Workbench.

📌 📊 Diagrama Entidade–Relacionamento (DER)
💡 Modelo Lógico

O modelo foi construído para contemplar todas as operações essenciais de uma oficina:

Cadastro de empregados, departamentos e endereços

Controle de dependentes dos empregados

Registro de telefones

Sistema de vendas e itens vendidos

Controle de bombas de combustível e abastecimentos

Registro de combustíveis e volumes abastecidos

Métodos de pagamento

📷 Diagrama completo:
(coloque aqui a imagem do seu DER inserida no GitHub)

🗂️ Descrição das Tabelas

A seguir uma visão geral das tabelas criadas no banco:

👨‍🔧 Empregado

Armazena os dados dos funcionários da oficina.

Campo	Tipo	Descrição
CPF	CHAR(11)	Chave primária do empregado
Nome	VARCHAR(100)	Nome completo
Sexo	ENUM('M','F')	Gênero
Salario	DECIMAL(10,2)	Salário do empregado
idDepartamento	INT	FK → Departamento
Endereco_CPF_Empregado	CHAR(11)	FK → Endereço
🏢 Departamento
Campo	Tipo	Descrição
idDepartamento	INT	PK
Nome	VARCHAR(45)	Nome do setor
Email	VARCHAR(100)	Contato oficial
Descrição	VARCHAR(200)	Função do departamento
Local	VARCHAR(100)	Localização
CPF_Gerente	CHAR(11)	FK → Empregado
Empregado_CPF	CHAR(11)	FK auxiliar
🏠 Endereço
Campo	Tipo
CPF_Empregado	CHAR(11) PK/FK
Cidade	VARCHAR(45)
Bairro	VARCHAR(45)
Rua	VARCHAR(45)
Numero	INT
Complemento	VARCHAR(45)
CEP	VARCHAR(9)
☎️ Telefone
Campo	Tipo
idTelefone	INT PK
Numero	VARCHAR(15)
Empregado_CPF	CHAR(11) FK
👨‍👩‍👧 Dependente
Campo	Tipo
idDependente	INT PK
Nome	VARCHAR(100)
DataNasc	DATE
Parentesco	VARCHAR(30)
CPF_Empregado	CHAR(11) FK
⛽ Combustíveis
Campo	Tipo
idCombustiveis	INT PK
Combustivel	VARCHAR(45)
BombComb_idBomba	INT FK
🛢️ BombComb (Bombas)
Campo	Tipo
idBomba	INT PK
DataAbastecimento	DATE
idVenda	INT FK
📦 Volume
Campo	Tipo
idVolume	INT PK
BombComb_idBomba	INT FK
🧾 Vendas
Campo	Tipo
idVendas	INT PK
Data	DATE
ValorTotal	DECIMAL(10,2)
FormPag	ENUM(...)
CPF_Empregado	CHAR(11) FK
BombComb_idBomba	INT FK
🛒 ItensVenda
Campo	Tipo
idItem	INT PK
Nome	VARCHAR(100)
Quantidade	INT
Valor	DECIMAL(10,2)
idVenda	INT FK
💳 FormaPag
Campo	Tipo
idFormaPag	INT PK
Cartao	VARCHAR(40)
Pix	FLOAT
Dinheiro	FLOAT
🧱 Regras de Integridade (Foreign Keys)

Algumas relações importantes:

Empregado → Departamento

Empregado → Endereço

Telefone → Empregado

Dependente → Empregado

Vendas → Empregado

Vendas → BombComb

ItensVenda → Vendas

Combustíveis → BombComb

Volume → BombComb

🚀 Tecnologias Utilizadas

MySQL Community Server 8.x

MySQL Workbench

Modelo Relacional

DER + DDL + DML

📚 Objetivo Educacional

Este projeto foi desenvolvido como atividade prática para modelar e implementar um banco de dados relacional completo de um sistema de Oficina Mecânica, atendendo requisitos de normalização, integridade e relacionamento entre entidades.
