# Gerenciador de Usuários

Sistema simples de gerenciamento de usuários desenvolvido em **PHP**, permitindo **cadastro**, **login**, **listagem**, **alteração de senha** e **logout**.
Ideal para estudos, trabalhos acadêmicos ou como base para projetos maiores.

---

##  Estrutura do Projeto

```
Sistema_Cadastro-main/
│── LICENSE
│── alterarsenha.php
│── cadastrar.php
│── cadastro.php
│── conexao.php
│── index.php
│── lista.php
│── logado.php
│── login.php
│── logout.php
│── senhaatualizada.php
│── banco de dados/
```

---

##  Funcionalidades

* Cadastro de novos usuários
* Login com autenticação
* Página protegida para usuários logados
* Listagem de usuários
* Alteração de senha
* Logout
* Conexão com banco de dados MySQL

---

##  Tecnologias Usadas

* **PHP**
* **MySQL**
* **HTML/CSS**
* **Sessions**

---

##  Como Executar

1. Instale **XAMPP** ou **WAMP**
2. Coloque o projeto dentro da pasta:

```
htdocs/
```

3. Inicie **Apache** e **MySQL**
4. Acesse no navegador:

```
http://localhost/Sistema_Cadastro-main/index.php
```

---

##  Banco de Dados (Exemplo)

```sql
CREATE DATABASE sistema_cadastro;

CREATE TABLE usuarios (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nome VARCHAR(255) NOT NULL,
  email VARCHAR(255) UNIQUE NOT NULL,
  senha VARCHAR(255) NOT NULL
);
```

Configure as credenciais no arquivo:

```
conexao.php
```

---

## 📄 Licença – GPL-2.0

Este projeto é distribuído sob a **GNU General Public License v2.0 (GPL-2.0)**.
Consulte o arquivo `LICENSE` para mais detalhes.
