# 📚 SQL com MySQL: manipule e consulte dados

## 📖 Sobre o curso

Este repositório reúne minhas anotações e os principais conceitos estudados durante o curso **SQL com MySQL: manipule e consulte dados**, da Alura.

Ao longo do curso, construí uma base sólida sobre bancos de dados relacionais e a linguagem SQL, compreendendo desde sua história até a criação, manipulação e consulta de dados no MySQL. Além da prática com comandos SQL, também conheci os principais tipos de dados disponíveis no banco, boas práticas na definição de tabelas e diferentes formas de realizar consultas.

---

# 🎯 Objetivos do curso

- Compreender a origem e evolução da linguagem SQL.
- Conhecer a história e as características do MySQL.
- Aprender a utilizar o MySQL Workbench e o terminal.
- Criar bancos de dados e tabelas.
- Manipular registros utilizando SQL.
- Entender os diversos tipos de dados oferecidos pelo MySQL.
- Realizar consultas utilizando filtros e operadores.

---

# 📚 Conteúdo estudado

## 🏛️ História do SQL

Durante o curso foi apresentada a evolução da linguagem SQL e sua importância para bancos de dados relacionais.

Foram abordados conceitos como:

- Surgimento dos bancos de dados relacionais;
- Evolução da linguagem SQL;
- Padronização da linguagem;
- Diferenças entre SQL padrão e implementações dos SGBDs;
- Características do MySQL.

---

# 🖥️ Conhecendo o MySQL

Aprendi sobre:

- Instalação do MySQL Server;
- Instalação do MySQL Workbench;
- Navegação pelo Workbench;
- Execução de comandos SQL;
- Administração de bancos de dados.

Também utilizamos o MySQL diretamente pelo terminal:

```bash
mysql -h localhost -u root -p
```

Encerrando a sessão:

```bash
exit
```

---

# 📁 Bancos de Dados

Aprendi a criar e remover bancos de dados utilizando SQL.

## Criando um banco

```sql
CREATE DATABASE nomeBanco;
```

ou

```sql
CREATE SCHEMA nomeBanco;
```

Também foi apresentado o uso da cláusula:

```sql
CREATE DATABASE IF NOT EXISTS nomeBanco;
```

---

## Removendo um banco

```sql
DROP DATABASE nomeBanco;
```

ou

```sql
DROP SCHEMA nomeBanco;
```

Com proteção:

```sql
DROP DATABASE IF EXISTS nomeBanco;
```

---

# 📦 Tipos de Dados

Um dos tópicos mais completos do curso foi o estudo dos tipos de dados disponíveis no MySQL.

## Números inteiros

- TINYINT
- SMALLINT
- MEDIUMINT
- INT
- BIGINT

Também aprendemos:

- SIGNED
- UNSIGNED
- ZEROFILL
- AUTO_INCREMENT

Além dos erros gerados quando um valor excede os limites permitidos (**Out of Range**).

---

## Ponto flutuante

Foram apresentados:

- FLOAT
- DOUBLE
- DECIMAL

Diferenças entre precisão e armazenamento.

---

## Strings

Aprendemos a diferença entre:

### Tamanho fixo

```text
CHAR
```

### Tamanho variável

```text
VARCHAR
```

Além dos tipos:

- TEXT
- TINYTEXT
- MEDIUMTEXT
- LONGTEXT

---

## Dados Binários

- BLOB
- TINYBLOB
- MEDIUMBLOB
- LONGBLOB

---

## Datas

- DATE
- DATETIME
- TIMESTAMP
- TIME
- YEAR

---

## Outros tipos

Também conhecemos:

- ENUM
- SET
- COLLATE
- Tipos espaciais (Spatial)

---

# 🏗️ Criação de Tabelas

Aprendi a criar tabelas utilizando SQL.

```sql
CREATE TABLE produtos (
    codigo VARCHAR(10),
    nome VARCHAR(100),
    preco DECIMAL(10,2)
);
```

Também vimos como remover tabelas.

```sql
DROP TABLE produtos;
```

---

# 🔑 Alterando Tabelas

Utilizamos o comando:

```sql
ALTER TABLE
```

Para diversas operações.

## Adicionando chave primária

```sql
ALTER TABLE produtos
ADD PRIMARY KEY (codigo);
```

## Adicionando colunas

```sql
ALTER TABLE produtos
ADD COLUMN estoque INT;
```

---

# ✍️ Manipulação de Dados

## Inserção

```sql
INSERT INTO produtos (...)
VALUES (...);
```

---

## Atualização

```sql
UPDATE produtos
SET preco = 15.90
WHERE codigo = '100';
```

---

## Exclusão

```sql
DELETE FROM produtos
WHERE codigo = '100';
```

---

# 🔎 Consultas

Foram estudadas diversas formas de consulta utilizando o comando SELECT.

## Consultando todos os registros

```sql
SELECT *
FROM produtos;
```

---

## Selecionando colunas

```sql
SELECT nome, preco
FROM produtos;
```

---

## Filtrando registros

Utilizando:

```sql
WHERE
```

Operadores:

- =
- >
- <
- >=
- <=
- <>
- !=

---

## Consultas por datas

```sql
SELECT *
FROM produtos
WHERE dataCadastro >= '2026-01-01';
```

---

## Filtros compostos

Foram utilizados operadores como:

- AND
- OR
- NOT

Exemplo:

```sql
SELECT *
FROM produtos
WHERE preco > 10
AND estoque > 0;
```

---

# 💡 Curiosidades aprendidas

- O SQL utilizado no MySQL **não é Case Sensitive**, ou seja, comandos podem ser escritos em letras maiúsculas ou minúsculas.

Exemplo:

```sql
select * from produtos;
```

é equivalente a

```sql
SELECT * FROM produtos;
```

Embora a convenção seja escrever comandos SQL em letras maiúsculas para facilitar a leitura.

---

# 🛠️ Tecnologias utilizadas

- SQL
- MySQL
- MySQL Workbench
- MySQL Command Line
