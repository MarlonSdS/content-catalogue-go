# content-catalogue-go
Um backend em go para armazenar, categorizar e buscar conteúdos web. Sua função é guardar links de qualquer conteúdo na internet com a possibilidade de marcar corretamente seu tipo (vídeo, artigo, jogo etc) e a sua categoria (notícia, tutorial, tecnologia, etc).

## Objetivo
Isso é um servidor que armazena links em um banco de dados. Qualquer tipo de link, é basicamente um armazém
de favoritos. Será possível salvar além do link várias informações para possibilitar a filtragem posterior. Este projeto é o backend, um servidor go com uma api restfull. Há um outro projeto em react (talvez com next, não decidi ainda) que servirá como frontend. Possívelmente, não decidi ainda, no futuro, pode haver também um frontend não web, mas um app desktop com GUI.

## Tecnologias empregadas
- **Go:** Linguagem de programção principal
- **Gin Gonic:** Framework web
- **PostgreSQL:** Banco de dados
- **Docker:** Tanto o servidor quanto o banco de dados rodarão dentro de containers

## Estrutura de um content
Um content será o objeto principal desse sistema, devendo guardar, além de um link obviamente, também informações 
complementares para busca e filtragem. Este é um esboço de como a tabela principal deve ser:
| Coluna      | Atributos                                                  |
|-------------|------------------------------------------------------------|
| id          | AI, int                                                    |
| name        | text, required                                             |
| type        | [ video \| text \| image \| file \| game \| code \| site ] |
| tags        | text, array                                                |
| category    | int, FK                                                    |
| description | text, optional                                             |
| created_at  | timestamp, auto                                            |
| updated_at  | timestamp                                                  |
| deleted_at  | timestamp                                                  |