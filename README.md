# ATV_SQL_2304

### Código SQL:

```sql
-- Criação da tabela Clientes
CREATE TABLE Clientes (
codigo INT PRIMARY KEY AUTO_INCREMENT,
nome VARCHAR(100),
endereco VARCHAR(255),
telefone VARCHAR(20),
email VARCHAR(100),
cpf VARCHAR(14)
);

-- Criação da tabela Carros
CREATE TABLE Carros (
    codigo INT PRIMARY KEY AUTO_INCREMENT,
    marca VARCHAR(50),
    modelo VARCHAR(50),
    ano INT,
    cor VARCHAR(20),
    placa VARCHAR(10),
    combustivel VARCHAR(20),
    disponibilidade BOOLEAN,
    preco_dia DECIMAL(10, 2),
    preco_km DECIMAL(10, 2)
);

-- Criacao da tabela Locacoes
CREATE TABLE Locacoes (
    codigo INT PRIMARY KEY AUTO_INCREMENT,
    cod_cliente INT,
    cod_carro INT,
    data_retirada DATE,
    data_devolucao DATE,
    km_inicial DECIMAL(10, 2),
    km_final DECIMAL(10, 2),
    local VARCHAR(100),
    preco_final DECIMAL(10, 2),
    metodoPagamento VARCHAR(50),
    FOREIGN KEY (cod_cliente) REFERENCES Clientes(codigo),
    FOREIGN KEY (cod_carro) REFERENCES Carros(codigo)
);

-- Inserir dados na tabela Clientes
INSERT INTO Clientes (nome, endereco, telefone, email, cpf)
VALUES
    ('João Silva', 'Rua A, 123', '(11) 1234-5678', 'joao@email.com', '123.456.789-10'),
    ('Maria Santos', 'Av. B, 456', '(21) 9876-5432', 'maria@email.com', '987.654.321-01'),
    ('Carlos Oliveira', 'Rua C, 789', '(31) 4567-8901', 'carlos@email.com', '456.789.123-45'),
    ('Ana Lima', 'Rua D, 987', '(41) 6543-2109', 'ana@email.com', '789.123.456-78'),
    ('Pedro Souza', 'Av. E, 321', '(51) 8901-2345', 'pedro@email.com', '321.654.987-10'),
    ('Fernanda Costa', 'Rua F, 654', '(61) 2109-8765', 'fernanda@email.com', '654.987.321-54'),
    ('Rafael Santos', 'Av. G, 987', '(71) 5432-1098', 'rafael@email.com', '987.321.654-32'),
    ('Camila Almeida', 'Rua H, 234', '(81) 8765-4321', 'camila@email.com', '456.789.123-98'),
    ('Lucas Oliveira', 'Av. I, 567', '(91) 2109-8765', 'lucas@email.com', '123.456.789-65'),
    ('Mariana Silva', 'Rua J, 876', '(101) 5432-0987', 'mariana@email.com', '321.654.987-32');

-- Inserir dados na tabela Carros
INSERT INTO Carros (marca, modelo, ano, cor, placa, combustivel, disponibilidade, preco_dia, preco_km)
VALUES
    ('Toyota', 'Corolla', 2022, 'Preto', 'ABC-1234', 'Gasolina', true, 100.00, 0.50),
    ('Honda', 'Civic', 2023, 'Prata', 'XYZ-5678', 'Flex', true, 120.00, 0.60),
    ('Ford', 'Fiesta', 2021, 'Branco', 'DEF-9012', 'Álcool', true, 80.00, 0.40),
    ('Chevrolet', 'Onix', 2022, 'Vermelho', 'GHI-3456', 'Gasolina', false, 90.00, 0.45),
    ('Volkswagen', 'Gol', 2020, 'Azul', 'JKL-7890', 'Flex', true, 70.00, 0.35),
    ('Fiat', 'Uno', 2023, 'Verde', 'MNO-2345', 'Flex', true, 60.00, 0.30),
    ('Hyundai', 'HB20', 2022, 'Prata', 'PQR-6789', 'Flex', true, 85.00, 0.42),
    ('Renault', 'Kwid', 2021, 'Azul', 'STU-1234', 'Álcool', true, 75.00, 0.38),
    ('Nissan', 'March', 2023, 'Vermelho', 'VWX-5678', 'Gasolina', true, 95.00, 0.48),
    ('Chevrolet', 'Tracker', 2022, 'Cinza', 'YZA-9012', 'Flex', false, 110.00, 0.55),
    ('Volkswagen', 'Virtus', 2021, 'Preto', 'BCD-2345', 'Álcool', true, 85.00, 0.42),
    ('Toyota', 'Yaris', 2023, 'Branco', 'EFG-6789', 'Flex', true, 100.00, 0.50),
    ('Honda', 'Fit', 2022, 'Azul', 'HIJ-0123', 'Gasolina', true, 95.00, 0.48),
    ('Ford', 'Ka', 2021, 'Vermelho', 'KLM-4567', 'Flex', true, 75.00, 0.38),
    ('Fiat', 'Argo', 2022, 'Prata', 'NOP-8901', 'Álcool', false, 90.00, 0.45),
    ('Hyundai', 'Creta', 2023, 'Preto', 'QRS-2345', 'Gasolina', true, 115.00, 0.58),
    ('Renault', 'Sandero', 2021, 'Branco', 'TUV-6789', 'Flex', true, 80.00, 0.40),
    ('Nissan', 'Versa', 2022, 'Cinza', 'WXY-0123', 'Flex', true, 90.00, 0.45),
    ('Chevrolet', 'S10', 2023, 'Prata', 'ZAB-4567', 'Diesel', true, 150.00, 0.75),
    ('Volkswagen', 'T-Cross', 2021, 'Azul', 'BCD-8901', 'Flex', true, 105.00, 0.53);

-- Inserir dados na tabela Locacoes
INSERT INTO Locacoes (cod_cliente, cod_carro, data_retirada, data_devolucao, km_inicial, km_final, local, preco_final, metodoPagamento)
VALUES
    (1, 1, '2024-04-23', '2024-04-25', 100.00, 200.00, 'Aeroporto', 250.00, 'Cartão de Crédito'),
    (2, 2, '2024-04-25', '2024-04-28', 80.00, 300.00, 'Centro', 350.00, 'Dinheiro'),
    (3, 3, '2024-04-26', '2024-04-30', 120.00, 400.00, 'Rodoviária', 400.00, 'Cartão de Débito'),
    (4, 4, '2024-04-27', '2024-04-29', 90.00, 250.00, 'Hotel', 300.00, 'Transferência Bancária'),
    (5, 5, '2024-04-28', '2024-05-01', 150.00, 350.00, 'Residência', 450.00, 'Cheque');
```

### Exercícios:

```sql
-- Ex 1
SELECT * FROM Carros;

-- Ex 2
SELECT * FROM Locacoes WHERE cod_carro = 1;

-- Ex 3
SELECT Locacoes.*, Clientes.nome AS nome_cliente, Clientes.telefone
FROM Locacoes
JOIN Carros ON Locacoes.cod_carro = Carros.codigo
JOIN Clientes ON Locacoes.cod_cliente = Clientes.codigo
WHERE Carros.combustivel = 'Gasolina';

-- Ex 4
SELECT Carros.*
FROM Carros
JOIN Locacoes ON Carros.codigo = Locacoes.cod_carro
WHERE Carros.disponibilidade = "INDISPONÍVEL";

-- Ex 5
DELIMITER //

CREATE PROCEDURE ConsultarLocacoesPorCodigoCarro(IN codigo_carro_param INT)
BEGIN
    SELECT *
    FROM Locacoes
    WHERE cod_carro = codigo_carro_param;
END//

DELIMITER ;

CALL ConsultarLocacoesPorCodigoCarro(1);

-- Ex 6
DELIMITER //

CREATE PROCEDURE AdicionarNovoCarro(
    IN marca_param VARCHAR(50),
    IN modelo_param VARCHAR(50),
    IN ano_param INT,
    IN cor_param VARCHAR(20),
    IN placa_param VARCHAR(10),
    IN combustivel_param VARCHAR(20),
    IN disponibilidade_param BOOLEAN,
    IN preco_dia_param DECIMAL(10, 2),
    IN preco_km_param DECIMAL(10, 2)
)
BEGIN
    INSERT INTO Carros (marca, modelo, ano, cor, placa, combustivel, disponibilidade, preco_dia, preco_km)
    VALUES (marca_param, modelo_param, ano_param, cor_param, placa_param, combustivel_param, disponibilidade_param, preco_dia_param, preco_km_param);
END//

DELIMITER ;

CALL AdicionarNovoCarro('Toyota', 'Corolla', 2024, 'Preto', 'ABC-5678', 'Gasolina', TRUE, 100.00, 0.50);
```
