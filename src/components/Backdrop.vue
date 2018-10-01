<template>
  <div class="backdrop">
    <slot></slot>
  </div>
</template>

<style lang="scss" scoped>
  .backdrop {
    height: 100%;
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    background-color: rgba(0, 0, 0, .9);
    z-index: 999;
    // @media only screen and (min-width: 1024px) {
    //   display: flex;
    //   justify-content: center;
    //   align-items: center;
    // }
  }
</style>
