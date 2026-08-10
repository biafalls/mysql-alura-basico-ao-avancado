# 📚 SQL com MySQL — Do Básico ao Avançado

Repositório criado para registrar meus estudos e práticas nos cursos de **SQL com MySQL**, realizados pela [Alura](https://www.alura.com.br/).

Neste repositório estão reunidos os conteúdos dos cursos:

- **SQL com MySQL: manipule e consulte dados**
- **Consultas SQL: avançando no SQL com MySQL**

A proposta é documentar minha evolução desde os fundamentos de bancos de dados e consultas SQL até recursos mais avançados, como `JOINs`, subconsultas, `Views`, funções de agregação e construção de relatórios.

---

## 📌 Sumário

- [🎯 Sobre o Repositório](#-sobre-o-repositório)
- [🛠️ Tecnologias e Ferramentas](#️-tecnologias-e-ferramentas)
- [📘 Curso 1 — SQL com MySQL: manipule e consulte dados](#-curso-1--sql-com-mysql-manipule-e-consulte-dados)
  - [🗄️ Banco de Dados](#️-banco-de-dados)
  - [📊 Tipos de Dados](#-tipos-de-dados)
  - [🏗️ Criação e Alteração de Tabelas](#️-criação-e-alteração-de-tabelas)
  - [✏️ Manipulação de Dados](#️-manipulação-de-dados)
  - [🔎 Consultas](#-consultas)
- [📗 Curso 2 — Consultas SQL: avançando no SQL com MySQL](#-curso-2--consultas-sql-avançando-no-sql-com-mysql)
  - [💾 Recuperação do Ambiente](#-recuperação-do-ambiente)
  - [🔎 Consultas e Filtros](#-consultas-e-filtros)
  - [🎯 DISTINCT](#-distinct)
  - [↕️ Ordenação](#️-ordenação)
  - [📊 GROUP BY e Funções de Agregação](#-group-by-e-funções-de-agregação)
  - [🔍 HAVING](#-having)
  - [🔢 LIMIT](#-limit)
  - [🔀 CASE](#-case)
  - [🔗 JOINs](#-joins)
  - [🔄 UNION e UNION ALL](#-union-e-union-all)
  - [🧩 Subconsultas](#-subconsultas)
  - [👁️ Views](#️-views)
  - [🔤 Funções de Texto](#-funções-de-texto)
  - [➗ Funções Matemáticas](#-funções-matemáticas)
  - [📅 Funções de Data](#-funções-de-data)
  - [🔄 Funções de Conversão](#-funções-de-conversão)
  - [📑 Construção de Relatórios](#-construção-de-relatórios)
- [🚀 Evolução dos Conhecimentos](#-evolução-dos-conhecimentos)
- [📂 Organização do Repositório](#-organização-do-repositório)

---

## 🎯 Sobre o Repositório

Este repositório reúne anotações, exercícios e consultas desenvolvidas durante minha aprendizagem de **SQL e MySQL**.

Ao longo dos cursos, os estudos partiram dos conceitos fundamentais de bancos de dados e avançaram para consultas mais elaboradas, relacionamento entre tabelas, análise de dados e construção de relatórios.

O objetivo é utilizar este espaço como registro da minha evolução e também como material de consulta para estudos futuros.

---

## 🛠️ Tecnologias e Ferramentas

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)

- **MySQL**
- **SQL**
- **MySQL Workbench**
- **Git**
- **GitHub**

---

# 📘 Curso 1 — SQL com MySQL: manipule e consulte dados

Curso realizado pela **Alura**, com foco nos fundamentos de bancos de dados relacionais e na utilização do SQL para criação, manipulação e consulta de dados.

## 🗄️ Banco de Dados

Durante o curso, foram apresentados conceitos fundamentais sobre bancos de dados relacionais e o funcionamento do MySQL.

Também foi abordada a história do SQL e sua importância como linguagem utilizada para comunicação com bancos de dados relacionais.

### 📜 História do SQL

O SQL surgiu na **IBM na década de 1970**, inicialmente conhecido como **SEQUEL**.

Posteriormente, a linguagem foi padronizada pela **ANSI** e pela **ISO**, contribuindo para sua ampla utilização em diferentes Sistemas de Gerenciamento de Bancos de Dados (SGBDs).

### 🐬 História do MySQL

O **MySQL** é um Sistema de Gerenciamento de Banco de Dados Relacional (SGBD) de código aberto.

Foi criado pela empresa sueca **MySQL AB** e posteriormente adquirido pela **Sun Microsystems** e pela **Oracle**.

---

## 📊 Tipos de Dados

Um dos pontos importantes estudados foi a escolha adequada dos tipos de dados para armazenar informações.

### 🔢 Tipos numéricos

- `TINYINT`
- `SMALLINT`
- `MEDIUMINT`
- `INT`
- `BIGINT`
- `DECIMAL`
- `FLOAT`
- `DOUBLE`

Também foram abordados conceitos como:

- `SIGNED`
- `UNSIGNED`
- `ZEROFILL`
- Valores fora do intervalo (`OUT OF RANGE`)
- Números inteiros e de ponto flutuante

### 🔤 Strings

Foram estudados diferentes tipos para armazenamento de textos:

- `CHAR`
- `VARCHAR`
- `TEXT`
- `BLOB`

Também foram abordadas diferenças entre campos de tamanho fixo e variável.

### 📅 Datas

Tipos utilizados para armazenamento de informações relacionadas a datas e horários.

### 🏷️ ENUM e SET

- `ENUM` — permite definir um conjunto de valores possíveis para um campo.
- `SET` — permite armazenar uma ou mais opções de um conjunto previamente definido.

### 🌎 COLLATE

Estudo de configurações relacionadas à comparação e ordenação de strings, considerando regras de caracteres e acentuação.

### 📍 Spatial

Introdução aos tipos utilizados para trabalhar com dados espaciais.

---

## 🏗️ Criação e Alteração de Tabelas

Durante o curso foram praticados comandos relacionados à criação e estruturação das tabelas.

Entre os principais conceitos:

- Criação de bancos de dados
- Criação de tabelas
- Definição de colunas
- Tipos de dados
- Chaves
- Restrições
- Alteração da estrutura das tabelas

### `CREATE TABLE`

Utilizado para criar uma nova tabela.

```sql
CREATE TABLE produtos (
    id INT,
    nome VARCHAR(100),
    preco DECIMAL(10,2)
);
```

### `ALTER TABLE`

Utilizado para modificar a estrutura de uma tabela existente.

```sql
ALTER TABLE produtos
ADD COLUMN categoria VARCHAR(50);
```

---

## ✏️ Manipulação de Dados

Foram estudados os principais comandos para manipulação dos registros armazenados nas tabelas.

### `INSERT`

Utilizado para inserir registros.

```sql
INSERT INTO produtos (id, nome, preco)
VALUES (1, 'Produto A', 10.00);
```

### `UPDATE`

Utilizado para atualizar registros existentes.

```sql
UPDATE produtos
SET preco = 12.00
WHERE id = 1;
```

### `DELETE`

Utilizado para remover registros.

```sql
DELETE FROM produtos
WHERE id = 1;
```

---

## 🔎 Consultas

O comando `SELECT` foi apresentado como principal recurso para recuperação de informações armazenadas no banco.

```sql
SELECT *
FROM produtos;
```

Também foram trabalhados filtros e condições para retornar somente os dados necessários.

---

# 📗 Curso 2 — Consultas SQL: avançando no SQL com MySQL

Neste curso, os conhecimentos de SQL foram aprofundados, explorando consultas mais complexas, relacionamento entre tabelas, funções e construção de relatórios.

---

## 💾 Recuperação do Ambiente

Foram estudadas diferentes maneiras de recuperar ou importar uma base de dados para continuar os exercícios.

Entre elas:

- **Data Import / Restore**
- **Run SQL Script**
- Execução manual de comandos SQL

Esse processo também reforçou a importância de conhecer a estrutura da base de dados antes de iniciar a construção das consultas.

---

## 🔎 Consultas e Filtros

As consultas foram aprofundadas utilizando diferentes condições para selecionar os registros desejados.

### `WHERE`

Permite definir condições para filtrar os resultados.

```sql
SELECT *
FROM produtos
WHERE preco > 100;
```

### Operadores de comparação

Foram utilizados:

- `>`
- `>=`
- `<`
- `<=`
- `=`
- `<>`

### Operadores lógicos

Também foram combinadas diferentes condições utilizando:

- `AND`
- `OR`

### `LIKE`

Utilizado para realizar buscas baseadas em padrões de texto.

```sql
SELECT *
FROM clientes
WHERE nome LIKE 'A%';
```

---

## 🎯 DISTINCT

O `DISTINCT` permite apresentar somente valores diferentes em uma consulta, eliminando duplicidades no resultado.

```sql
SELECT DISTINCT categoria
FROM produtos;
```

---

## ↕️ Ordenação

O `ORDER BY` permite organizar os resultados de uma consulta.

### Ordem crescente

```sql
SELECT *
FROM produtos
ORDER BY preco ASC;
```

### Ordem decrescente

```sql
SELECT *
FROM produtos
ORDER BY preco DESC;
```

---

## 📊 GROUP BY e Funções de Agregação

O `GROUP BY` permite agrupar registros de acordo com um ou mais campos.

Foi utilizado em conjunto com funções de agregação para realizar análises sobre os dados.

### Principais funções estudadas

| Função | Utilização |
|---|---|
| `SUM()` | Soma dos valores |
| `MIN()` | Menor valor |
| `MAX()` | Maior valor |
| `AVG()` | Média dos valores |
| `COUNT()` | Quantidade de registros |

Exemplo:

```sql
SELECT
    categoria,
    SUM(valor) AS total
FROM vendas
GROUP BY categoria;
```

---

## 🔍 HAVING

O `HAVING` permite aplicar condições sobre os resultados agrupados.

Enquanto o `WHERE` filtra registros antes do agrupamento, o `HAVING` pode ser utilizado para filtrar os grupos gerados pelo `GROUP BY`.

```sql
SELECT
    categoria,
    SUM(valor) AS total
FROM vendas
GROUP BY categoria
HAVING SUM(valor) > 1000;
```

---

## 🔢 LIMIT

O `LIMIT` permite limitar a quantidade de registros retornados por uma consulta.

```sql
SELECT *
FROM produtos
LIMIT 10;
```

---

## 🔀 CASE

O `CASE` permite criar classificações ou condições dentro de uma consulta.

```sql
SELECT
    nome,
    preco,
    CASE
        WHEN preco >= 100 THEN 'Caro'
        ELSE 'Barato'
    END AS classificacao
FROM produtos;
```

Esse recurso pode ser utilizado para transformar valores em categorias de acordo com determinados critérios.

---

# 🔗 JOINs

Os `JOINs` permitem combinar informações provenientes de duas ou mais tabelas relacionadas.

Durante o curso foram estudados os diferentes tipos de `JOIN` suportados pelo MySQL.

### INNER JOIN

Retorna os registros que possuem correspondência entre as tabelas.

```sql
SELECT
    cliente.nome,
    pedido.data
FROM cliente
INNER JOIN pedido
    ON cliente.id = pedido.id_cliente;
```

### LEFT JOIN

Retorna todos os registros da tabela à esquerda e os registros correspondentes da tabela à direita.

### RIGHT JOIN

Retorna todos os registros da tabela à direita e os registros correspondentes da tabela à esquerda.

### Tipos estudados

- `INNER JOIN`
- `LEFT JOIN`
- `RIGHT JOIN`

Os `JOINs` são importantes para trabalhar com bancos de dados relacionais, permitindo consultar informações distribuídas entre diferentes tabelas.

---

# 🔄 UNION e UNION ALL

Os comandos `UNION` e `UNION ALL` permitem combinar os resultados de duas ou mais consultas.

Para isso, as seleções precisam possuir estruturas compatíveis, com a mesma quantidade de campos selecionados e tipos de dados compatíveis.

### UNION

Combina os resultados eliminando registros duplicados.

```sql
SELECT nome
FROM clientes

UNION

SELECT nome
FROM fornecedores;
```

### UNION ALL

Combina os resultados mantendo possíveis duplicidades.

```sql
SELECT nome
FROM clientes

UNION ALL

SELECT nome
FROM fornecedores;
```

---

# 🧩 Subconsultas

Uma subconsulta é uma consulta SQL utilizada dentro de outra consulta.

Esse recurso permite utilizar o resultado de uma consulta como critério para outra.

```sql
SELECT *
FROM produtos
WHERE preco > (
    SELECT AVG(preco)
    FROM produtos
);
```

As subconsultas foram utilizadas como uma forma de tornar as consultas mais flexíveis e trabalhar com resultados intermediários.

---

# 👁️ Views

As `Views` permitem criar uma visão baseada no resultado de uma consulta.

Elas podem ser utilizadas para facilitar o acesso a consultas que são utilizadas com frequência.

### Criando uma View

```sql
CREATE VIEW produtos_categoria AS
SELECT
    nome,
    categoria,
    preco
FROM produtos;
```

### Consultando uma View

```sql
SELECT *
FROM produtos_categoria;
```

O estudo de Views ajudou a compreender uma forma de organizar e reutilizar consultas dentro do banco de dados.

---

# 🔤 Funções de Texto

Foram estudadas funções utilizadas para manipular e trabalhar com valores textuais.

Entre os conceitos abordados estão funções para:

- Manipulação de strings
- Alteração de formatação
- Busca e tratamento de textos
- Combinação de informações textuais

Essas funções são úteis principalmente na preparação e organização dos dados retornados pelas consultas.

---

# ➗ Funções Matemáticas

Também foram exploradas funções matemáticas disponíveis no MySQL.

Essas funções permitem realizar operações e tratamentos matemáticos diretamente nas consultas SQL.

---

# 📅 Funções de Data

Foram apresentadas funções relacionadas ao tratamento de datas.

Esses recursos permitem:

- Consultar informações de datas
- Extrair partes de uma data
- Realizar operações envolvendo datas
- Organizar e analisar informações temporais

---

# 🔄 Funções de Conversão

As funções de conversão permitem transformar valores entre diferentes tipos de dados.

Esse tipo de recurso é importante quando os dados precisam ser tratados ou apresentados em um formato diferente durante uma consulta.

---

# 📑 Construção de Relatórios

Ao final do curso, os conhecimentos adquiridos foram colocados em prática na construção de **dois relatórios**, seguindo as necessidades apresentadas por uma empresa do segmento de sucos de frutas.

Essa etapa permitiu combinar diferentes recursos estudados durante o curso, como:

- Filtros
- Agrupamentos
- Funções de agregação
- `JOINs`
- Subconsultas
- `CASE`
- Funções SQL

A construção dos relatórios ajudou a aproximar os conhecimentos de SQL de uma situação prática, mostrando como consultas podem ser utilizadas para transformar dados armazenados em informações relevantes para uma empresa.

---

# 🚀 Evolução dos Conhecimentos

Com os dois cursos, minha aprendizagem em SQL evoluiu desde os fundamentos até a construção de consultas mais complexas.

### 🟢 Fundamentos

- Conceitos de bancos de dados relacionais
- História do SQL e MySQL
- Tipos de dados
- Criação de bancos e tabelas
- Alteração de tabelas
- `INSERT`
- `UPDATE`
- `DELETE`
- `SELECT`

### 🟡 Consultas e manipulação

- `WHERE`
- `AND` e `OR`
- Operadores de comparação
- `LIKE`
- `DISTINCT`
- `ORDER BY`
- `LIMIT`
- `CASE`

### 🔵 Consultas avançadas

- `GROUP BY`
- Funções de agregação
- `HAVING`
- `JOINs`
- `UNION`
- `UNION ALL`
- Subconsultas
- Views
- Funções de texto
- Funções matemáticas
- Funções de data
- Funções de conversão

### 📊 Aplicação prática

- Construção de consultas
- Análise e organização de dados
- Construção de relatórios
- Utilização de diferentes recursos SQL em conjunto

---

# 📂 Organização do Repositório

O repositório está organizado de acordo com a evolução dos conteúdos estudados.

```text
mysql-alura-basico-ao-avancado/
│
├── 📁 curso-01/
│   └── SQL com MySQL: manipule e consulte dados
│
├── 📁 curso-02/
│   └── Consultas SQL: avançando no SQL com MySQL
│
└── 📄 README.md
```

> A estrutura das pastas pode variar conforme a organização dos exercícios e arquivos desenvolvidos durante os cursos.

---

## 🎓 Cursos

### SQL com MySQL: manipule e consulte dados
📚 **Plataforma:** Alura

### Consultas SQL: avançando no SQL com MySQL
📚 **Plataforma:** Alura

---

## 💜 Sobre o aprendizado

Estudar SQL tem sido uma etapa importante na minha formação em **Análise e Desenvolvimento de Sistemas**, principalmente por ampliar minha compreensão sobre como os dados são armazenados, relacionados, consultados e transformados em informações.

Este repositório representa parte desse processo de aprendizado e continuará sendo atualizado conforme novos conhecimentos forem adquiridos.

---

**Desenvolvido por [Beatriz Lima Evangelista](https://github.com/biafalls) 💜**
