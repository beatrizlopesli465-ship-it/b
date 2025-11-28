# UserAccess Manager

Um sistema simples de gerenciamento de usuários, permitindo **cadastro**, **login**, **alteração de senha** e **logout**. Ideal para estudos ou como base para aplicações maiores em PHP.

---

## 🚀 Funcionalidades

* Cadastro de novos usuários
* Login e autenticação
* Alteração de senha
* Logout seguro
* Estrutura simples para expansão

---

## 📂 Estrutura de Arquivos

```
/Sistema_Cadastro-main
│── login.php
│── logout.php
│── alterarSenha.php
│── senhaAtualizada.php
│── LICENSE
```

*(A lista pode variar conforme seus arquivos.)*

---

## 🛠️ Tecnologias Utilizadas

* **PHP**
* **HTML/CSS**
* **MySQL** (se estiver usando banco de dados)
* **Sessions** para autenticação

---

## ▶️ Como rodar o projeto

1. Instale o **XAMPP** ou **WAMP**
2. Coloque o projeto dentro da pasta:

```
htdocs/
```

3. Inicie **Apache** e **MySQL**
4. Acesse no navegador:

```
http://localhost/Sistema_Cadastro-main/login.php
```

---

## 🧩 Configuração do Banco (opcional)

Caso use banco de dados:

```sql
CREATE DATABASE sistema_cadastro;

CREATE TABLE usuarios (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nome VARCHAR(255),
  email VARCHAR(255) UNIQUE,
  senha VARCHAR(255)
);
```

Atualize as credenciais no arquivo de conexão conforme necessário.

---

## 📄 Licença

Este projeto está licenciado sob a licença MIT.
