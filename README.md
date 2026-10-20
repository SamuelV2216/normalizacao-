
# Normalização de Banco de Dados: 1FN, 2FN e 3FN

Artigo técnico sobre como transformar uma planilha de pedidos com dados repetidos
em um modelo relacional organizado, usando 1FN, 2FN e 3FN.

**Página publicada:** [colocar link após ativar o GitHub Pages]

## Autores

- Samuel Vitor — [GitHub](https://github.com/SamuelV2216)
- Ericles Gabriel — [GitHub](https://github.com/ericlesgabriel200408)
- Vinicius Ian — [GitHub](https://github.com/Vinicius-ian007)
- Johann do Santos  — [GitHub](https://github.com/johanndossantos15-glitch)
- Samuel Silva — [GitHub](https://github.com/samuel0072562)

## Tema

Normalização de uma planilha de pedidos de uma loja, separando clientes, pedidos,
produtos e itens de pedido para evitar redundância e anomalias de inserção,
atualização e exclusão.

## Tecnologias

- HTML5
- CSS3
- PostgreSQL 16

## Como executar os scripts

1. Instale o PostgreSQL 16.
2. Crie um banco de dados vazio.
3. Execute o arquivo `sql/normalizacao.sql`.
4. Execute as consultas de demonstração indicadas no artigo.

## Estrutura do projeto

- `index.html` — artigo técnico
- `style.css` — estilos da página
- `sql/normalizacao.sql` — criação das tabelas e inserção de dados fictícios
- `img/` — figuras e imagens dos autores

## Decisões do grupo

- Usamos PostgreSQL 16 por ser gratuito, bem documentado e amplamente utilizado.
- Explicamos 1FN, 2FN e 3FN com um único caso de loja.
- Apresentamos o problema antes da teoria.
- Não incluímos vídeos.

## Referências

- Codd, E. F. *A Relational Model of Data for Large Shared Data Banks*. Communications of the ACM, 1970.
- Elmasri, R.; Navathe, S. B. *Sistemas de banco de dados*. 7. ed. Pearson, 2018.
- [Documentação do PostgreSQL](https://www.postgresql.org/docs/current/ddl.html)
- [Alura — Normalização de banco de dados](https://www.alura.com.br/artigos/normalizacao-banco-de-dados-estrutura)

## Licença

MIT
