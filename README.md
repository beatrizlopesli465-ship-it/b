
# AccessHub - Sistema de Gerenciamento de Acesso e Usuários

Um sistema web robusto para gerenciamento de usuários com controle de acesso baseado em níveis de permissão (Administrador, Gerente e Usuário). Ideal para organizações que precisam manter controle seguro sobre quem acessa o sistema e quais funcionalidades cada usuário pode utilizar.

## 🎯 Características Principais

- **Autenticação Segura**: Login com criptografia MD5
- **Controle de Acesso em Três Níveis**:
  - **Administrador (Nível 1)**: Acesso total ao sistema, pode gerenciar usuários e permissões
  - **Gerente (Nível 2)**: Acesso intermediário, pode adicionar usuários básicos
  - **Usuário (Nível 3)**: Acesso limitado, apenas funcionalidades básicas
- **Gerenciamento de Usuários**: Adicionar, alterar dados e gerenciar senhas
- **Pesquisa de CNPJ**: Integração para consulta de dados de empresas
- **Registro de Alterações**: Log completo de todas as alterações de acesso
- **Painel Personalizado**: Interface adaptada conforme o nível de acesso do usuário

## 📋 Funcionalidades

### Para Administradores
- Adicionar novos usuários
- Mudar nível de acesso de usuários
- Alterar dados cadastrais
- Pesquisar informações de CNPJ

### Para Gerentes
- Adicionar usuários básicos (nível 3)
- Alterar dados cadastrais
- Pesquisar informações de CNPJ

### Para Usuários
- Alterar seus dados cadastrais
- Pesquisar informações de CNPJ

## 🗄️ Estrutura do Banco de Dados

### Tabelas Principais

**usuario**
```
- nome (VARCHAR)
- cpf (VARCHAR) - Chave primária
- telefone (VARCHAR)
```

**nivel**
\`\`\`
- id (INT) - Chave primária
- descricao (VARCHAR)
\`\`\`

**login**
\`\`\`
- id (INT) - Chave primária
- cpf (VARCHAR) - FK usuario
- login (VARCHAR)
- senha (VARCHAR) - Criptografada
- nivel (INT) - FK nivel
\`\`\`

**LOG**
\`\`\`
- id (INT) - Chave primária
- cpf (VARCHAR) - FK usuario
- cpf_alterado (VARCHAR) - FK usuario
- DATA (TIMESTAMP)
- nivel_novo (INT) - FK nivel
\`\`\`

## 🚀 Como Começar

### Pré-requisitos
- Servidor com PHP 5.6+
- MySQL 5.7+
- Servidor web (Apache, Nginx, etc.)

### Instalação

1. **Clonar ou extrair o projeto**
\`\`\`bash
# Se estiver em um ZIP
unzip AccessHub.zip
cd AccessHub
\`\`\`

2. **Criar o banco de dados**
   - Abra seu cliente MySQL
   - Execute os comandos do arquivo `Banco de dados` para criar as tabelas e inserts iniciais

3. **Configurar a conexão com banco de dados**
   - Abra o arquivo `conexao.php`
   - Atualize as credenciais (host, usuário, senha, banco de dados):
   \`\`\`php
   $conexao = mysqli_connect('localhost', 'seu_usuario', 'sua_senha', 'seguranca_2', '3306');
   \`\`\`

4. **Acessar a aplicação**
   - Coloque os arquivos na raiz do servidor web
   - Acesse `http://localhost/index.php` no navegador

### Credenciais de Teste

**Admin**
- Login: `admin`
- Senha: `admin`

**Gerente**
- Login: `gerente`
- Senha: `gerente`

## 📁 Estrutura de Arquivos

\`\`\`
AccessHub/
├── index.php                    # Página de login
├── login.php                    # Processamento de autenticação
├── logout.php                   # Saída do sistema
├── principal.php                # Dashboard principal
├── conexao.php                  # Configuração de banco de dados
├── funcoes.php                  # Funções utilitárias
├── addusuario.php              # Adicionar novo usuário
├── alterardados.php            # Editar dados do usuário
├── alterarsenha.php            # Alterar senha
├── mudaracesso.php             # Mudar nível de acesso (Admin)
├── mudartipo.php               # Mudar tipo de usuário
├── pesquisarcnpj.php           # Pesquisar CNPJ
├── chamausuario.php            # Chamar dados do usuário
├── autenticarcnpj.php          # Autenticar CNPJ
├── aviso.php                   # Página de avisos
├── validalogin.php             # Validar sessão de login
├── validaradmin.php            # Validar acesso admin
├── validaradmingerente.php     # Validar acesso admin/gerente
├── validaadmin.php             # Verificar admin
├── validaadmingerente.php      # Verificar admin/gerente
├── Banco de dados              # Script SQL para criar o banco
└── LICENSE                     # Licença do projeto
\`\`\`

## 🔒 Segurança

- Senhas são criptografadas usando MD5
- Sistema de sessão para manter usuários autenticados
- Controle de acesso baseado em níveis
- Log de todas as alterações de permissão

**Nota Importante**: MD5 é considerado obsoleto para novos projetos. Para produção, recomenda-se migrar para `password_hash()` e `password_verify()`.

## 🛠️ Tecnologias Utilizadas

- **Backend**: PHP
- **Banco de Dados**: MySQL
- **Frontend**: HTML, CSS
- **Autenticação**: Sessões PHP

## 📝 Fluxo Principal

1. Usuário acessa `index.php`
2. Insere credenciais (login e senha)
3. Sistema valida as credenciais via `login.php`
4. Se válido, cria sessão e redireciona para `principal.php`
5. Painel se adapta conforme nível de acesso
6. Usuário acessa funcionalidades de acordo com permissão
7. Logout encerra a sessão

## 🤝 Contribuindo

Para melhorias ou correções, sinta-se livre para contribuir com pull requests.

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 📞 Suporte

Para dúvidas ou problemas, entre em contato com o desenvolvedor ou abra uma issue no repositório.

---

**Versão**: 1.0.0  
**Última atualização**: Novembro 2025
