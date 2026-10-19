-- =====================================================
-- Artigo: 1FN, 2FN e 3FN
-- SGBD utilizado: PostgreSQL 16
-- Dados totalmente fictícios
-- =====================================================

DROP TABLE IF EXISTS pedido_itens;
DROP TABLE IF EXISTS pedidos;
DROP TABLE IF EXISTS produtos;
DROP TABLE IF EXISTS clientes;

-- 3FN: dados do cliente ficam em uma tabela própria
CREATE TABLE clientes (
  id_cliente SERIAL PRIMARY KEY,
  nome VARCHAR(100) NOT NULL,
  telefone VARCHAR(20)
);

-- 2FN: dados do produto ficam separados dos itens do pedido
CREATE TABLE produtos (
  id_produto SERIAL PRIMARY KEY,
  nome VARCHAR(100) NOT NULL,
  preco NUMERIC(10,2) NOT NULL CHECK (preco >= 0)
);

CREATE TABLE pedidos (
  id_pedido SERIAL PRIMARY KEY,
  id_cliente INT NOT NULL,
  CONSTRAINT fk_pedido_cliente
    FOREIGN KEY (id_cliente) REFERENCES clientes(id_cliente)
);

-- Tabela associativa entre pedido e produto
CREATE TABLE pedido_itens (
  id_pedido INT NOT NULL,
  id_produto INT NOT NULL,
  quantidade INT NOT NULL CHECK (quantidade > 0),
  PRIMARY KEY (id_pedido, id_produto),
  CONSTRAINT fk_item_pedido
    FOREIGN KEY (id_pedido) REFERENCES pedidos(id_pedido),
  CONSTRAINT fk_item_produto
    FOREIGN KEY (id_produto) REFERENCES produtos(id_produto)
);

INSERT INTO clientes (nome, telefone) VALUES
('Ana Souza', '(11) 90000-0001'),
('Bruno Lima', '(11) 90000-0002');

INSERT INTO produtos (nome, preco) VALUES
('Teclado', 150.00),
('Mouse', 80.00),
('Monitor', 900.00);

INSERT INTO pedidos (id_cliente) VALUES
(1), (1), (2);

INSERT INTO pedido_itens (id_pedido, id_produto, quantidade) VALUES
(1, 1, 1),
(2, 2, 2),
(3, 3, 1);

-- Consulta final: pedido com cliente e produto
SELECT p.id_pedido,
       c.nome AS cliente,
       pr.nome AS produto,
       pi.quantidade,
       pr.preco
FROM pedidos p
JOIN clientes c ON c.id_cliente = p.id_cliente
JOIN pedido_itens pi ON pi.id_pedido = p.id_pedido
JOIN produtos pr ON pr.id_produto = pi.id_produto
ORDER BY p.id_pedido;

-- Correção de uma anomalia de atualização:
-- mudamos o telefone em apenas uma linha.
UPDATE clientes
SET telefone = '(11) 90000-0009'
WHERE id_cliente = 1;
