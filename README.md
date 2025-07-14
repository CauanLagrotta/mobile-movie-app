<div align="center">
  <div>
    <img src="https://img.shields.io/badge/-React_Native-black?style=for-the-badge&logoColor=white&logo=react&color=61DAFB" alt="React Native" />
    <img src="https://img.shields.io/badge/-Expo-black?style=for-the-badge&logoColor=white&logo=expo&color=000020" alt="Expo" />
    <img src="https://img.shields.io/badge/-TypeScript-black?style=for-the-badge&logoColor=white&logo=typescript&color=3178C6" alt="TypeScript" />
    <img src="https://img.shields.io/badge/-Tailwind_CSS-black?style=for-the-badge&logoColor=white&logo=tailwindcss&color=06B6D4" alt="Tailwind CSS" />
    <img src="https://img.shields.io/badge/-Appwrite-black?style=for-the-badge&logoColor=white&logo=appwrite&color=F02E65" alt="Appwrite" />
  </div>

  <h3 align="center">Um Aplicativo de Busca de Filmes com Pesquisa Avançada</h3>
</div>

## 📋 <a name="table">Índice</a>

1. 🤖 [Introdução](#introduction)

2. ⚙️ [Tecnologias](#tech-stack)

3. 🔋 [Funcionalidades](#features)

4. 🤸 [Início Rápido](#quick-start)

5. 🕸️ [Trechos de Código](#snippets)


## <a name="introduction">🤖 Introdução</a>

Construído com Expo, TypeScript e Tailwind CSS, este aplicativo busca filmes e cria um algoritmo de popularidade usando o Appwrite. Ele oferece aos usuários uma experiência de navegação perfeita, classificando os filmes com base em várias métricas de engajamento. O aplicativo aproveita os princípios modernos de UI/UX para uma interface responsiva e visualmente atraente, garantindo escalabilidade e desempenho do mundo real.


## <a name="tech-stack">⚙️ Tecnologias</a>

- Expo

- React Native

- Appwrite

- TypeScript

- Tailwind CSS

## <a name="features">🔋 Funcionalidades</a>

### Funcionalidades do Aplicativo de Filmes Móvel

👉 **Dados em tempo real**: Busca e exibe dados de filmes em tempo real

👉 **Página Inicial**: Filmes em destaque e para descobrir

👉 **Página de Busca**: Pesquise seus filmes favoritos

👉 **Algoritmo de popularidade**: Rastreia as pesquisas dos usuários para exibir os filmes mais populares

(e muito mais)

e muito mais, incluindo arquitetura de código e reutilização.

## <a name="quick-start">🤸 Início Rápido</a>

Siga estas etapas para configurar o projeto localmente em sua máquina.

**Pré-requisitos**

Certifique-se de ter o seguinte instalado em sua máquina:

- [Git](https://git-scm.com/)

- [Node.js](https://nodejs.org/en)

- [npm](https://www.npmjs.com/) (Node Package Manager)

**Clonando o Repositório**

```bash

git clone https://github.com/adrianhajdin/rn-movie-app.git

cd rn-movie-app

```

**Instalação**

Instale as dependências do projeto usando npm:

```bash

npm install

```

**Configurando Variáveis de Ambiente**

Crie um novo arquivo chamado `.env` na raiz do seu projeto e adicione o seguinte conteúdo:

```env

EXPO_PUBLIC_MOVIE_API_KEY=

EXPO_PUBLIC_APPWRITE_PROJECT_ID=

EXPO_PUBLIC_APPWRITE_DATABASE_ID=

EXPO_PUBLIC_APPWRITE_COLLECTION_ID=



```

Substitua os valores de espaço reservado pela sua chave de API TMDB, ID do projeto Appwrite, ID do banco de dados e ID da coleção. Você pode obter essas credenciais se cadastrando no [Appwrite](https://cloud.appwrite.io/console/login) e [TMDB](https://www.themoviedb.org/login).

**Executando o Projeto**

```bash

npx expo start

```

Abra o aplicativo ExpoGO no seu telefone e escaneie o código QR para visualizar o projeto.

## <a name="snippets">🕸️ Trechos de Código</a>

<details>

<summary><code>tailwind.config.js</code></summary>

```typescript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./app/**/*.{js,jsx,ts,tsx}", "./components/**/*.{js,jsx,ts,tsx}"],
  presets: [require("nativewind/preset")],
  theme: {
    extend: {
      colors: {
        primary: "#030014",
        secondary: "#151312",
        ratingBox: "#221F3D",
        searchBar: "#0F0D23",
        text: "#9CA4AB",
        darkAccent: "#AB8BFF",
        accentText: "#A8B5DB",
        secondaryText: "#D6C7FF",
      },
    },
  },
  plugins: [],
};
```

</details>

<details>

<summary><code>app/globals.css</code></summary>

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

</details>

<details>

<summary><code>interfaces/interfaces.d.ts</code></summary>

```typescript
interface Movie {
  id: number;
  title: string;
  adult: boolean;
  backdrop_path: string;
  genre_ids: number[];
  original_language: string;
  original_title: string;
  overview: string;
  popularity: number;
  poster_path: string;
  release_date: string;
  video: boolean;
  vote_average: number;
  vote_count: number;
}

interface TrendingMovie {
  searchTerm: string;
  movie_id: number;
  title: string;
  count: number;
  poster_url: string;
}

interface MovieDetails {
  adult: boolean;
  backdrop_path: string | null;
  belongs_to_collection: {
    id: number;
    name: string;
    poster_path: string;
    backdrop_path: string;
  } | null;
  budget: number;
  genres: {
    id: number;
    name: string;
  }[];
  homepage: string | null;
  id: number;
  imdb_id: string | null;
  original_language: string;
  original_title: string;
  overview: string | null;
  popularity: number;
  poster_path: string | null;
  production_companies: {
    id: number;
    logo_path: string | null;
    name: string;
    origin_country: string;
  }[];
  production_countries: {
    iso_3166_1: string;
    name: string;
  }[];
  release_date: string;
  revenue: number;
  runtime: number | null;
  spoken_languages: {
    english_name: string;
    iso_639_1: string;
    name: string;
  }[];
  status: string;
  tagline: string | null;
  title: string;
  video: boolean;
  vote_average: number;
  vote_count: number;
}

interface TrendingCardProps {
  movie: TrendingMovie;
  index: number;
}
```

</details>

## Melhorias futuras

- [] Adicionar funcionalidade de salvar filmes
- [] Fazer a tela de perfil