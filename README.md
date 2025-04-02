# 📦 Sistema de Rastreamento de Pacotes de Entrega  

**Um sistema completo para gerenciar pacotes, remetentes, destinatários e entregadores com PostgreSQL e PGAdmin.**  

---

## ✨ Funcionalidades  

✅ **Cadastro de Pacotes**  
- Número de rastreamento único.  
- Detalhes do conteúdo e destino.  

✅ **Gerenciamento de Remetentes e Destinatários**  
- Informações de contato e endereço.  

✅ **Controle de Entregadores**  
- Registro de veículos e dados de identificação.  

✅ **Consultas Eficientes**  
- Relacionamento entre pacotes, remetentes e destinatários.  

---

## 🛠️ Tecnologias  

- **Banco de Dados**: PostgreSQL  
- **Ferramenta de Administração**: PGAdmin  
- **Linguagem**: SQL  

---

## 📋 Estrutura do Banco de Dados  

### **Tabelas Principais**  

| Tabela          | Descrição                          |
|-----------------|-----------------------------------|
| `remetentes`    | Armazena dados dos remetentes.    |
| `destinatarios` | Armazena dados dos destinatários. |
| `entregadores`  | Gerencia entregadores e veículos. |
| `pacotes`       | Rastreia pacotes com chaves estrangeiras. |

---

## 🚀 Como Usar  

### **1. Pré-requisitos**  
- PostgreSQL instalado.  
- PGAdmin configurado.  

### **2. Configuração do Banco de Dados**  

```sql
-- Criação da tabela 'remetentes'
CREATE TABLE remetentes (
    remetente_id SERIAL PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    contato VARCHAR(50) NOT NULL,
    endereco TEXT NOT NULL
);
```

*(Consulte o arquivo [schema.sql](link-para-schema.sql) para o SQL completo.)*  

### **3. Inserindo Dados**  

```sql
-- Exemplo: Inserir um remetente
INSERT INTO remetentes (nome, contato, endereco)
VALUES ('Loja Tech', 'contato@lojatech.com', 'Av. Principal, 100');
```

### **4. Consultando Pacotes**  

```sql
-- Listar pacotes com detalhes de remetente e destinatário
SELECT p.numero_rastreamento, r.nome AS remetente, d.nome AS destinatario
FROM pacotes p
JOIN remetentes r ON p.remetente_id = r.remetente_id
JOIN destinatarios d ON p.destinatario_id = d.destinatario_id;
```

---

## 📌 Exemplo de Saída  

| numero_rastreamento | remetente  | destinatario |  
|---------------------|------------|--------------|  
| `BR123456789`       | Loja Tech  | João Silva   |  

---

## 📂 Estrutura do Projeto  

```
📁 sistema-rastreamento/
├── 📄 schema.sql          # Script SQL para criação das tabelas
├── 📄 inserts.sql         # Exemplos de inserção de dados
├── 📄 queries.sql         # Consultas úteis
└── 📄 README.md           # Este arquivo
```

---

**⭐️ Deixe uma estrela se gostou do projeto!** ⭐️  

📢 **Pronto para usar! Clone o repositório e comece a explorar.** 🚀
