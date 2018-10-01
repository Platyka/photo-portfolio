<template>
  <nav class="sidenav">
    <ul class="sidenav__list">
      <router-link tag="li" class="sidenav__item" to="/portfolio" active-class="sidenav__active"><a class="sidenav__link">Portfolio</a></router-link>
      <router-link tag="li" class="sidenav__item" to="/about" active-class="sidenav__active"><a class="sidenav__link">About me</a></router-link>
      <router-link tag="li" class="sidenav__item" to="/contact" active-class="sidenav__active"><a class="sidenav__link">Contact</a></router-link>
    </ul>
  </nav>
</template>

<style lang="scss" scoped>
  .sidenav {
    width: 70%;
    height: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: #2c3e50;
    z-index: 1000;
    &__list {
      list-style: none;
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
    }
    &__item {
      color: #fff;
      font-size: 4rem;
      margin: 2rem 0;
    }
    &__link:visited,
    &__link:link {
      color: #fff;
      text-decoration: none;
      display: block;
      padding: 2rem 4rem;
    }
    &__active {
      background-color: #27ae60;
      border-radius: 5px;
    }
  }
</style>
