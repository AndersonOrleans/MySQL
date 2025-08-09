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
## 📚 Criação do banco de dados com configuração adequada e descrição da tabela: 

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

### 💡 **Explicando coluna:**

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





