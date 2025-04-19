"# Easy-Learn" 
/*script bd for SQL 

CREATE DATABASE IF NOT EXISTS PlataformaCursos;
USE PlataformaCursos;

-- Tabela Usuário
CREATE TABLE Usuario (
    id_usuario INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    sobrenome VARCHAR(100),
    email VARCHAR(100),
    CPF VARCHAR(14),
    senha VARCHAR(255),
    foto TEXT
);

-- Tabela Cursos
CREATE TABLE Cursos (
    id_cursos INT AUTO_INCREMENT PRIMARY KEY,
    duracao VARCHAR(50),
    tutor VARCHAR(100),
    documentacao TEXT,
    videos TEXT,
    certificado BOOLEAN
);

-- Tabela Cursos_destaque
CREATE TABLE Cursos_destaque (
    id_cursos_destaque INT AUTO_INCREMENT PRIMARY KEY,
    duracao VARCHAR(50),
    tutor VARCHAR(100),
    documentacao TEXT,
    videos TEXT,
    certificado BOOLEAN,
    id_cursos INT,
    FOREIGN KEY (id_cursos) REFERENCES Cursos(id_cursos)
);

-- Tabela Meus_Cursos
CREATE TABLE Meus_Cursos (
    id_meus_cursos INT AUTO_INCREMENT PRIMARY KEY,
    id_usuario INT,
    FOREIGN KEY (id_usuario) REFERENCES Usuario(id_usuario)
);

-- Tabela Progresso
CREATE TABLE Progresso (
    id_progresso INT AUTO_INCREMENT PRIMARY KEY,
    meus_cursos_id INT,
    tempo_na_plataforma TIME,
    cursos_salvos TEXT,
    certificados TEXT,
    minhas_premiacoes TEXT,
    FOREIGN KEY (meus_cursos_id) REFERENCES Meus_Cursos(id_meus_cursos)
);

-- Tabela Professores
CREATE TABLE Professores (
    id_professores INT AUTO_INCREMENT PRIMARY KEY,
    materia VARCHAR(100)
);

-- Tabela Cursos_professor
CREATE TABLE Cursos_professor (
    id_cursos_professor INT AUTO_INCREMENT PRIMARY KEY,
    id_professor INT,
    id_curso INT,
    documentacao_professor TEXT,
    FOREIGN KEY (id_professor) REFERENCES Professores(id_professores),
    FOREIGN KEY (id_curso) REFERENCES Cursos(id_cursos)
);

-- Tabela Contato
CREATE TABLE Contato (
    id_contato INT AUTO_INCREMENT PRIMARY KEY,
    id_professor INT,
    email VARCHAR(100),
    FOREIGN KEY (id_professor) REFERENCES Professores(id_professores)
);
*/
/* script by Postgree SQL 
-- Criação do banco de dados
CREATE DATABASE plataforma_cursos;

-- Seleciona o banco para uso (se estiver no psql, você pode usar \c plataforma_cursos)
\c plataforma_cursos;

-- Tabela Usuario
CREATE TABLE Usuario (
    id_usuario SERIAL PRIMARY KEY,
    nome VARCHAR(100),
    sobrenome VARCHAR(100),
    email VARCHAR(100),
    cpf VARCHAR(14),
    senha TEXT,
    foto TEXT
);

-- Tabela Cursos
CREATE TABLE Cursos (
    id_cursos SERIAL PRIMARY KEY,
    duracao VARCHAR(50),
    tutor VARCHAR(100),
    documentacao TEXT,
    videos TEXT,
    certificado BOOLEAN
);

-- Tabela Cursos_destaque
CREATE TABLE Cursos_destaque (
    id_cursos_destaque SERIAL PRIMARY KEY,
    duracao VARCHAR(50),
    tutor VARCHAR(100),
    documentacao TEXT,
    videos TEXT,
    certificado BOOLEAN,
    id_cursos INT REFERENCES Cursos(id_cursos)
);

-- Tabela Meus_Cursos
CREATE TABLE Meus_Cursos (
    id_meus_cursos SERIAL PRIMARY KEY,
    id_usuario INT REFERENCES Usuario(id_usuario)
);

-- Tabela Progresso
CREATE TABLE Progresso (
    id_progresso SERIAL PRIMARY KEY,
    meus_cursos_id INT REFERENCES Meus_Cursos(id_meus_cursos),
    tempo_na_plataforma INTERVAL,
    cursos_salvos TEXT,
    certificados TEXT,
    minhas_premiacoes TEXT
);

-- Tabela Professores
CREATE TABLE Professores (
    id_professores SERIAL PRIMARY KEY,
    materia VARCHAR(100)
);

-- Tabela Cursos_professor
CREATE TABLE Cursos_professor (
    id_cursos_professor SERIAL PRIMARY KEY,
    id_professor INT REFERENCES Professores(id_professores),
    id_curso INT REFERENCES Cursos(id_cursos),
    documentacao_professor TEXT
);

-- Tabela Contato
CREATE TABLE Contato (
    id_contato SERIAL PRIMARY KEY,
    id_professor INT REFERENCES Professores(id_professores),
    email VARCHAR(100)
);
*/