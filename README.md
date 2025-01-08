
# BackEnd for FrontEnd (BFF) com NestJS | Friends & Stephen King
## 🎯 Objetivo

O objetivo deste repositório é utilizar APIs públicas disponibilizadas pela comunidade de desenvolvimento de *software* para construir um BFF usando NestJS com *Clean Architecture* com variados níveis de complexidade em suas *endpoints*.


## ❓ Justificativa

Os participantes deste repositório lançaram mão de desenvolver este BFF usando NestJS como forma de desenvolvimento pessoal em habilidades com as tecnologias abordadas.


## 👤 Participantes

- Guilherme Melo
 	- [GitHub](https://github.com/Gmelo52)
	- [E-mail pessoal](mailto:guilherme52melo@gmail.com)
	- [LinkedIn](https://www.linkedin.com/in/gmelo52)
- Leonardo Wagner
 	- [GitHub](https://github.com/LeoHacklaender)
	- [E-mail pessoal](mailto:nortonhw@gmail.com)
	- [LinkedIn](https://www.linkedin.com/in/leonardo-hacklaender-wagner-35784aa4)
- Leonardo Zuin
 	- [GitHub](https://github.com/zuinl)
	- [E-mail pessoal](mailto:leonardosoareszuin@gmail.com)
	- [LinkedIn](https://www.linkedin.com/in/lzuin)


## 🧑‍💻 Tecnologias utilizadas

- [Nest JS](https://nestjs.com/)


## 📡 APIs

As APIs utilizadas neste repositório são:
- [Friends API](https://github.com/dmtrxw/friends-episodes-api) (série de televisão);
- [Stephen King API](https://stephen-king-api.onrender.com/) (autor de livros de terror);
- [Fatos Inúteis API](https://uselessfacts.jsph.pl/).


## ⛓️ Endpoints disponibilizadas

Serão disponibilizadas *endpoints* completamente aleatórias, sem qualquer significado válido, mantendo anonimato e randominização de dados. Elas serão separadas por nível de complexidade (baixo, médio, alto) com o objetivo de auxiliar nos estudos de cada caso. Segue abaixo lista de *endpoints* disponibilizadas:


### Complexidade baixa

- **GET**: /api/friends/seasons/{*seasonId*}/episodes -> **Guilherme Melo**
	- Descrição: listagem de episódios de uma temporada
	- Path parameters:
		- *seasonId*: ID da temporada da série (de 1 a 10);
	- Response: uma lista de objetos [**Episódio**](#entities)

- **GET**: /api/friends/seasons/{*seasonId*}/episodes/{*episodeId*}
	- Descrição: coleta de um episódio da temporada
	- Path parameters:
		- *seasonId*: ID da temporada da série (de 1 a 10);
		- *episodeId*: ID do episódio da série (de 1 a 24);
	- Response: um objeto [**Episódio**](#entities)

- **GET**: /api/friends/random
	- Descrição: coleta de um episódio aleatório, de qualquer temporada
	- Response: um objeto [**Episódio**](#entities)


### Complexidade média


- **GET**: /api/friends/seasons/{*seasonId*}/episodes/{*episodeId*}/villains -> **Guilherme Melo**
	- Descrição: coleta de um episódio de uma temporada com uma sugestão de vilão de Stephen King a ser adicionado
	- Path parameters:
		- *seasonId*: ID da temporada da série (de 1 a 10);
		- *episodeId*: ID do episódio da série (de 1 a 24);
	- Response: um objeto [**Episódio**](#entities) com campo adicional *suggested_villain* (nome do vilão sugerido)

- **GET**: /api/friends/seasons/{*seasonId*}/episodes/{*episodeId*}/short-stories
	- Descrição: coleta de um episódio de uma temporada com uma sugestão de uma história curta do Stephen King para um *crossover*
	- Path parameters:
		- *seasonId*: ID da temporada da série (de 1 a 10);
		- *episodeId*: ID do episódio da série (de 1 a 24);
	- Response: um objeto [**Episódio**](#entities) com campo adicional *suggested_short_story* (nome da história curta)

- **GET**: /api/friends/seasons/{*seasonId*}/episodes/{*episodeId*}/books
	- Descrição: coleta de um episódio de uma temporada com uma sugestão de um livro do Stephen King para um *crossover*
	- Path parameters:
		- *seasonId*: ID da temporada da série (de 1 a 10);
		- *episodeId*: ID do episódio da série (de 1 a 24);
	- Response: um objeto [**Episódio**](#entities) com campo adicional *suggested_book* (nome do livro)


### Complexidade alta

- **GET**: /api/friends/seasons/{*seasonId*}/episodes/{*episodeId*}/villains/{*villainId*}/useless-fact
	- Descrição: coleta de um episódio de uma temporada com uma sugestão de vilão de Stephen King a ser adicionado com uma fala específica (fato inútil)
	- Path parameters:
		- *seasonId*: ID da temporada da série (de 1 a 10);
		- *episodeId*: ID do episódio da série (de 1 a 24);
		- *villainId*: ID do vilão do Stephen King (de 1 a 115).
	- Response: um objeto [**Episódio**](#entities) com campos adicionais *suggested_villain* (nome do vilão sugerido) e *suggested_useless_fact* (o fato inútil sugerido)

- **GET**: /api/friends/seasons/{*seasonId*}/episodes/{*episodeId*}/short-stories/{*shortStoryId*}/useless-fact
	- Descrição: coleta de um episódio de uma temporada com uma sugestão de história curta de Stephen King a ser adicionado com uma fala específica (fato inútil)
	- Path parameters:
		- *seasonId*: ID da temporada da série (de 1 a 10);
		- *episodeId*: ID do episódio da série (de 1 a 24);
		- *shortStoryId*: ID da história curta do Stephen King (de 1 a 212).
	- Response: um objeto [**Episódio**](#entities) com campos adicionais *suggested_short_story* (nome da história curta sugerida) e *suggested_useless_fact* (o fato inútil sugerido)

- **GET**: /api/friends/seasons/{*seasonId*}/episodes/{*episodeId*}/books/{*bookId*}/useless-fact -> **Guilherme Melo**
	- Descrição: coleta de um episódio de uma temporada com uma sugestão de livro de Stephen King a ser adicionado com uma fala específica (fato inútil)
	- Path parameters:
		- *seasonId*: ID da temporada da série (de 1 a 10);
		- *episodeId*: ID do episódio da série (de 1 a 24);
		- *bookId*: ID do livro do Stephen King (de 1 a 63).
	- Response: um objeto [**Episódio**](#entities) com campos adicionais *suggested_book* (nome do livro sugerido) e *suggested_useless_fact* (o fato inútil sugerido)


### *Entities*
- Episódio
```
{
    "code": "string",
    "season": "number",
    "no_in_season": "number",
    "title": "string",
    "synopsis": "string",
    "image_url": "string"
}
```


## 📬 Como usar
TODO
