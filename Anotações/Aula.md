#Aula 2
    -Revisão da utlima aula
    -estudo sobre tipos de dados, restrições - constraints

    Exercicio da Aula:

    -- Cirando meu Banco
CREATE DATABASE biblioteca;
USE biblioteca;

drop table Autor;
drop table Livro;

CREATE table Autor(
id_autor int primary Key,
nome varchar(150) not null,
nacionalidade varchar(74)  null
);

CREATE table Livro(
id_livro int primary Key,
titulo TEXT not null,
ano_publicacao YEAR not null,
fk_id_autor int ,
fk_id_editora int ,
FOREIGN KEY (fk_id_autor) REFERENCES Autor(id_autor),
foreign key(fk_id_editora) references Editora(id_editora)
);

create table Editora(
id_editora INT primary key,
nome varchar(100) not null,
cidade varchar(50) not null,
site varchar(100),
ano_fundacao year
);


ALTER TABLE Livro
ADD genero varchar(100);

Alter TABLE Autor
MODIFY COLUMN nacionalidade char(5);

alter table Livro -- rever
change id ISBN varchar(20);

# Aula 1
- Explicação inicial e como funcionará a materia
- Revisão de banco de dados
- Modelo Entidade-Relacionamento Conceitual
- Tipos de cardinalidade
- 
     ## EX1.
  ``sql
      /* Lógico_2: */
      CREATE TABLE Funcionario (
          Cpf CHAR(14) PRIMARY KEY,
          Nome VARCHAR(100),
          DataNascimento DATE,
          Salario DECIMAL(10,2),
          Rua VARCHAR(100),
          Cep CHAR(9),
          Numero INTEGER,
          complemento VARCHAR(100)
      );
  ``



    <img width="940" height="296" alt="print" src="https://github.com/user-attachments/assets/ff2cb3ea-7efe-45c9-84a7-9ecdfc1594fc" />

  EX2.
  <img width="912" height="562" alt="captura 1" src="https://github.com/user-attachments/assets/8de837a5-2a49-412f-8f27-5efb00523124" />

  


  ## OBS:
  - 1.O banco de de dados é mais usado, pois ajuda a evitar a dupluicidade de dados
  
