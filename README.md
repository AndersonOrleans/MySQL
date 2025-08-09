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

## 📚 Guia de Criação de Banco de Dados e Tabelas no MySQL

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

## Como usar o comando DESCRIBE no MySQL

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

  
