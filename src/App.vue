<template>
  <div id="app">
    <HeaderFilm></HeaderFilm>
    <div class="content__cards">
      <FilmCard
        v-for="film in films"
        :key="film.id"
        :path="`https://image.tmdb.org/t/p/w300${film.poster_path}`"
        :title="film.title"
        :genres="film.genre_ids"
        :release="film.release_date"
        :vote="film.vote_average"
      ></FilmCard>
    </div>
  </div>
</template>

<script>
const API_KEY = "bb47124fe990b3a04ccb5a994cf49456";
const BASE_URL_TRENDING = "https://api.themoviedb.org/3/trending/movie/week?";

import HeaderFilm from "./components/HeaderFilm.vue";
import FilmCard from "./components/FilmCard.vue";

export default {
  name: "App",
  components: { HeaderFilm, FilmCard },
  data() {
    return {
      films: {},
    };
  },
  async created() {
    this.films = await this.fetchTrend();
  },
  methods: {
    async fetchTrend() {
      const searchParams = new URLSearchParams({
        api_key: API_KEY,
      });
      const url = `${BASE_URL_TRENDING}${searchParams}`;
      const response = await fetch(url);
      const collection = await response.json();
      console.log(collection);
      return collection.results;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.content__cards {
  display: grid;
  max-width: 100%;
  grid-template-columns: repeat(auto-fill, minmax(274px, 1fr));
  grid-auto-rows: max-content;
  grid-gap: 30px;
  align-items: stretch;
  justify-content: center;
  transition: opacity 200ms ease;
}
</style>
