# MySQL

- Banco de dados contem: **Tabelas** contem **Registros** são compostos por **Campos**
_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
# Tipos de Dados – MySQL

## Tabela de Tipos de Dados

| **Categoria** | **Subtipo** | **Tipos** | **Descrição** | **Exemplo de Uso** |
|---------------|------------|-----------|---------------|--------------------|
| **Numérico** | **Inteiro** | `TINYINT`, `SMALLINT`, `INT`, `MEDIUMINT`, `BIGINT` | Números inteiros (sem casas decimais), variando no tamanho do intervalo suportado. | Idade de uma pessoa: `INT` |
|               | **Real** | `DECIMAL`, `FLOAT`, `DOUBLE`, `REAL` | Números com casas decimais (precisão simples ou dupla). | Preço de produto: `DECIMAL(8,2)` |
|               | **Lógico** | `BIT`, `BOOLEAN` | Valores lógicos (verdadeiro ou falso). | Campo "ativo" de um usuário: `BOOLEAN` |
| **Data/Tempo** | - | `DATE`, `DATETIME`, `TIMESTAMP`, `TIME`, `YEAR` | Armazenamento de datas, horas e anos. | Data de cadastro: `DATE` |
| **Literal** | **Caractere** | `CHAR`, `VARCHAR` | Armazenam cadeias curtas de caracteres (fixas ou variáveis). | Código de produto: `CHAR(5)` |
|              | **Texto** | `TINYTEXT`, `TEXT`, `MEDIUMTEXT`, `LONGTEXT` | Textos longos, de tamanhos diferentes conforme necessidade. | Descrição de um artigo: `TEXT` |
|              | **Binário** | `TINYBLOB`, `BLOB`, `MEDIUMBLOB`, `LONGBLOB` | Armazenam dados binários como imagens, arquivos, etc. | Foto de perfil: `BLOB` |
|              | **Coleção** | `ENUM`, `SET` | Valores pré-definidos (ENUM = um valor; SET = múltiplos valores). | `ENUM('masculino','feminino')` |
| **Espacial** | - | `GEOMETRY`, `POINT`, `POLYGON`, `MULTIPOLYGON` | Dados geoespaciais (localizações, áreas, formas). | Localização no mapa: `POINT` |

---

## Resumo Rápido
- **Numérico:** números inteiros, decimais e valores lógicos.
- **Data/Tempo:** datas, horas e anos.
- **Literal:** textos curtos, longos, dados binários e listas pré-definidas.
- **Espacial:** coordenadas e formas geográficas.

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

## 📚 Guia de Criação de Banco de Dados e Tabelas no MySQL Básico: 

Este guia ensina de forma simples como criar um banco de dados e tabelas no MySQL usando o MySQL Workbench.

🗄️ 1. Como criar um banco de dados
1. Abrir o MySQL Workbench e garantir que o servidor MySQL esteja rodando.
2. Criar o banco de dados digitando:
CREATE DATABASE cadastro;
Obs.: O nome "cadastro" é apenas um exemplo. Não use acentos nem espaços.
3. Executar o comando clicando no ícone de raio (⚡) com o número 1 ou selecionando o código e clicando no mesmo ícone.
4. Confirmar a criação clicando com o botão direito na lista de bancos e escolhendo "Refresh All".

📋 2. Como criar uma tabela
1. Selecionar o banco de dados com:
USE cadastro;
(Se o nome for diferente, substitua por ele.)
2. Criar a tabela digitando:
```
CREATE TABLE pessoas (
    nome VARCHAR(30),
    idade TINYINT,
    sexo CHAR(1),
    peso FLOAT,
    altura FLOAT,
    nacionalidade VARCHAR(20)
);
```
Descrição dos campos:
- VARCHAR(30) → texto de até 30 caracteres (nome)
- TINYINT → número inteiro pequeno (idade)
- CHAR(1) → texto de 1 caractere (M/F)
- FLOAT → número decimal (peso/altura)
- VARCHAR(20) → texto de até 20 caracteres (nacionalidade)
3. Executar o comando clicando no ícone de raio (⚡).
4. Atualizar a lista de tabelas no painel lateral clicando em "Refresh".
5. Verificar os atributos clicando no nome do banco, expandindo "Tables", clicando em "pessoas" e depois em "Columns".

✅ Fluxo resumido:
Criar banco de dados → CREATE DATABASE nome; → Selecionar banco → USE nome; → Criar tabela → CREATE TABLE ... → Verificar no painel lateral.

<img width="953" height="835" alt="02" src="https://github.com/user-attachments/assets/2ebb2843-f44b-4d72-b795-89cc93e1ef5f" />


_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

## 💡Como usar o comando DESCRIBE no MySQL

Depois que você criou a tabela pessoas, para ver os detalhes dos campos dela, você pode usar o comando:

```
DESCRIBE pessoas;
```

Esse comando mostra:

- Nome dos campos (colunas)
- Tipo de dado de cada campo (ex.: VARCHAR, INT)
- Se o campo pode ser NULL (aceita valor vazio ou não)
- Se é chave primária (Primary Key)
- Informações sobre padrão (default) e outras propriedades

**Exemplo:** 

<img width="655" height="173" alt="03" src="https://github.com/user-attachments/assets/fb3bdf46-2499-40d8-88c2-61fae61be1ab" />



_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

## 💡 Como apagar um banco de dados

No **MySQL Workbench**:

- Para apagar um bancos ou tabelas via SQL, use a opção **File > New Query Tab** (Arquivo > Nova aba de consulta).  
- Essa opção abre um editor onde você pode digitar comandos SQL manualmente, como:

```sql
DROP DATABASE cadastro;
```

Após digitar o comando, clique no ícone de raio (⚡) para executar e o banco será apagado.

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

## 💡Melhores práticas para criação de banco de dados no MySQL

```sql
CREATE DATABASE cadastro
DEFAULT CHARACTER SET utf8mb4
DEFAULT COLLATE utf8mb4_general_ci;
```

---

## 📄 Detalhamento do comando

- **CREATE DATABASE cadastro**
  
  Inicializa a criação de um novo banco de dados denominado cadastro, que servirá como container para as tabelas e objetos relacionados.

- **DEFAULT CHARACTER SET utf8mb4**
  
  Estabelece o conjunto de caracteres padrão para o banco de dados.
 
  Essa configuração determina os caracteres que poderão ser armazenados, abrangendo letras, números, símbolos, acentuações e emojis.

  A codificação utf8mb4 é a implementação completa do padrão UTF-8, suportando todo o espectro Unicode, garantindo compatibilidade com caracteres especiais e emojis.
  
  Sua adoção é recomendada para evitar limitações associadas ao charset utf8 tradicional, que não suporta adequadamente caracteres multibyte.

- **DEFAULT COLLATE utf8mb4_general_ci**
  
  Define a regra padrão de ordenação e comparação de dados textuais no banco.
  
  A collation utf8mb4_general_ci realiza comparações insensíveis a maiúsculas e minúsculas (case insensitive), facilitando operações de busca e ordenação que não diferenciam o uso de caixa alta ou baixa.
    
  Além disso, estabelece a sequência alfabética para ordenação de strings dentro do banco de dados.

---

## 📄 Justificativa para as configurações adotadas

- Compatibilidade e abrangência: Garante o suporte completo a caracteres Unicode, incluindo símbolos especiais e emojis, eliminando problemas de armazenamento e exibição.
  
- Consistência nas comparações: Assegura que operações envolvendo texto, como buscas e ordenações, sejam realizadas de forma natural, sem diferenciação entre maiúsculas e minúsculas, promovendo uma melhor experiência para aplicações e usuários.

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
## 📚 Criação do banco de dados com configuração adequada e descrição:

### ✏️ Passo 1 - Criando o banco de dados: 

```
CREATE DATABASE cadastro
DEFAULT CHARACTER SET utf8mb4
DEFAULT COLLATE utf8mb4_general_ci;
use cadastro;

create table pessoas (
id int not null auto_increment,
nome varchar(30) not null,
nascimento date,
sexo enum('M', 'F'),
peso decimal(3,2),
altura decimal(3,2),
nacionalidade varchar(20) default 'Brasil',
primary key (id)
) default charset = utf8mb4;
```

### 💡 **Explicação:**

- `id INT NOT NULL AUTO_INCREMENT:` 

Coluna do tipo inteiro (INT), não aceita valor nulo (NOT NULL), e seu valor aumenta automaticamente (AUTO_INCREMENT) a cada novo registro. Usado como identificador único.

- `nome VARCHAR(30) NOT NULL:`  

Texto variável com até 30 caracteres, obrigatório (não pode ser nulo).

- `nascimento DATE:`  

Data de nascimento, tipo de dado DATE.

- `sexo ENUM('M', 'F'):`  

Campo que aceita só valores pré-definidos: 'M' (masculino) ou 'F' (feminino).

- `peso DECIMAL(3,2):`  

Número decimal com 3 dígitos no total, sendo 2 após a vírgula. Exemplo: 70.50

- `altura DECIMAL(3,2):`  

Mesma definição que peso, para altura.

- `nacionalidade VARCHAR(20) DEFAULT 'Brasil':`  

Texto até 20 caracteres. Se nenhum valor for informado, o padrão será 'Brasil'.

- `PRIMARY KEY (id):`  

Define a coluna id como chave primária, ou seja, identificador único de cada registro.

- `DEFAULT CHARSET = utf8mb4:`  

Define que a tabela usará o charset utf8mb4 para armazenamento de textos.

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

### ✏️ Passo 2 - Incerindo dados no banco de dados: 

```
INSERT INTO pessoas

(id, nome, nascimento, sexo, peso, altura, nacionalidade)

VALUES

(default, 'Nathalia Orleans', '2003-08-02', 'F', 65.3, 1.60, 'Brasil');

```
### 💡 **Explicação:**

- `INSERT INTO pessoas` → indica que você quer inserir dados na tabela chamada `pessoas`.
  
- `(id, nome, nascimento, sexo, peso, altura, nacionalidade)`→ lista de colunas onde os valores serão colocados, na ordem exata.
  
- `VALUES` → palavra-chave que introduz os valores que serão inseridos.

- `default` → para a coluna `id`, significa "usar o valor padrão".

- No caso do `id` que é **AUTO_INCREMENT**, o MySQL vai gerar automaticamente o próximo número disponível.

- `'Nathalia Orleans'` → nome (texto).

- `'2003-08-02` → data de nascimento no formato **YYYY-MM-DD.**

- `'F'` → valor do campo sexo, que no seu caso só pode ser `M` ou `F`.

- `65.3` → peso (número decimal).

- `1.60` → altura (número decimal).

- `'Brasil'` → nacionalidade.
_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
## 📌 Dica muito importante sobre o passo 2, que se refere à inserção de dados no banco de dados:

- No passo número 2, usamos desta forma:

```
INSERT INTO pessoas

(id, nome, nascimento, sexo, peso, altura, nacionalidade)

VALUES

(default, 'Nathalia Orleans', '2003-08-02', 'F', 65.3, 1.60, 'Brasil');
```

- Mas podemos usar desta forma também:

```
INSERT INTO pessoas VALUES

(default, 'Nathalia Orleans', '2003-08-02', 'F', 65.3, 1.60, 'Brasil');
```

- Porque podemos usar desta forma?
- Por que na tabela já criada no banco de dados, está organizada de formar que deve receber as informações inceridas. Como o exemplo abaixo:
  
<img width="208" height="140" alt="06" src="https://github.com/user-attachments/assets/0b245318-ce3e-4252-aceb-06fefab896b3" />

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

## 🗨️ 🗒️Verificando os dados já inseridos na tabela: 

<img width="679" height="108" alt="05" src="https://github.com/user-attachments/assets/6a523e63-abf6-4270-93fb-691f66b06d17" />

- Para verificar os dados inseridos na tabela no banco de dados, vamos usar o comando:

    `SELECT * FROM e o nome da tabela;`
  
    **Exemplo:** `SELECT * FROM pessoas;`

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

## 📌 Comandos DML (Data Manipulation Language) — Manipulação de Dados

| Comando   | Função                                  | Exemplo básico                             |
|-----------|----------------------------------------|-------------------------------------------|
| `SELECT`  | Buscar/consultar dados                  | `SELECT * FROM pessoas;`                   |
| `INSERT`  | Inserir novos registros                 | `INSERT INTO pessoas (nome) VALUES ('Ana');` |
| `UPDATE`  | Atualizar registros existentes          | `UPDATE pessoas SET peso = 70 WHERE id=1;` |
| `DELETE`  | Apagar registros                       | `DELETE FROM pessoas WHERE id=1;`         |
| `CALL`    | Executar uma procedure armazenada       | `CALL minha_procedure();`                  |
| `EXPLAIN` | Analisar consulta (não altera dados)   | `EXPLAIN SELECT * FROM pessoas;`          |

---

## 📌 Comandos DDL (Data Definition Language) — Definição da Estrutura

| Comando    | Função                                  | Exemplo básico                                     |
|------------|----------------------------------------|---------------------------------------------------|
| `CREATE`   | Criar banco, tabela, índice, view      | `CREATE TABLE pessoas (...);`                      |
| `ALTER`    | Modificar estrutura de tabelas         | `ALTER TABLE pessoas ADD COLUMN email VARCHAR(50);` |
| `DROP`     | Apagar banco, tabela, índice           | `DROP TABLE pessoas;`                              |
| `TRUNCATE` | Apagar dados de uma tabela (rápido)   | `TRUNCATE TABLE pessoas;`                          |
| `RENAME`   | Renomear tabelas, colunas              | `RENAME TABLE pessoas TO clientes;`               |
| `COMMENT`  | Adicionar comentários (metadados)      | Usado em tabelas/colunas para documentação        |

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

# 📌 Guia Rápido de Comandos MySQL

Este é um resumo dos principais comandos do MySQL, separados por categorias (DDL, DML, DQL, DCL e TCL).

---

## 🏗️ 1. DDL (Data Definition Language) – Estrutura do banco

| Comando | Função |
|---------|--------|
| `CREATE DATABASE nome;` | Cria um banco de dados |
| `DROP DATABASE nome;` | Exclui um banco de dados |
| `USE nome;` | Seleciona o banco de dados |
| `CREATE TABLE nome (...);` | Cria uma tabela |
| `DROP TABLE nome;` | Exclui uma tabela |
| `ALTER TABLE nome ADD coluna tipo;` | Adiciona uma coluna |
| `ALTER TABLE nome DROP coluna;` | Remove uma coluna |
| `ALTER TABLE nome MODIFY coluna tipo;` | Modifica tipo de coluna |
| `ALTER TABLE nome CHANGE coluna_antiga nova_coluna tipo;` | Renomeia coluna |
| `ALTER TABLE nome RENAME TO novo_nome;` | Renomeia a tabela |
| `TRUNCATE TABLE nome;` | Apaga todos os dados, mas mantém a tabela |

---

## 📝 2. DML (Data Manipulation Language) – Manipulação de dados

| Comando | Função |
|---------|--------|
| `INSERT INTO tabela (...) VALUES (...);` | Insere dados |
| `UPDATE tabela SET coluna = valor WHERE condição;` | Atualiza dados |
| `DELETE FROM tabela WHERE condição;` | Exclui registros |

---

## 🔍 3. DQL (Data Query Language) – Consultas

| Comando | Função |
|---------|--------|
| `SELECT * FROM tabela;` | Seleciona todos os registros |
| `SELECT coluna1, coluna2 FROM tabela;` | Seleciona colunas específicas |
| `WHERE` | Filtra registros |
| `ORDER BY coluna ASC|DESC;` - Ordena resultados|
| `GROUP BY coluna;` | Agrupa registros |
| `HAVING` | Filtra após agrupamento |
| `LIMIT n;` | Limita registros retornados |

🔹 **Funções úteis em consultas**:
- `COUNT(*)` → Conta registros  
- `SUM(coluna)` → Soma valores  
- `AVG(coluna)` → Média  
- `MAX(coluna)` → Maior valor  
- `MIN(coluna)` → Menor valor  

---

## 🔐 4. DCL (Data Control Language) – Controle de acesso

| Comando | Função |
|---------|--------|
| `CREATE USER 'usuario'@'localhost' IDENTIFIED BY 'senha';` | Cria usuário |
| `GRANT ALL PRIVILEGES ON banco.* TO 'usuario'@'localhost';` | Concede permissões |
| `REVOKE` | Remove permissões |
| `DROP USER 'usuario'@'localhost';` | Exclui usuário |

---

## 🔄 5. TCL (Transaction Control Language) – Transações

| Comando | Função |
|---------|--------|
| `START TRANSACTION;` | Inicia transação |
| `COMMIT;` | Confirma alterações |
| `ROLLBACK;` | Desfaz alterações |
| `SAVEPOINT nome;` | Cria ponto de restauração |
| `RELEASE SAVEPOINT nome;` | Remove ponto de restauração |

---

## 📚 6. Outros comandos úteis

| Comando | Função |
|---------|--------|
| `DESCRIBE tabela;` | Mostra estrutura da tabela |
| `SHOW COLUMNS FROM tabela;` | Lista colunas da tabela |
| `SHOW TABLES;` | Lista todas as tabelas do banco |
| `SHOW DATABASES;` | Lista todos os bancos de dados |
| `SHOW CREATE TABLE tabela;` | Mostra SQL de criação da tabela |
| `SHOW PROCESSLIST;` | Lista processos em execução |

---

## 🚀 Resumão

- **DDL** → estrutura (banco, tabelas, colunas)  
- **DML** → dados (inserir, atualizar, apagar)  
- **DQL** → consultas (buscar e filtrar)  
- **DCL** → permissões (usuários e acessos)  
- **TCL** → transações (commit, rollback, savepoint)  

---

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

# Manipulação de Registros 
### Podemos chamar também de: Manipulando Linhas ou Manipulando Tuplas. 

<img width="952" height="687" alt="01" src="https://github.com/user-attachments/assets/aadff730-7764-41ee-9644-487fb9ac1e73" />

## Vamos alterar algumas palavras das tabelas que estão escritas de forma errada:

<img width="782" height="386" alt="02" src="https://github.com/user-attachments/assets/1c554ed1-625e-4c41-aeb0-f172b282ce48" />

#Comandos usados para alterar dados em uma tabela:

## Update de registros em MySQL

`update cursos`
-- Atualiza registros da tabela 'cursos'.

`set nome = 'HTML5'`  
-- Define o novo valor para a coluna 'nome', substituindo o valor antigo.

`where idcurso = '1'`  
-- Especifica qual registro será alterado, filtrando pelo ID igual a 1.

`select * from cursos`
-- Recupera todos os registros da tabela 'cursos' para verificar as alterações.
_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

`update cursos` 
-- Atualiza registros da tabela 'cursos'.

`set nome = 'PHP', ano = '2015'`  
-- Define novos valores para as colunas 'nome' e 'ano'.

`where idcurso = '4'`  
-- Especifica que a alteração será feita no registro com ID 4.

`select * from cursos`  
-- Recupera todos os registros da tabela 'cursos' para verificar as alterações.


<img width="295" height="105" alt="03" src="https://github.com/user-attachments/assets/0e821ed8-6fbc-48fb-b0ab-649d5c217259" />

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

# Removendo uma linha da tabela: 

`delete from cursos`  
-- Remove registros da tabela 'cursos'.

`where idcurso = '8'` 
-- Especifica qual registro será deletado, filtrando pelo ID igual a 8.

`select * from cursos`  
-- Recupera todos os registros da tabela 'cursos' para verificar como ficou após a exclusão.










