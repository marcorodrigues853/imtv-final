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
