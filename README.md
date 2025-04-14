# Movie & TV Show Catalog - React Exercise

## Project Description
Build a React application that consumes the TMDB API to display movies and TV shows with:
- Category-based navigation
- Detailed view pages
- Smooth routing between sections

## Technical Requirements

### Core Features
- Two main routes:
  - `/movies` - displays movies
  - `/tv` - displays TV shows
- Detail pages:
  - `/movie/:id` - movie details
  - `/tv/:id` - TV show details

### API Endpoints to Implement

#### Movies (`/movies`):
| Category        | Endpoint               | 
|----------------|-----------------------|
| Popular        | `/movie/popular`      |
| Top Rated      | `/movie/top_rated`    |
| Now Playing    | `/movie/now_playing`  |
| Upcoming       | `/movie/upcoming`     |

#### TV Shows (`/tv`):
| Category        | Endpoint               |
|----------------|-----------------------|
| Popular        | `/tv/popular`         |
| Top Rated      | `/tv/top_rated`       |
| On The Air     | `/tv/on_the_air`      |
| Airing Today   | `/tv/airing_today`    |

### Component Structure

#### Listing Page:
- Must display for each item:
  - Poster image
  - Title
  - Rating (vote average)
  - Release date
- Category navigation

#### Detail Page:
- Must show:
  - Main banner
  - Title and overview
  - Technical information
  - Cast list (with photos and characters)
  - Crew information (by department)

## Implementation Guide

1. **API Calls**:
```javascript
const fetchData = async (mediaType, category) => {
  const response = await fetch(
    `https://api.themoviedb.org/3/${mediaType}/${category}`,
    {
      headers: {
        Authorization: `Bearer ${process.env.REACT_APP_TMDB_ACCESS_TOKEN}`
      }
    }
  );
  return await response.json();
};




//NEW

markdown
Copy
# Exercício: Catálogo de Filmes e Séries com React

## Objetivo
Desenvolver uma aplicação React que utiliza a API do The Movie Database (TMDb) para mostrar:

- Listagens de filmes e séries organizadas por categorias
- Páginas detalhadas com informações completas
- Navegação fluida entre secções

## Requisitos Técnicos

### 1. Rotas Obrigatórias
```jsx
// No ficheiro App.jsx
<Routes>
  <Route path="/" element={<HomePage />} />
  <Route path="/filmes" element={<PaginaFilmes />} />
  <Route path="/series" element={<PaginaSeries />} />
  <Route path="/filme/:id" element={<DetalhesFilme />} />
  <Route path="/serie/:id" element={<DetalhesSerie />} />
</Routes>
2. Endpoints da API
Para Filmes (/filmes):
Categoria	Endpoint
Populares	/movie/popular
Melhor Avaliados	/movie/top_rated
Em Exibição	/movie/now_playing
Em Breve	/movie/upcoming
Para Séries (/series):
Categoria	Endpoint
Populares	/tv/popular
Melhor Avaliadas	/tv/top_rated
No Ar	/tv/on_the_air
Em Exibição Hoje	/tv/airing_today
3. Componentes Principais
Página de Listagem:
Elementos obrigatórios por item:

jsx
Copy
<div className="card">
  <img src={poster_path} alt={title} />
  <h3>{title}</h3>
  <div className="rating">⭐ {vote_average}/10</div>
  <p>Data de lançamento: {release_date}</p>
</div>
Página de Detalhes:
Elementos obrigatórios:

jsx
Copy
<div className="detalhes">
  <img src={backdrop_path} alt={title} />
  <h1>{title}</h1>
  <p>{overview}</p>
  
  <div className="elenco">
    {cast.map(ator => (
      <div key={ator.id} className="ator">
        <img src={ator.profile_path} alt={ator.name} />
        <p>{ator.name} como {ator.character}</p>
      </div>
    ))}
  </div>
</div>
Critérios de Avaliação
Funcionalidade (50%)

Todas as rotas implementadas

Categorias funcionais

Paginação básica

Qualidade de Código (30%)

Componentes reutilizáveis

Gestão de estado adequada

Tratamento de erros

Interface (20%)

Design responsivo

Feedback visual durante loading

Navegação intuitiva

Como Entregar
Criar repositório no GitHub com:

Código fonte completo

Ficheiro .gitignore apropriado

README com instruções

Fazer deploy em:

Vercel ou

Netlify

Enviar para avaliação:

Link do repositório

URL da aplicação live

Breve documentação técnica

Configuração Inicial
Instalar dependências:

bash
Copy
npm install react-router-dom axios
Criar ficheiro .env:

env
Copy
REACT_APP_TMDB_API_KEY=sua_chave_aqui
REACT_APP_TMDB_BASE_URL=https://api.themoviedb.org/3
Exemplo de chamada à API:

javascript
Copy
export const getFilmes = async (categoria) => {
  const resposta = await axios.get(
    `${process.env.REACT_APP_TMDB_BASE_URL}/movie/${categoria}`, 
    {
      headers: {
        Authorization: `Bearer ${process.env.REACT_APP_TMDB_API_KEY}`
      }
    }
  );
  return resposta.data.results;
};
Extras (Opcional)
Sistema de pesquisa

Favoritos com localStorage

Modo escuro/claro

Paginação infinita






//new
