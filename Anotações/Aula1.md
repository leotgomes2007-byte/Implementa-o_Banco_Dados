# Aula 1
- Explicação inicial e como funcionará a materia
- Revisão de banco de dados
    ->Modelo Entidade-Relacionamento Conceitual
    ->Tipos de cardinalidade
      EX1.
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

  EX2.
  <img width="912" height="562" alt="captura 1" src="https://github.com/user-attachments/assets/8de837a5-2a49-412f-8f27-5efb00523124" />

  


  ## OBS:
  - 1.O banco de de dados é mais usado, pois ajuda a evitar a dupluicidade de dados
  - 
