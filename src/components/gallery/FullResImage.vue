<template>
  <div class="full-image">
    <div class="lds-ring" v-show="!loadFinished">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>
    <img :src="clickedImage" alt="" class="full-image__img" @load="loadFinished = true" v-show="loadFinished">
  </div>
</template>

<script>
export default {
  data() {
    return {
      loadFinished: false
    }
  },
  props: ['clickedImage']
}
</script>

<style lang="scss" scoped>
  .full-image {
    height: 100vh;
    padding: 2rem;
    display: flex;
    justify-content: center;
    align-items: center;
    @media only screen and (min-width: 1024px) {
      padding: 4rem;
    }
    &__img {
      height: 100%;
      width: 100%;
      object-fit: contain;
    }
  }
  .lds-ring {
  display: inline-block;
  position: relative;
  width: 64px;
  height: 64px;
}
  .lds-ring div {
    box-sizing: border-box;
    display: block;
    position: absolute;
    width: 51px;
    height: 51px;
    margin: 6px;
    border: 6px solid #fff;
    border-radius: 50%;
    animation: lds-ring 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
    border-color: #fff transparent transparent transparent;
  }
  .lds-ring div:nth-child(1) {
    animation-delay: -0.45s;
  }
  .lds-ring div:nth-child(2) {
    animation-delay: -0.3s;
  }
  .lds-ring div:nth-child(3) {
    animation-delay: -0.15s;
  }
  @keyframes lds-ring {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
</style>
