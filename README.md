# Manutenção de PCs

# 🖥️ Sistema de Gerenciamento de Manutenção de PCs

O Sistema de Gerenciamento de Manutenção de PCs é uma aplicação desenvolvida para auxiliar no controle, registro e acompanhamento de manutenções realizadas em computadores.
O sistema permite gerenciar equipamentos, ordens de serviço, clientes e técnicos, proporcionando maior organização, rastreabilidade e eficiência operacional.

# 📌 Descrição

Este projeto tem como objetivo auxiliar técnicos e empresas de TI no controle de manutenções de computadores, permitindo:

- Cadastro de clientes  
- Registro de equipamentos  
- Abertura e acompanhamento de ordens de serviço  
- Histórico completo de manutenções  
- Controle de status (em andamento, concluído, aguardando peças, etc.)

---

# 🚀 Funcionalidades

- 👤 Cadastro de clientes  
- 💻 Cadastro de computadores/dispositivos  
- 🛠️ Registro de manutenção  
- 📊 Acompanhamento de status  
- 📝 Histórico de serviços realizados  
- 🔍 Busca e filtragem de registros  

---

# 🛠️ Tecnologias Utilizadas

*(Edite conforme seu projeto)*

- JavaScript / TypeScript  
- Node.js  
- Express  
- React / Vue / Angular  
- MongoDB / MySQL / PostgreSQL  


# ⚙️ Funcionalidades
👤 Gestão de Clientes
Cadastro de clientes
Edição e exclusão
Consulta de histórico

# 💻 Gestão de Equipamentos
Cadastro de PCs/notebooks
Informações técnicas (processador, RAM, etc.)
Associação com cliente

# 🧾 Ordens de Serviço
Abertura de OS
Descrição do problema
Definição de técnico responsável
Atualização de status:
Em análise
Em manutenção
Finalizado

# 🔧 Controle de Manutenção
Registro de serviços realizados
Peças utilizadas
Custos envolvidos

# 📊 Relatórios
Histórico por cliente
Equipamentos atendidos
Serviços realizados

# 🧱 Estrutura do Projeto
📁 projeto-manutencao-pcs
│
├── 📁 frontend
│   ├── index.html
│   ├── style.css
│   └── app.js
│
├── 📁 backend
│   ├── server.js / app.py
│   ├── routes/
│   └── controllers/
│
├── 📁 database
│   └── schema.sql
│
├── README.md
└── package.json / requirements.txt

# Api Sistema De Manutenção De Pcs
API completa funcional já inclui:
CRUD de clientes
Equipamentos
Técnicos
Ordens de serviço
Banco automático

## 1. Instalar dependências
npm init -y
npm install express sqlite3 body-parser

## 2. Rodar a API
node index.js

## 3. 🔥 Testar (Postman ou Insomnia)
Criar cliente
POST /clientes
{
  "nome": "João",
  "telefone": "99999999",
  "email": "joao@email.com"
}

## 4. Criar equipamento
POST /equipamentos
{
  "tipo": "Notebook",
  "marca": "Dell",
  "modelo": "Inspiron",
  "cliente_id": 1
}

## 5. Criar ordem
POST /ordens
{
  "data_abertura": "2026-04-14",
  "status": "Em análise",
  "equipamento_id": 1,
  "tecnico_id": 1
}

# Api Sistema De Manutenção De Pcs (node· javascript
## // ===============================
    [tipo, marca, modelo, cliente_id],
    function (err) {
      if (err) return res.status(500).json(err);
      res.json({ id: this.lastID });
    }
  );
});

 app.get('/equipamentos', (req, res) => {
  db.all(`SELECT * FROM equipamentos`, [], (err, rows) => {
    if (err) return res.status(500).json(err);
    res.json(rows);
  });
});


// ===============================
// ROTAS - TECNICOS
// ===============================


 app.post('/tecnicos', (req, res) => {
  const { nome, especialidade } = req.body;
  db.run(
    `INSERT INTO tecnicos (nome, especialidade) VALUES (?, ?)`,
    [nome, especialidade],
    function (err) {
      if (err) return res.status(500).json(err);
      res.json({ id: this.lastID });
    }
  );
});


 app.get('/tecnicos', (req, res) => {
  db.all(`SELECT * FROM tecnicos`, [], (err, rows) => {
    if (err) return res.status(500).json(err);
    res.json(rows);
  });
});


// ===============================
// ROTAS - ORDENS DE SERVIÇO
// ===============================


 app.post('/ordens', (req, res) => {
  const { data_abertura, status, equipamento_id, tecnico_id } = req.body;
  db.run(
    `INSERT INTO ordens (data_abertura, status, equipamento_id, tecnico_id)
     VALUES (?, ?, ?, ?)`,
    [data_abertura, status, equipamento_id, tecnico_id],
    function (err) {
      if (err) return res.status(500).json(err);
      res.json({ id: this.lastID });
    }
  );
});


 app.get('/ordens', (req, res) => {
  db.all(`SELECT * FROM ordens`, [], (err, rows) => {
    if (err) return res.status(500).json(err);
    res.json(rows);
  });
});


 app.put('/ordens/:id', (req, res) => {
  const { status } = req.body;
  db.run(
    `UPDATE ordens SET status = ? WHERE id = ?`,
    [status, req.params.id],
    function (err) {
      if (err) return res.status(500).json(err);
      res.json({ updated: this.changes });
    }
  );
});


// ===============================
// INICIAR SERVIDOR
// ===============================


const PORT = 3000;
app.listen(PORT, () => {
  console.log(`Servidor rodando em http://localhost:${PORT}`);
});



# 🗄️ Modelagem do Banco de Dados
Principais entidades:
Clientes
Equipamentos
Ordens de Serviço
Técnicos
Serviços
Exemplo simplificado:

CLIENTE (id, nome, telefone, email)
EQUIPAMENTO (id, tipo, marca, modelo, cliente_id)
ORDEM_SERVICO (id, data_abertura, status, equipamento_id, tecnico_id)
SERVICO (id, descricao, custo, ordem_id)
TECNICO (id, nome, especialidade)

# 🚀 Como Executar o Projeto
1. Clonar o repositório
git clone https://github.com/seu-usuario/seu-repositorio.git

3. Acessar a pasta
cd projeto-manutencao-pcs
4. Instalar dependências
npm install ou
pip install -r requirements.txt

5. Configurar banco de dados
Criar banco
Executar script schema.sql

6. Executar o sistema
npm start ou
python app.py

# 🔄 Fluxo do Sistema
Cadastro do cliente
Cadastro do equipamento
Abertura da ordem de serviço
Diagnóstico do problema
Execução da manutenção
Finalização e registro histórico

# 🧪 Testes
Testes manuais via interface
Testes de API (Postman / Insomnia)
Testes unitários (opcional)

# 📈 Melhorias Futuras
Autenticação de usuários (login)
Dashboard com gráficos
Integração com API de peças
Notificações por e-mail
Sistema mobile

# 👨‍💻 Contribuição
Contribuições são bem-vindas!
Fork o projeto
Crie uma branch
git checkout -b minha-feature
Commit suas alterações
Push
Abra um Pull Request

# 📄 Licença
Este projeto está sob a licença MIT.


# 📞 Contato
Caso tenha dúvidas ou sugestões:
Email: seuemail@email.com
GitHub: seu-usuario
