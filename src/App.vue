<template>
  <div id="app">
    <app-backdrop v-if="showSideNav" @click.native="closeSideNav">
      <transition name="slide" appear>
        <app-side-nav></app-side-nav>
      </transition>
    </app-backdrop>
    <app-nav-bar v-if="showNav" @menuWasClicked="slideSideNav"></app-nav-bar>
    <router-view></router-view>
  </div>
</template>

<script>
import NavBar from './components/navigation/NavBar.vue'
import SideNav from './components/navigation/SideNav.vue'
import Backdrop from './components/Backdrop.vue'
export default {
  data () {
    return {
      showSideNav: false
    }
  },
  computed: {
    showNav () {
      return this.$route.path === '/portfolio' || this.$route.path === '/about' || this.$route.path === '/contact'
    }
  },
  methods: {
    slideSideNav (data) {
      this.showSideNav = data
    },
    closeSideNav () {
      this.showSideNav = false
    }
  },
  components: {
    appNavBar: NavBar,
    appSideNav: SideNav,
    appBackdrop: Backdrop
  }
}
</script>

<style lang="scss">
*,*::after, *::before {
  margin:0;
  padding:0;
  box-sizing: inherit;
}
html {
  font-size: 37.5%;
  box-sizing: border-box;
  @media only screen and (min-width: 768px) {
    font-size: 50%;
  }
  @media only screen and (min-width: 1024px) {
    font-size: 62.5%;
  }
}
body {
  font-family: Montserrat, sans-serif;
}
#app {
  height: 100vh;
}
.slide-enter-active {
  animation: slide-in .4s ease forwards;
}
@keyframes slide-in {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(0);
  }
}
@keyframes slide-out {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-100%);
  }
}
</style>
