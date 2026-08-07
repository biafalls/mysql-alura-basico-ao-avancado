# 📚 SQL com MySQL: manipule e consulte dados

## 📖 Sobre o curso

Este repositório reúne minhas anotações e os principais conceitos aprendidos durante o curso **SQL com MySQL: manipule e consulte dados**, da Alura.

Ao longo do curso, aprendi desde a criação de bancos de dados e tabelas até a manipulação e consulta de informações utilizando a linguagem SQL, desenvolvendo uma base sólida para trabalhar com bancos de dados relacionais utilizando o MySQL.

---

## 🎯 Objetivos do curso

- Compreender a história e os fundamentos da linguagem SQL.
- Conhecer as principais características do MySQL.
- Aprender a utilizar o MySQL Workbench.
- Criar e administrar bancos de dados.
- Criar, alterar e excluir tabelas.
- Manipular registros utilizando comandos SQL.
- Realizar consultas e filtros em bancos de dados.

---

# 📚 Conteúdo estudado

## 🗄️ Introdução ao SQL e ao MySQL

- História da linguagem SQL.
- Conceitos de bancos de dados relacionais.
- História e características do MySQL.
- Instalação do MySQL Server.
- Instalação do MySQL Workbench.
- Navegação pelo ambiente do Workbench.

---

## 🏗️ Criação de Bancos de Dados

Aprendi a:

- Criar bancos de dados utilizando scripts SQL.
- Criar bancos de dados pelo assistente gráfico.
- Excluir bancos de dados.
- Acessar bancos de dados existentes.

### Principais comandos

```sql
CREATE DATABASE nome_banco;

DROP DATABASE nome_banco;

USE nome_banco;
```

---

## 📦 Criação de Tabelas

Durante o curso aprendi:

- Os principais tipos de dados do MySQL.
- Como definir colunas.
- Como criar tabelas.
- Como excluir tabelas.

### Exemplo

```sql
CREATE TABLE clientes (
    id INT,
    nome VARCHAR(100),
    idade INT,
    data_cadastro DATE,
    ativo BOOLEAN
);
```

---

## 🔑 Chaves Primárias

Foi apresentado o conceito de **Primary Key**, responsável por identificar exclusivamente cada registro de uma tabela.

Exemplo:

```sql
CREATE TABLE produtos (
    id INT PRIMARY KEY,
    nome VARCHAR(100)
);
```

Também foi mostrado o cuidado necessário ao definir uma chave primária para evitar registros duplicados.

---

# ✏️ Manipulação de Dados (DML)

Aprendi os principais comandos para manipular registros.

## Inserindo dados

```sql
INSERT INTO clientes
VALUES (1, 'Beatriz', 20, '2026-08-07', TRUE);
```

---

## Atualizando dados

```sql
UPDATE clientes
SET nome = 'Beatriz Lima'
WHERE id = 1;
```

---

## Excluindo registros

```sql
DELETE FROM clientes
WHERE id = 1;
```

---

# 🔎 Consultando Dados

O curso apresentou diversas formas de realizar consultas.

## Selecionando todos os registros

```sql
SELECT * FROM clientes;
```

---

## Selecionando colunas específicas

```sql
SELECT nome, idade
FROM clientes;
```

---

## Filtrando informações

### Igualdade

```sql
SELECT *
FROM clientes
WHERE nome = 'Beatriz';
```

---

### Maior e menor

```sql
SELECT *
FROM clientes
WHERE idade >= 18;
```

```sql
SELECT *
FROM clientes
WHERE idade < 30;
```

---

### Filtros por datas

```sql
SELECT *
FROM clientes
WHERE data_cadastro >= '2026-01-01';
```

---

### Filtros compostos

```sql
SELECT *
FROM clientes
WHERE idade >= 18
AND ativo = TRUE;
```

Também foram utilizados operadores como:

- `AND`
- `OR`
- `NOT`

---

# 📌 Tipos de Dados

Durante o curso conheci alguns dos principais tipos de dados do MySQL:

| Tipo | Utilização |
|-------|------------|
| INT | Números inteiros |
| VARCHAR | Texto com tamanho variável |
| CHAR | Texto com tamanho fixo |
| DATE | Datas |
| BOOLEAN | Valores verdadeiro ou falso |

---

# 🛠️ Tecnologias utilizadas

- MySQL
- MySQL Workbench
- SQL

