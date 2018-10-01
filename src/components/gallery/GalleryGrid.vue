<template>
  <div class="gallery-grid">
    <slot></slot>
  </div>
</template>

<style lang="scss" scoped>
.gallery-grid {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(20, 50vw);
  grid-gap: 4rem;
  @media only screen and (min-width: 1024px) {
    grid-template-columns: repeat(8, 1fr);
    grid-template-rows: repeat(18, 8vw);
    grid-gap: 2rem;
  }
}
</style>
