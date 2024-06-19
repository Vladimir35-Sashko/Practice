<template>
  <header class="page-header">
    <div class="header__container container home-container">
      <div class="header__nav-wrapper">
        <a class="logo__link" href="#!"
          ><img
            class="logo__img"
            width="24"
            height="24"
            src="/src/assets/images/header/logo.svg"
            data-index="home" /></a
        ><a class="title-link" href="#!" data-index="home">Filmoteka </a>

        <ul class="header__nav list">
          <li class="header__nav-item">
            <a
              class="header__nav-link header__nav-link--active"
              data-index="home"
              href="#!"
              >HOME</a
            >
          </li>

          <li class="header__nav-item">
            <a
              class="header__nav-link"
              data-index="liba"
              data-name="Watched"
              href="#!"
              >MY LIBRARY</a
            >
          </li>
        </ul>
      </div>
      <div class="header__form">
        <input
          class="header__input js-input"
          type="text"
          name="query"
          placeholder="Поиск Фильмов"
          autocomplete="off"
        />
        <p class="header__input-icon"></p>
      </div>

      <strong class="header__warning" style="display: none"
        >Search result not successful. Enter the correct movie name and
      </strong>
      <b class="header__thats-all-msg" style="display: none"
        >Это все, что найдено по данному запросу</b
      >
    </div>
    <div
      class="header__container container lib-container"
      style="display: none"
    >
      <div class="header__nav-wrapper">
        <a class="logo__link" href="#!"
          ><img
            class="logo__img"
            width="24"
            height="24"
            src="/src/assets/images/header/logo.svg"
            data-index="home" /></a
        ><a class="title-link" href="#!" data-index="home">Filmoteka </a>
        <ul class="header__nav list">
          <li class="header__nav-item">
            <a class="header__nav-link" data-index="home" href="#!">HOME</a>
          </li>

          <li class="header__nav-item">
            <a
              class="header__nav-link header__nav-link--active"
              data-index="liba"
              data-name="Watched"
              href="#!"
              >MY LIBRARY</a
            >
          </li>
        </ul>
      </div>
      <div class="header__filter-button-wrapper">
        <button
          type="button"
          data-name="Watched"
          class="modal-button header__button--right modal-button--active js-watched"
        >
          Watched
        </button>
        <button type="button" class="modal-button js-queue" data-name="Queue">
          Queue
        </button>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderFilm'
};
</script>

<style lang="scss" scoped>
.page-header {
  background-color: black;
}
.header {
  &__container {
    height: 230px;
    display: flex;
    flex-direction: column;

    background-color: black;
    background-image: linear-gradient(
        to left,
        rgba(0, 0, 0, 0.56),
        rgba(0, 0, 0, 0.56)
      ),
      url("../assets/images/header/bg-small.jpg");
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;

    @media screen and (min-width: 768px) {
      background-image: linear-gradient(
          to left,
          rgba(0, 0, 0, 0.56),
          rgba(0, 0, 0, 0.56)
        ),
        url("../assets/images/header/bg-medium.jpg");
    }
    @media screen and (min-width: 1024px) {
      background-image: linear-gradient(
          to left,
          rgba(0, 0, 0, 0.56),
          rgba(0, 0, 0, 0.56)
        ),
        url("../assets/images/header/bg-big.jpg");
    }
  }
  &__nav-wrapper {
    display: flex;
    margin-top: 46px;
    align-items: flex-end;
    height: 24px;
  }
  &__nav {
    display: flex;
  }
}
.logo__link {
  display: flex;
  align-items: stretch;
  outline-color: #ff6b08;
}

.title-link {
  line-height: 0.8;
  margin-left: 10px;
  display: none;
  font-weight: 500;
  @media screen and (min-width: 768px) {
    display: block;
    color: white;
    font-size: 30px;

    align-self: center;
  }
  background: url(https://i.ibb.co/RDTnNrT/animated-text-fill.png) repeat-y;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  -webkit-animation: transform 80s linear infinite;
  -webkit-transform: translate3d(0, 0, 0);
  -webkit-backface-visibility: hidden;
}
@-webkit-keyframes transform {
  0% {
    background-position: 0% 50%;
  }
  100% {
    background-position: 100% 50%;
  }
}
.header__nav-wrapper {
  display: flex;

  outline: none;
}
.header__nav {
  margin-left: auto;
}
.header__nav-item {
  position: relative;
}
.header__nav-item:first-child {
  margin-right: 40px;
}

.header__nav-link {
  font-weight: 500;
  line-height: 1.2;
  color: white;
  text-transform: uppercase;
  outline-color: #ff6b08;
}

.header__nav-link--active::after {
  content: "";
  position: absolute;
  display: block;
  bottom: -3px;
  left: 0;
  width: 100%;
  height: 4px;
  border-radius: 1px;
  background-color: #ff6b08;
}
@keyframes changeColor {
  0% {
    color: white;
  }

  50% {
    color: #ff6b08;
  }

  100% {
    color: white;
  }
}
.header__nav-link:hover,
// .title-link:hover,
.header__nav-link:focus,
.title-link:focus {
  animation-name: changeColor;
  animation-duration: 1300ms;
  animation-timing-function: ease-in;
  animation-iteration-count: infinite;
  outline-color: #ff6b08;
}

.header__form {
  position: relative;
  width: 100%;
  max-width: 336px;
  height: 20px;
  border-bottom: solid 1px white;
  align-self: center;
  margin-top: 40px;
  font-size: 14px;
  @media screen and (min-width: 768px) {
    max-width: 436px;
    height: 30px;
    font-size: 18px;
  }
}
.header__input-icon::before {
  content: "";
  position: absolute;
  display: inline-block;
  top: 5px;
  right: 0px;
  width: 12px;
  height: 12px;

  background-image: url("../assets/images/header/search2.svg");
  background-repeat: no-repeat;
}

.header__input {
  background-color: transparent;
  border: none;
  width: 100%;
  outline: none;
  color: white;
}

.header__warning {
  margin-top: 22px;
  align-self: center;
  color: red;
  font-size: 14px;
  font-weight: 400;
  text-align: left;
}
.header__filter-button-wrapper {
  display: flex;
  margin-left: auto;
  margin-right: auto;
  margin-top: 45px;
}
.header__button--right {
  margin-right: 20px;
  @media screen and (min-width: 768px) {
    margin-right: 15px;
  }
}

.lib-container {
  background-image: linear-gradient(to left, rgba(0, 0, 0, 0.56), rgba(0, 0, 0, 0.56)),
    url("../assets/images/header/lib-bg-small.jpg");

  @media screen and (min-width: 768px) {
    background-image: linear-gradient(to left, rgba(0, 0, 0, 0.56), rgba(0, 0, 0, 0.56)),
      url("../assets/images/header/lib-bg-medium.jpg");
  }
  @media screen and (min-width: 1024px) {
    background-image: linear-gradient(to left, rgba(0, 0, 0, 0.56), rgba(0, 0, 0, 0.56)),
      url("../assets/images/header/lib-bg-big.jpg");
  }
}
.header__thats-all-msg {
  margin-top: 22px;
  align-self: center;
  color: #ff6b08;
  font-size: 16px;
  font-weight: 500;
  text-align: left;
}

.empty-list {
  text-align: center;
}
</style>
