# 📚 SQL com MySQL — Do Básico ao Avançado

Repositório criado para registrar meus estudos, anotações e práticas realizadas durante os cursos de SQL com MySQL da [Alura](https://www.alura.com.br/).

Neste repositório estão reunidos os conteúdos desenvolvidos ao longo dos cursos:

* **SQL com MySQL: manipule e consulte dados**
* **Consultas SQL: avançando no SQL com MySQL**

A documentação acompanha minha evolução desde os fundamentos de bancos de dados relacionais e definição de estruturas até consultas SQL mais elaboradas, relacionamento entre tabelas, funções e construção de relatórios.

---

## 📌 Sumário

* [🎯 Sobre o Repositório](#-sobre-o-repositório)
* [🛠️ Tecnologias e Ferramentas](#️-tecnologias-e-ferramentas)
* [📘 Curso 1 — SQL com MySQL: manipule e consulte dados](#-curso-1--sql-com-mysql-manipule-e-consulte-dados)

  * [🗄️ Banco de Dados](#️-banco-de-dados)

    * [📜 História do SQL](#-história-do-sql)
    * [🐬 História do MySQL](#-história-do-mysql)
  * [📊 Tipos de Dados](#-tipos-de-dados)

    * [🔢 Tipos Numéricos](#-tipos-numéricos)
    * [🔤 Tipos de Strings](#-tipos-de-strings)
    * [📅 Tipos de Data e Hora](#-tipos-de-data-e-hora)
    * [🏷️ ENUM e SET](#️-enum-e-set)
    * [🌎 COLLATE](#-collate)
    * [📍 Dados Espaciais](#-dados-espaciais)
  * [🏗️ Criação e Alteração de Tabelas](#️-criação-e-alteração-de-tabelas)

    * [`CREATE DATABASE`](#create-database)
    * [`CREATE TABLE`](#create-table)
    * [🔑 Chaves e Restrições](#-chaves-e-restrições)
    * [`ALTER TABLE`](#alter-table)
    * [🔗 Adicionando FOREIGN KEY com ALTER TABLE](#-adicionando-foreign-key-com-alter-table)

---

## 🎯 Sobre o Repositório

Este repositório funciona como um registro prático dos conhecimentos adquiridos durante meus estudos de **SQL e MySQL**.

Além de armazenar os scripts desenvolvidos durante os cursos, a documentação apresenta os principais conceitos estudados, acompanhados de exemplos de comandos SQL utilizados nas atividades.

A proposta é registrar não apenas os comandos utilizados, mas também compreender como o banco de dados é estruturado, como os diferentes tipos de dados são definidos e como as tabelas podem ser relacionadas e modificadas ao longo do desenvolvimento de uma aplicação.

---

## 🛠️ Tecnologias e Ferramentas

* `SQL` — linguagem utilizada para definição, manipulação e consulta de dados.
* `MySQL` — Sistema de Gerenciamento de Banco de Dados Relacional (SGBD).
* `MySQL Workbench` — ferramenta utilizada para desenvolvimento, execução e gerenciamento dos scripts SQL.
* `Git` — controle de versão dos arquivos desenvolvidos.
* `GitHub` — armazenamento e documentação do repositório.

---

# 📘 Curso 1 — SQL com MySQL: manipule e consulte dados

Primeiro curso da trilha, com foco nos fundamentos de bancos de dados relacionais e na utilização do SQL para criar estruturas, definir dados e trabalhar com tabelas.

## 🗄️ Banco de Dados

### 📜 História do SQL

O **SQL (Structured Query Language)** surgiu na IBM durante a década de 1970, inicialmente com o nome **SEQUEL**.

A linguagem foi desenvolvida para permitir a interação com bancos de dados relacionais de maneira estruturada. Posteriormente, o SQL passou por processos de padronização pela **ANSI** e pela **ISO**, contribuindo para sua adoção por diferentes Sistemas de Gerenciamento de Bancos de Dados.

O SQL tornou-se uma das principais linguagens utilizadas para trabalhar com bancos de dados relacionais, sendo empregado para definir estruturas, manipular registros e realizar consultas.

### 🐬 História do MySQL

O **MySQL** é um **Sistema de Gerenciamento de Banco de Dados Relacional (SGBD)** de código aberto.

Foi criado pela empresa sueca **MySQL AB** e posteriormente passou pela aquisição da **Sun Microsystems**, que por sua vez foi adquirida pela **Oracle**.

Durante os estudos, o MySQL foi utilizado como ambiente para praticar os conceitos de SQL e trabalhar diretamente com bancos de dados relacionais.

---

# 📊 Tipos de Dados

A definição correta dos tipos de dados é uma etapa importante na criação de uma estrutura de banco de dados.

Durante o curso, foram estudadas diferentes categorias de dados disponíveis no MySQL, considerando características como tamanho, faixa de valores, precisão e finalidade de armazenamento.

## 🔢 Tipos Numéricos

Os tipos numéricos permitem armazenar valores inteiros e números de ponto flutuante.

### Inteiros

* `TINYINT`
* `SMALLINT`
* `MEDIUMINT`
* `INT`
* `BIGINT`

A escolha depende principalmente da faixa de valores que precisa ser armazenada.

### Ponto flutuante e precisão

* `DECIMAL`
* `FLOAT`
* `DOUBLE`

O `DECIMAL` é especialmente utilizado quando é necessário trabalhar com valores de precisão exata, como valores monetários.

### `SIGNED` e `UNSIGNED`

Os atributos `SIGNED` e `UNSIGNED` permitem definir se um tipo numérico poderá armazenar valores negativos.

* `SIGNED` — permite valores positivos e negativos.
* `UNSIGNED` — permite somente valores não negativos, ampliando a faixa disponível para valores positivos.

Exemplo:

```sql
CREATE TABLE produtos (
    id INT UNSIGNED
);
```

### `ZEROFILL`

O atributo `ZEROFILL` permite preencher com zeros à esquerda a representação de determinados valores numéricos.

Exemplo:

```sql
CREATE TABLE produtos (
    codigo INT(5) ZEROFILL
);
```

Um valor como `25` pode ser apresentado como:

```text
00025
```

### Valores fora do intervalo

Também foram observados os problemas relacionados à tentativa de armazenar valores que ultrapassam a faixa suportada pelo tipo numérico escolhido.

Esse comportamento reforça a importância de selecionar um tipo de dado compatível com os valores que a aplicação precisa armazenar.

---

## 🔤 Tipos de Strings

Os tipos de strings são utilizados para armazenamento de caracteres e textos.

Entre os tipos estudados:

* `CHAR`
* `VARCHAR`
* `TEXT`
* `BLOB`

### `CHAR`

Utilizado para strings de tamanho fixo.

É adequado quando os valores possuem tamanho conhecido ou praticamente constante.

### `VARCHAR`

Utilizado para strings de tamanho variável.

É apropriado para informações cujo tamanho pode variar, como nomes, endereços e descrições curtas.

### `TEXT`

Indicado para armazenamento de textos maiores.

### `BLOB`

O tipo `BLOB` permite armazenar dados binários.

### Tamanho fixo e variável

Uma diferença importante estudada foi a forma como `CHAR` e `VARCHAR` trabalham com o tamanho dos valores:

* `CHAR` → tamanho fixo;
* `VARCHAR` → tamanho variável.

A escolha do tipo deve considerar a natureza dos dados que serão armazenados.

---

## 📅 Tipos de Data e Hora

O MySQL possui tipos específicos para armazenar informações relacionadas a datas e horários.

Durante os estudos foram abordadas estruturas utilizadas para representar:

* datas;
* horários;
* data e horário.

A escolha do tipo depende da informação que precisa ser armazenada e da precisão necessária para o sistema.

---

## 🏷️ ENUM e SET

O MySQL também disponibiliza tipos que permitem restringir os valores aceitos em uma coluna.

### `ENUM`

Permite definir previamente um conjunto de valores possíveis para uma coluna.

Exemplo:

```sql
CREATE TABLE usuarios (
    status ENUM('ATIVO', 'INATIVO')
);
```

Nesse caso, a coluna `status` trabalha com opções previamente determinadas.

### `SET`

Também trabalha com um conjunto previamente definido de opções, porém permite armazenar **uma ou mais opções** simultaneamente.

Exemplo:

```sql
CREATE TABLE produtos (
    categorias SET('NOVO', 'PROMOCAO', 'DESTAQUE')
);
```

---

## 🌎 COLLATE

`COLLATE` está relacionado às regras utilizadas pelo banco para **comparar e ordenar strings**.

Essas configurações influenciam aspectos como:

* comparação de caracteres;
* ordenação;
* acentuação;
* diferenciação ou não entre determinadas variações de caracteres.

Esse conceito é importante porque a forma como os textos são comparados pode afetar o resultado das consultas realizadas posteriormente.

---

## 📍 Dados Espaciais

Também foi realizada uma introdução aos **dados espaciais**, utilizados para representar informações relacionadas a posições e formas geográficas.

Esse tipo de dado permite trabalhar com informações que possuem uma dimensão espacial, sendo útil em aplicações que precisam representar localizações ou outros elementos geográficos.

---

# 🏗️ Criação e Alteração de Tabelas

Uma parte fundamental dos estudos foi a definição da estrutura do banco de dados.

Foram praticados comandos utilizados para:

* criar bancos de dados;
* criar tabelas;
* definir colunas;
* escolher tipos de dados;
* estabelecer chaves;
* definir restrições;
* alterar estruturas existentes;
* estabelecer relacionamentos entre tabelas.

---

## `CREATE DATABASE`

O comando `CREATE DATABASE` é utilizado para criar um novo banco de dados.

Exemplo:

```sql
CREATE DATABASE sucos;
```

Depois da criação, o banco pode ser selecionado para receber as tabelas e demais estruturas:

```sql
USE sucos;
```

O comando `USE` define qual banco de dados será utilizado pelos comandos seguintes.

---

## `CREATE TABLE`

O comando `CREATE TABLE` permite criar uma nova tabela e definir sua estrutura.

Exemplo:

```sql
CREATE TABLE produtos (
    id INT,
    nome VARCHAR(100),
    preco DECIMAL(10,2)
);
```

Na definição da tabela, cada coluna possui:

* um nome;
* um tipo de dado;
* opcionalmente, restrições e outras propriedades.

A definição da estrutura acontece antes da inserção dos registros, estabelecendo quais informações poderão ser armazenadas.

---

## 🔑 Chaves e Restrições

Além dos tipos de dados, uma tabela pode possuir regras que ajudam a garantir a integridade das informações.

### `PRIMARY KEY`

A **chave primária** identifica de forma única cada registro de uma tabela.

Exemplo:

```sql
CREATE TABLE produtos (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    preco DECIMAL(10,2)
);
```

Nesse exemplo, `id` funciona como identificador único dos produtos.

### `AUTO_INCREMENT`

O `AUTO_INCREMENT` permite que o MySQL gere automaticamente valores sequenciais para uma coluna numérica, sendo bastante utilizado em identificadores.

Exemplo:

```sql
CREATE TABLE produtos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100),
    preco DECIMAL(10,2)
);
```

Assim, novos registros podem receber automaticamente um novo identificador.

### `NOT NULL`

A restrição `NOT NULL` determina que uma coluna não pode receber valor `NULL`.

Exemplo:

```sql
CREATE TABLE produtos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL
);
```

Nesse caso, um produto precisa obrigatoriamente possuir um valor para `nome`.

---

## `ALTER TABLE`

Enquanto `CREATE TABLE` é utilizado para criar uma nova tabela, `ALTER TABLE` permite modificar a estrutura de uma tabela que já existe.

Uma tabela pode precisar ser alterada durante a evolução de um banco de dados, por exemplo, para adicionar uma nova coluna.

Exemplo:

```sql
ALTER TABLE produtos
ADD COLUMN categoria VARCHAR(50);
```

Nesse caso, a tabela `produtos` recebe uma nova coluna chamada `categoria`.

O comando também pode ser utilizado para outras alterações estruturais, como adicionar restrições e estabelecer relacionamentos.

---

## 🔗 Adicionando `FOREIGN KEY` com `ALTER TABLE`

Uma **chave estrangeira (`FOREIGN KEY`)** é utilizada para estabelecer um relacionamento entre tabelas.

Por exemplo, podemos ter uma tabela `categorias`:

```sql
CREATE TABLE categorias (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL
);
```

E uma tabela `produtos` contendo uma coluna destinada a armazenar a categoria relacionada:

```sql
CREATE TABLE produtos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    id_categoria INT
);
```

Se as tabelas já estiverem criadas, o relacionamento pode ser adicionado posteriormente utilizando `ALTER TABLE`:

```sql
ALTER TABLE produtos
ADD CONSTRAINT fk_produto_categoria
FOREIGN KEY (id_categoria)
REFERENCES categorias(id);
```

Nesse comando:

* `ADD CONSTRAINT` adiciona uma nova restrição à tabela;
* `fk_produto_categoria` é o nome atribuído à restrição;
* `FOREIGN KEY (id_categoria)` define a coluna que armazenará a referência;
* `REFERENCES categorias(id)` indica a tabela e a coluna que serão referenciadas.

Dessa forma, `produtos.id_categoria` passa a estabelecer uma relação com `categorias.id`.

Essa abordagem também demonstra uma diferença importante entre **criar uma estrutura** e **alterar uma estrutura existente**: o relacionamento não precisa necessariamente ser definido no momento da criação da tabela, podendo ser acrescentado posteriormente conforme o banco evolui.

---

# 📝 Manipulação e Consulta de Dados

Depois de definir a estrutura das tabelas, o próximo passo foi aprender a trabalhar com os registros armazenados no banco de dados.

Nesta etapa, foram estudados os comandos responsáveis por **inserir, atualizar, excluir e consultar informações**, além dos recursos utilizados para filtrar, ordenar e organizar os resultados.

---

## ➕ `INSERT`

O comando `INSERT` é utilizado para adicionar novos registros a uma tabela.

### Inserindo um registro

```sql
INSERT INTO produtos (nome, preco, categoria)
VALUES ('Suco de Laranja', 8.50, 'Frutas');
```

Nesse formato, as colunas que receberão valores são especificadas explicitamente, tornando a instrução mais clara e evitando depender da ordem física das colunas.

### Inserindo múltiplos registros

Também é possível inserir vários registros utilizando uma única instrução:

```sql
INSERT INTO produtos (nome, preco, categoria)
VALUES
    ('Suco de Uva', 9.00, 'Frutas'),
    ('Suco de Manga', 7.50, 'Frutas'),
    ('Suco de Maracujá', 8.00, 'Frutas');
```

Essa abordagem permite realizar múltiplas inserções de maneira mais eficiente.

---

# 🔄 `UPDATE`

O comando `UPDATE` permite modificar dados que já estão armazenados em uma tabela.

Exemplo:

```sql
UPDATE produtos
SET preco = 10.00
WHERE id = 1;
```

A cláusula `WHERE` determina quais registros serão alterados.

Sem uma condição, o comando pode modificar **todos os registros da tabela**:

```sql
UPDATE produtos
SET preco = 10.00;
```

Por isso, a utilização consciente do `WHERE` é fundamental para evitar alterações indesejadas.

---

# 🗑️ `DELETE`

O comando `DELETE` é utilizado para remover registros.

Exemplo:

```sql
DELETE FROM produtos
WHERE id = 1;
```

Assim como no `UPDATE`, o `WHERE` determina quais registros serão removidos.

Sem uma condição:

```sql
DELETE FROM produtos;
```

todos os registros da tabela podem ser excluídos.

> ⚠️ `DELETE` remove os registros, mas não elimina a estrutura da tabela.

---

# 🔎 `SELECT`

O `SELECT` é utilizado para consultar informações armazenadas no banco de dados.

Uma consulta simples pode retornar todas as colunas:

```sql
SELECT *
FROM produtos;
```

Também é possível selecionar apenas as informações necessárias:

```sql
SELECT nome, preco
FROM produtos;
```

Selecionar somente as colunas relevantes torna os resultados mais objetivos e pode reduzir a quantidade de dados retornados.

---

# 🎯 `WHERE`

A cláusula `WHERE` permite estabelecer condições para selecionar determinados registros.

Exemplo:

```sql
SELECT *
FROM produtos
WHERE preco > 10;
```

Nesse caso, somente os produtos cujo preço seja maior que `10` serão retornados.

O `WHERE` também pode ser utilizado em comandos de alteração e exclusão, como demonstrado anteriormente.

---

# ⚙️ Operadores de Comparação

As condições das consultas podem utilizar diferentes operadores:

| Operador | Significado    |
| -------- | -------------- |
| `=`      | Igual          |
| `<>`     | Diferente      |
| `!=`     | Diferente      |
| `>`      | Maior que      |
| `<`      | Menor que      |
| `>=`     | Maior ou igual |
| `<=`     | Menor ou igual |

Exemplo:

```sql
SELECT nome, preco
FROM produtos
WHERE preco >= 10;
```

---

# 🔗 Operadores Lógicos

As condições podem ser combinadas utilizando operadores lógicos.

## `AND`

Exige que todas as condições sejam verdadeiras.

```sql
SELECT *
FROM produtos
WHERE categoria = 'Frutas'
  AND preco < 10;
```

## `OR`

Permite que pelo menos uma das condições seja verdadeira.

```sql
SELECT *
FROM produtos
WHERE categoria = 'Frutas'
   OR categoria = 'Legumes';
```

A combinação desses operadores permite construir filtros mais específicos.

---

# 🔍 `LIKE`

O operador `LIKE` permite realizar buscas baseadas em padrões de texto.

O caractere `%` representa uma sequência de caracteres.

### Começando com determinado texto

```sql
SELECT *
FROM produtos
WHERE nome LIKE 'Suco%';
```

Retorna valores que começam com `Suco`.

### Contendo determinado texto

```sql
SELECT *
FROM produtos
WHERE nome LIKE '%Uva%';
```

Retorna valores que contenham `Uva` em qualquer posição.

### Terminando com determinado texto

```sql
SELECT *
FROM produtos
WHERE nome LIKE '%Laranja';
```

Retorna valores que terminam com `Laranja`.

O `LIKE` é especialmente útil para pesquisas textuais em que não se conhece exatamente o valor completo.

---

# 🔢 `DISTINCT`

O `DISTINCT` elimina valores duplicados do resultado da consulta.

Exemplo:

```sql
SELECT DISTINCT categoria
FROM produtos;
```

Se vários produtos pertencerem à mesma categoria, cada categoria aparecerá apenas uma vez no resultado.

---

# ↕️ `ORDER BY`

A cláusula `ORDER BY` permite ordenar os resultados de uma consulta.

### Ordem crescente

```sql
SELECT nome, preco
FROM produtos
ORDER BY preco ASC;
```

`ASC` representa a ordem crescente e é o comportamento padrão.

### Ordem decrescente

```sql
SELECT nome, preco
FROM produtos
ORDER BY preco DESC;
```

`DESC` organiza os resultados em ordem decrescente.

Também é possível ordenar por mais de uma coluna:

```sql
SELECT nome, categoria, preco
FROM produtos
ORDER BY categoria ASC, preco DESC;
```

Nesse caso, os resultados são organizados primeiro por categoria e, dentro de cada categoria, pelo preço em ordem decrescente.

---

# 🔢 `LIMIT`

O `LIMIT` restringe a quantidade de registros retornados pela consulta.

```sql
SELECT *
FROM produtos
LIMIT 5;
```

Nesse exemplo, somente os cinco primeiros registros do resultado serão apresentados.

Combinado com `ORDER BY`, pode ser utilizado para obter resultados específicos, como os produtos de maior ou menor preço:

```sql
SELECT nome, preco
FROM produtos
ORDER BY preco DESC
LIMIT 5;
```

---

# 📊 Funções de Agregação

As funções de agregação permitem realizar cálculos sobre conjuntos de registros.

Entre as funções estudadas estão:

* `COUNT()` — quantidade de registros;
* `SUM()` — soma dos valores;
* `AVG()` — média;
* `MIN()` — menor valor;
* `MAX()` — maior valor.

### `COUNT()`

```sql
SELECT COUNT(*)
FROM produtos;
```

Retorna a quantidade de registros encontrados.

### `SUM()`

```sql
SELECT SUM(preco)
FROM produtos;
```

Calcula a soma dos valores da coluna.

### `AVG()`

```sql
SELECT AVG(preco)
FROM produtos;
```

Calcula a média dos valores.

### `MIN()` e `MAX()`

```sql
SELECT
    MIN(preco) AS menor_preco,
    MAX(preco) AS maior_preco
FROM produtos;
```

Permitem identificar os valores mínimo e máximo encontrados.

---

# 📦 `GROUP BY`

O `GROUP BY` permite agrupar registros que possuem o mesmo valor em determinada coluna.

Por exemplo, podemos contabilizar quantos produtos existem em cada categoria:

```sql
SELECT categoria, COUNT(*) AS quantidade
FROM produtos
GROUP BY categoria;
```

Nesse caso, os registros são separados por categoria e a função `COUNT()` é aplicada individualmente a cada grupo.

O `GROUP BY` é especialmente importante para transformar uma consulta de registros individuais em uma consulta de informações consolidadas.

---

# 🎯 `HAVING`

Enquanto o `WHERE` é utilizado para filtrar registros antes da formação dos grupos, o `HAVING` permite filtrar os resultados gerados pelo `GROUP BY`.

Exemplo:

```sql
SELECT categoria, COUNT(*) AS quantidade
FROM produtos
GROUP BY categoria
HAVING COUNT(*) > 5;
```

Nesse caso, somente as categorias que possuem mais de cinco produtos serão apresentadas.

### `WHERE` × `HAVING`

A diferença fundamental é:

* `WHERE` → filtra registros;
* `HAVING` → filtra grupos resultantes de uma agregação.

Essa distinção é importante principalmente em consultas que utilizam `GROUP BY` e funções de agregação.

---

# 🧠 `CASE`

O `CASE` permite criar condições dentro de uma consulta e produzir resultados diferentes de acordo com essas condições.

Exemplo:

```sql
SELECT
    nome,
    preco,
    CASE
        WHEN preco < 10 THEN 'Barato'
        WHEN preco <= 20 THEN 'Moderado'
        ELSE 'Caro'
    END AS classificacao
FROM produtos;
```

Nesse exemplo, cada produto recebe uma classificação baseada no seu preço.

O `CASE` permite transformar regras de negócio em classificações dentro do próprio resultado da consulta.

---

# 🏷️ Aliases com `AS`

O `AS` pode ser utilizado para criar um nome alternativo para uma coluna ou expressão no resultado.

Exemplo:

```sql
SELECT
    nome,
    preco AS valor
FROM produtos;
```

Também pode ser utilizado com funções:

```sql
SELECT
    AVG(preco) AS preco_medio
FROM produtos;
```

Os aliases tornam os resultados mais legíveis e facilitam a identificação das informações retornadas.

---

# 🧩 Construindo Consultas Mais Elaboradas

Os recursos estudados podem ser combinados em uma mesma consulta.

Por exemplo:

```sql
SELECT
    categoria,
    COUNT(*) AS quantidade,
    AVG(preco) AS preco_medio
FROM produtos
WHERE preco > 5
GROUP BY categoria
HAVING COUNT(*) >= 2
ORDER BY preco_medio DESC
LIMIT 5;
```

Essa consulta combina diferentes etapas:

1. `WHERE` → seleciona produtos com preço superior a `5`;
2. `GROUP BY` → agrupa os produtos por categoria;
3. `COUNT()` → contabiliza os produtos de cada categoria;
4. `AVG()` → calcula o preço médio;
5. `HAVING` → mantém apenas categorias com pelo menos dois produtos;
6. `ORDER BY` → ordena pela média de preço;
7. `LIMIT` → restringe o resultado aos cinco primeiros grupos.

A combinação desses recursos permite construir consultas capazes de gerar informações mais próximas das necessidades de uma aplicação ou relatório.

---

# 🚀 Consultas Avançadas e Recursos do MySQL

Nesta etapa, os conhecimentos de SQL foram ampliados com recursos voltados para **combinar informações de diferentes tabelas, trabalhar com consultas dentro de consultas, reutilizar resultados e aplicar funções sobre os dados**.

O objetivo passa a ser construir consultas mais completas e transformar dados armazenados em informações úteis para análise e relatórios.

---

# 🔗 `JOIN`

Os `JOINs` permitem combinar registros provenientes de duas ou mais tabelas relacionadas.

Considerando uma estrutura em que produtos possuem uma categoria associada, podemos consultar as informações das duas tabelas:

```sql
SELECT
    produtos.nome,
    categorias.nome AS categoria
FROM produtos
INNER JOIN categorias
    ON produtos.id_categoria = categorias.id;
```

A condição definida em `ON` determina como os registros das tabelas devem ser relacionados.

---

## `INNER JOIN`

O `INNER JOIN` retorna somente os registros que possuem correspondência nas duas tabelas.

```sql
SELECT
    produtos.nome,
    categorias.nome AS categoria
FROM produtos
INNER JOIN categorias
    ON produtos.id_categoria = categorias.id;
```

Se um produto não possuir uma categoria correspondente, ele não será incluído no resultado.

---

## `LEFT JOIN`

O `LEFT JOIN` mantém todos os registros da tabela localizada à esquerda da consulta, mesmo quando não existe correspondência na tabela relacionada.

```sql
SELECT
    produtos.nome,
    categorias.nome AS categoria
FROM produtos
LEFT JOIN categorias
    ON produtos.id_categoria = categorias.id;
```

Nesse caso, produtos sem categoria correspondente continuam aparecendo no resultado.

---

## `RIGHT JOIN`

O `RIGHT JOIN` utiliza uma lógica semelhante, mas prioriza os registros da tabela localizada à direita.

```sql
SELECT
    produtos.nome,
    categorias.nome AS categoria
FROM produtos
RIGHT JOIN categorias
    ON produtos.id_categoria = categorias.id;
```

Assim, categorias sem produtos relacionados também podem aparecer no resultado.

---

## 🧠 Escolhendo o tipo de `JOIN`

A escolha do `JOIN` depende da informação que se deseja obter:

| JOIN         | Resultado principal                      |
| ------------ | ---------------------------------------- |
| `INNER JOIN` | Apenas registros com correspondência     |
| `LEFT JOIN`  | Todos os registros da tabela da esquerda |
| `RIGHT JOIN` | Todos os registros da tabela da direita  |

Os `JOINs` são fundamentais para consultar informações distribuídas entre diferentes tabelas sem precisar duplicar os dados armazenados.

---

# 🔀 `UNION`

O `UNION` permite combinar os resultados de duas consultas em um único conjunto de resultados.

```sql
SELECT nome
FROM clientes
WHERE cidade = 'Santos'

UNION

SELECT nome
FROM fornecedores
WHERE cidade = 'Santos';
```

As consultas combinadas precisam possuir estruturas compatíveis, principalmente em relação à quantidade e aos tipos das colunas retornadas.

Por padrão, o `UNION` elimina registros duplicados.

---

## `UNION ALL`

O `UNION ALL` também combina os resultados, mas mantém as duplicidades.

```sql
SELECT nome
FROM clientes

UNION ALL

SELECT nome
FROM fornecedores;
```

A diferença principal é:

* `UNION` → elimina duplicidades;
* `UNION ALL` → mantém os resultados duplicados.

---

# 🔍 Subconsultas

Uma **subconsulta (subquery)** é uma consulta SQL inserida dentro de outra consulta.

Ela pode ser utilizada quando o resultado de uma consulta é necessário para determinar o resultado de outra.

Exemplo:

```sql
SELECT nome, preco
FROM produtos
WHERE preco > (
    SELECT AVG(preco)
    FROM produtos
);
```

A consulta interna calcula o preço médio dos produtos.

A consulta externa utiliza esse resultado para retornar somente os produtos que possuem preço acima da média.

As subconsultas permitem construir filtros e análises baseados em resultados obtidos dinamicamente pelo próprio banco.

---

# 👁️ Views

Uma **View** é uma estrutura baseada em uma consulta SQL que pode ser utilizada posteriormente como uma tabela virtual.

Ela permite encapsular uma consulta e facilitar seu reaproveitamento.

### Criando uma View

```sql
CREATE VIEW produtos_com_categorias AS
SELECT
    produtos.id,
    produtos.nome,
    produtos.preco,
    categorias.nome AS categoria
FROM produtos
INNER JOIN categorias
    ON produtos.id_categoria = categorias.id;
```

Depois de criada, a View pode ser consultada:

```sql
SELECT *
FROM produtos_com_categorias;
```

A utilização de Views pode ajudar a:

* simplificar consultas recorrentes;
* organizar consultas mais complexas;
* disponibilizar uma visão específica dos dados;
* facilitar a reutilização de consultas.

---

# 🔤 Funções de Texto

O MySQL disponibiliza funções para manipulação de strings.

Entre os recursos estudados estão funções utilizadas para:

* alterar maiúsculas e minúsculas;
* descobrir o tamanho de um texto;
* unir strings;
* extrair partes de um texto;
* remover espaços;
* trabalhar com caracteres.

### `UPPER()` e `LOWER()`

```sql
SELECT
    UPPER(nome) AS nome_maiusculo,
    LOWER(nome) AS nome_minusculo
FROM produtos;
```

### `LENGTH()`

```sql
SELECT
    nome,
    LENGTH(nome) AS quantidade_caracteres
FROM produtos;
```

### `CONCAT()`

Permite combinar diferentes valores em uma única string.

```sql
SELECT
    CONCAT(nome, ' - R$ ', preco) AS produto
FROM produtos;
```

Essas funções podem ser utilizadas para transformar os dados diretamente durante a consulta.

---

# 🔢 Funções Matemáticas

As funções matemáticas permitem realizar operações e transformações numéricas diretamente no banco.

Entre os recursos estudados estão funções relacionadas a:

* arredondamento;
* valores absolutos;
* potência;
* números aleatórios;
* operações matemáticas.

### `ROUND()`

```sql
SELECT
    ROUND(preco, 2) AS preco_arredondado
FROM produtos;
```

A função pode ser utilizada para controlar a quantidade de casas decimais apresentada no resultado.

---

# 📅 Funções de Data e Hora

O MySQL também possui funções para trabalhar com informações temporais.

Esses recursos permitem, entre outras operações:

* obter a data atual;
* obter o horário atual;
* extrair partes de uma data;
* calcular diferenças;
* realizar operações com datas.

### Data atual

```sql
SELECT CURRENT_DATE();
```

### Data e horário atuais

```sql
SELECT CURRENT_TIMESTAMP();
```

### Extraindo informações de uma data

```sql
SELECT
    YEAR(data_cadastro) AS ano,
    MONTH(data_cadastro) AS mes,
    DAY(data_cadastro) AS dia
FROM clientes;
```

Essas funções são úteis em consultas que dependem de períodos, datas de cadastro, vencimentos e análises temporais.

---

# 🔄 Conversão de Dados

Durante os estudos também foram abordadas funções utilizadas para converter valores entre diferentes tipos ou formatos.

O `CAST()` permite realizar conversões explicitamente.

```sql
SELECT CAST(preco AS DECIMAL(10,2))
FROM produtos;
```

A conversão de tipos pode ser necessária quando uma operação ou comparação exige que determinado valor seja tratado de uma maneira específica.

---

# 📑 Consultas para Relatórios

A combinação dos recursos estudados permite construir consultas direcionadas à geração de informações para relatórios.

Por exemplo:

```sql
SELECT
    categorias.nome AS categoria,
    COUNT(produtos.id) AS quantidade_produtos,
    ROUND(AVG(produtos.preco), 2) AS preco_medio
FROM categorias
LEFT JOIN produtos
    ON produtos.id_categoria = categorias.id
GROUP BY categorias.id, categorias.nome
ORDER BY quantidade_produtos DESC;
```

Essa consulta combina:

* relacionamento entre tabelas;
* `LEFT JOIN`;
* função `COUNT()`;
* função `AVG()`;
* `ROUND()`;
* agrupamento;
* ordenação.

O resultado apresenta uma visão consolidada das categorias, incluindo a quantidade de produtos e o preço médio de cada uma.

---

# 🧠 Evolução dos Conhecimentos

Ao longo dos estudos, a utilização do SQL evoluiu de comandos básicos para consultas capazes de representar necessidades mais próximas de aplicações reais.

A jornada passou por diferentes níveis:

### 1. Estrutura

Compreensão de bancos relacionais, tabelas, tipos de dados, chaves e restrições.

### 2. Manipulação

Utilização de comandos para inserir, atualizar e remover registros.

### 3. Consulta

Construção de consultas com filtros, ordenação, agrupamentos e funções de agregação.

### 4. Relacionamento

Combinação de informações distribuídas entre diferentes tabelas utilizando `JOIN`.

### 5. Análise

Uso de agregações, subconsultas, funções e consultas compostas para transformar registros em informações.

### 6. Reutilização

Criação de Views para encapsular consultas que podem ser utilizadas novamente.

Esse processo permitiu compreender o SQL não apenas como uma sequência de comandos, mas como uma ferramenta para **modelar, consultar e analisar informações armazenadas em bancos de dados relacionais**.

---

### 🚀 Próximos passos

Com os fundamentos de SQL e MySQL consolidados, os próximos estudos podem avançar para a integração de bancos de dados com aplicações, utilização de SQL a partir de linguagens de programação e implementação de mecanismos de persistência.
