<template>
  <div class="full-image">
    <img :src="clickedImage" alt="" class="full-image__img">
  </div>
</template>


<script>
export default {
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
</style>
