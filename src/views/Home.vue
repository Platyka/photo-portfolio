<template>
  <div class="home">
    <h1 class="home__title" key="home__title">Ambrus Attila</h1>
    <h2 class="home__subtitle" key="home__subtitle">Product photographer</h2>
    <router-link tag="button" class="home__cta" to="/portfolio">View portfolio</router-link>
  </div>
</template>

<style lang="scss" scoped>
  .home {
    height: 100%;
    width: 100%;
    display: flex;
    background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), 
                      url("../assets/images/backgrounds/main_mobile.jpg");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    color: #fff;
    @media screen and (min-width: 1024px) {
      background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), 
                        url("../assets/images/backgrounds/main_desktop.jpg");
    }
    &__title {
      font-size: 5.6rem;
      font-weight: 200;
      letter-spacing: 6px;
      @media screen and (min-width: 768px) {
        letter-spacing: 8px;
      }
      @media screen and (min-width: 1024px) {
        letter-spacing: 10px;
      }
    }
    &__subtitle {
      font-size: 4rem;
      font-weight: 100;
    }
    &__cta {
      margin-top: 6rem;
      outline: none;
      border: none;
      font-family: inherit;
      padding: 2rem 4rem;
      border-radius: 100px;
      cursor: pointer;
      background-color: #27ae60;
      font-size: 2rem;
      color: #fff;
      transition: all .4s ease;
      &:hover {
        background-color: #2ecc71;
      }
      @media only screen and (min-width: 1024px) {
        font-size: 1.6rem;
      }
    }
  }
</style>

