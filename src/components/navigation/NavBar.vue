<template>
  <nav class="nav">
    <div class="nav__container">
      <div class="nav__menu" v-if="windowWidth < 1024" @click="menuClick">
        <div class="nav__hamburger nav__hamburger--top"></div>
        <div class="nav__hamburger nav__hamburger--middle"></div>
        <div class="nav__hamburger nav__hamburger--bottom"></div>
      </div>
      <router-link to="/" class="nav__logo">AA Photography</router-link>
      <ul class="nav__list" v-if="windowWidth >= 1024">
        <router-link tag="li" class="nav__item" active-class="nav__active" to="/portfolio"><a class="nav__link">Portfolio</a></router-link>
        <router-link tag="li" class="nav__item" active-class="nav__active" to="/about"><a class="nav__link">About me</a></router-link>
        <router-link tag="li" class="nav__item" active-class="nav__active" to="/contact"><a class="nav__link">Contact</a></router-link>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      windowWidth: window.innerWidth,
      menuClicked: false
    }
  },
  methods: {
    menuClick () {
      this.menuClicked = true
      this.$emit('menuWasClicked', this.menuClicked)
      console.log(this.menuClicked)
    }
  },
  mounted () {
    window.addEventListener('resize', (event) => {
      this.windowWidth = event.target.innerWidth
    })
  }
}
</script>

<style lang="scss" scoped>
  .nav {
    height: 7rem;
    background-color: #2c3e50;
    padding: 0 2rem;
    @media only screen and (min-width: 768px) {
      height: 5rem;
    }
    @media only screen and (min-width: 1024px) {
      padding: 0;
      display: grid;
      grid-template-columns: minmax(6rem, 1fr) repeat(12, minmax(min-content, 10rem)) minmax(6rem, 1fr);
    }
    &__container {
      height: 100%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      @media only screen and (min-width: 1024px) {
        grid-column: 2 / -2;
      }
    }
    &__menu {
      height: 100%;
      width: 30px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-end;
      cursor: pointer;
    }
    &__hamburger {
      background-color: #fff;
      height: 3px;
      border-radius: 2px;
      &--top {
        width: 25px;
        transform: translateY(-5px);
      }
      &--middle {
        width: 30px;
      }
      &--bottom {
        width: 20px;
        transform: translateY(5px);
      }
    }
    &__logo:visited,
    &__logo:link,
    &__link:visited,
    &__link:link {
      text-decoration: none;
      color: #fff;
    }
    &__logo {
      font-size: 2.6rem;
      @media only screen and (min-width: 1024px) {
        font-size: 2.4rem;
      }
    }
    &__list {
      list-style: none;
      display: flex;
    }
    &__item {
      font-size: 1.6rem;
      transition: all .4s ease;
      &:not(:last-of-type) {
        margin-right: 2rem;
      }
      &:hover {
        background-color: #27ae60;
        border-radius: 5px;
      }
    }
    &__link {
      display: inline-block;
      padding: 1rem 2rem;
    }
    &__active {
      background-color: #27ae60;
      border-radius: 5px;
    }
  }
</style>
