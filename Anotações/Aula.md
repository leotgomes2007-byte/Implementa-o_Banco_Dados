# Aula 2
    -Revisão da utlima aula
    -estudo sobre tipos de dados, restrições - constraints
	
## Exercicio da Aula:  
    
```sql
-- Criando meu banco
CREATE DATABASE biblioteca;
DROP SCHEMA biblioteca;

-- Colocar o banco criado em uso
use biblioteca;

-- Criar o banco
CREATE TABLE Autor ( 
	id INT PRIMARY KEY,
    nome VARCHAR(151) NOT NULL,
    nacionalidade VARCHAR(74)
);

CREATE TABLE Editora(
	id_Editora INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100),
    cidade VARCHAR(50),
    site VARCHAR(100),
    ano_fundacao YEAR
);

CREATE TABLE Livro (
    ISBN CHAR(13) PRIMARY KEY,
    titulo VARCHAR(150) NOT NULL,
    ano_publicacao YEAR,
    fk_id_autor INT,
    fk_id_editora INT,

    FOREIGN KEY (fk_id_autor) REFERENCES Autor(id),
    FOREIGN KEY (fk_id_editora) REFERENCES Editora(id_Editora)
);

-- Remover a tabela livro
DROP TABLE Livro;

-- Adicionando FK via alteração
ALTER TABLE Livro 
ADD CONSTRAINT fk_Autor -- nome da restrição
FOREIGN KEY (fk_id_Autor) REFERENCES Autor (id);

-- Adicionando uma nova coluna na tabela Livro
ALTER TABLE Livro
ADD Genero TEXT; 

ALTER TABLE Autor
ADD COLUMN anoNascimento YEAR;

-- Removendo uma coluna 
ALTER TABLE Livro
DROP COLUMN Genero;

-- Modificar tipo de uma coluna
ALTER TABLE Autor
MODIFY COLUMN nacionalidade CHAR(2);

-- Alterando nome de uma coluna
ALTER TABLE Livro
CHANGE id ISBN VARCHAR(20);

-- Inserir
INSERT INTO Autor (id, nome, nacionalidade, anoNascimento) 
VALUES (1, "Machado de Assis", "Brasileiro", 1939);

INSERT INTO Autor
VALUES (2, "George Orwell", "Britânico", 1903); 

INSERT INTO editora(nome, cidade, site, ano_fundacao)
VALUES ("Companhia das Letras", "São Paulo", "www.cdi.br", 1986), 
	   ("Penguin", "Londres", "www.pg.ldn", 1935);
       
INSERT INTO Livro (titulo, ISBN, ano_publicacao, fk_id_autor, fk_id_editora)
VALUES ("Dom Casmurro", "9874689", 1910, 1, 1), ("1984", "7799654", 1949, 2, 2);

-- Update
UPDATE Autor
SET Autor.nacionalidade = "Brasileiro"
WHERE Autor.id = 2;

SELECT * FROM Livro;
SELECT * FROM Autor;

-- Query
SELECT l.titulo, l.ano_publicacao
FROM Livro as l
WHERE l.titulo LIKE "%Dom";

-- Query
SELECT l.titulo AS "Título", 
	   l.ano_publicacao AS "Ano de publicação", 
	   A.nome AS "Autor", 
	   A.nacionalidade AS "Nacionalidade", 
       CONCAT(A.nome, "/", A.nacionalidade) AS "Autor/Nacionalidade",
       e.nome AS "Editora"
FROM Livro AS l
JOIN Autor AS a ON l.fk_id_autor = A.id
JOIN Editora AS e ON l.fk_id_editora = e.id_editora; 
```

# Aula 1
- Explicação inicial e como funcionará a materia
- Revisão de banco de dados
- Modelo Entidade-Relacionamento Conceitual
- Tipos de cardinalidade
- 
     ## EX1.
  ```sql
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
  ```



    <img width="940" height="296" alt="print" src="https://github.com/user-attachments/assets/ff2cb3ea-7efe-45c9-84a7-9ecdfc1594fc" />

  EX2.
  
  <img width="912" height="562" alt="captura 1" src="https://github.com/user-attachments/assets/8de837a5-2a49-412f-8f27-5efb00523124" />

  


  ## OBS:
  - 1.O banco de de dados é mais usado, pois ajuda a evitar a dupluicidade de dados
  
