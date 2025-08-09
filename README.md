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

### Como criar um banco de dados? 

- Para criar um banco de dados vamos dar o seguinte comando:
  
  ```
  create database (aqui tem que ser o nome do banco que vai ser, Ex: cadastro);
  ```
  
- Após o comando acima, vamos clicar no raio com o número 1.
  
- Após o banco ser criado, vamos criar tabelas.
  
_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
  ### Como criar uma tabela? 

  - Para criar uma tabela, vamos dar o seguinte comando:
    
  - create table pessoas (aquidentro vai os atributos);
  - 
