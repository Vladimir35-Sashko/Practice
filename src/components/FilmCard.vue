<template>
  <li class="content__card">
    <a href="#!" data-id="id" class="content__link">
      <div class="poster__wraper">
        <img
         
          :src = "path"
          :alt="`poster for ${title}`"
          class="content__poster"
        />
      </div>
      <div class="card__description">
        <p class="content__title">{{title}}</p>
        <p class="content__info">
          <span class="content__genres">Rating: {{genres}} </span>          
          <span class="content__year">Release day: {{release}} </span>
          <span class="content__rating">Voteing: {{vote}} </span>
        </p>
      </div>
    </a>    
  </li>
</template>

<script>
export default {
  name: "FilmCard",
  props: {
    path: {
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    genres: {
      type: [],
      default: ''
    },
    release: {
      type: String,
      default: ''
    },
    vote: {
      type: Number,
      default: 0
    }
  }
};
</script>

<style lang="scss" scoped>
</style>
