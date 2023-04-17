O DBA é o profissional responsável por administrar o ambiente de banco de dados, e cabe a ele criar os bancos, mas isso funciona quando a gente está falando de uma empresa coorporativa, grande.

Se a gente estiver falando de empresas pequenas ou até mesmo de bancos de dados muito pontuais, muito departamentais, onde tem um servidor que foi comprado exclusivamente para colocar esse banco de dados, aí o próprio profissional que vai realmente criar as tabelas, os índices, as chaves primárias, a estrutura para receber os dados, também pode criar o banco de dados.

Então, apesar de que normalmente isso é uma tarefa do DBA e não do analista que está projetando o banco, a gente vai ver um pouquinho sobre como criar banco de dados no MySQL.

<br>

## Criando um banco

- Usar create database ou create schema
- Posso ter a cláusula if not exist, ou seja, se eu quiser criar um dado que já existe, se eu tiver a cláusula if not exist, não vai dar erro.
- O nome do banco, dependendo do ambiente ele é case sensitive ou não.
- A especificação da criação. Essa especificação são informações que estão relacionadas com a criptografia do banco, se ele vai ter ou não uma criptografia interna, e sobre o character set, ou seja, quais são os caracteres que o banco de dados vai suportar. 
- Se não especificar ele usará a padronização do ambiente operacional onde o banco está instalado.
#### Sintaxe do comando
```
CREATE {DATABASE|SCHEMA}[IF NOT EXISTS] DB_NAME
[ CREATE_ESPECIFICATION]...

CREATE_ESPECIFICATION:
[DEFAULT] CHARACTER SET [=] CHARSET_NAME
[DEFAULT] COLLATE [=] COLLATION_NAME
[DEFAULT] ENCRYPTION [=] {'y' | 'N'}

A CHARACTER SET CLAUSULA ESPECIFICA O CONJUNTO DE CARACTERES DO BANCO DE DADOS PADRÃO
A DEFAULT ENCRYPTION CLAUSULA INTRODUZIDA NO MYSQL8 PARA CRIPTOGRAFIA DE BANCO DE DADOS PADRÃO,
QUE É HERDADA PELAS TABELAS DO BANCO DE DADOS
```

## Apagando um banco
#### Sintaxe do comando
```
DROP {DATABASE|SCHEMA}[IF NOT EXISTS] DB_NAME
```
### Exemplos: 
```
CREATE DATABASE vendas_sucos;

CREATE DATABASE vendas_sucos DEFAULT CHARACTER SET utf8;

CREATE DATABASE IF NOT EXISTS vendas_sucos;

DROP DATABASE IF NOT EXISTS vendas_sucos;
```