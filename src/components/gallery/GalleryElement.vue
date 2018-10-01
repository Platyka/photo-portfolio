<template>
  <div class="gallery-element" :class="'gallery-element--' + source.id">
    <img :src="source.imgUrl" alt="" class="gallery-element__image">
    <i class="fas fa-search-plus gallery-element__icon"></i>
  </div>
</template>

<script>
export default {
  props: ['source']
}
</script>

<style lang="scss" scoped>
.gallery-element {
  overflow: hidden;
  @media only screen and (min-width: 1024px) {
    border-radius: 5px;
    position: relative;
    &:hover &__icon {
      display: block;
    }
  }
  &__image {
    width: 100%;
    height: 100%;
    display: block;
    object-fit: contain;
    @media only screen and (min-width: 1024px) {
      object-fit: cover;
      transition: all .4s ease;
      &:hover {
        filter: brightness(.4);
        transform: scale(1.2);
        cursor: pointer;
      }
    }
  }
  &__icon {
    display: none;
    color: #fff;
    font-size: 4rem;
    z-index: 100;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    animation: slide-up .6s ease;
    pointer-events: none;
  }
}
@media only screen and (min-width: 1024px) {
  .gallery-element--1 {
    grid-column: 1 / 4;
    grid-row: 1 / 3;
  }
  .gallery-element--2 {
    grid-column: 4 / 7;
    grid-row: 1 / 3;
  }
  .gallery-element--3 {
    grid-column: 7 / -1;
    grid-row: 1 / 4;
  }
  .gallery-element--4 {
    grid-column: 1 / 3;
    grid-row: 13 / 16;
  }
  .gallery-element--5 {
    grid-column: 7 / -1;
    grid-row: 12 / 15;
  }
  .gallery-element--6 {
    grid-column: 1 / 3;
    grid-row: 10 / 13;
  }
  .gallery-element--7 {
    grid-column: 3 / 7;
    grid-row: 3 / 6;
  }
  .gallery-element--8 {
    grid-column: 7 / -1;
    grid-row: 7 / 10;
  }
  .gallery-element--9 {
    grid-column: 7 / -1;
    grid-row: 4 / 7;
  }
  .gallery-element--10 {
    grid-column: 1 / 4;
    grid-row: 6 / 10;
  }
  .gallery-element--11 {
    grid-column: 1 / 3;
    grid-row: 3 / 6;
  }
  .gallery-element--12 {
    grid-column: 6 / -1;
    grid-row: 10 / 12;
  }
  .gallery-element--13 {
    grid-column: 1 / 3;
    grid-row: 16 / -1;
  }
  .gallery-element--14 {
    grid-column: 3 / 6;
    grid-row: 15 / 17;
  }
  .gallery-element--15 {
    grid-column: 6 / -1;
    grid-row: 15 / -1;
  }
  .gallery-element--16 {
    grid-column: 4 / 7;
    grid-row: 8 / 10;
  }
  .gallery-element--17 {
    grid-column: 4 / 7;
    grid-row: 6 / 8;
  }
  .gallery-element--18 {
    grid-column: 3 / 7;
    grid-row: 12 / 15;
  }
  .gallery-element--19 {
    grid-column: 3 / 6;
    grid-row: 10 / 12;
  }
  .gallery-element--20 {
    grid-column: 3 / 6;
    grid-row: 17 / -1;
  }
}
@keyframes slide-up {
  from {
    transform: translate(-50%,0%);
    opacity: 0;
  }
  to {
    transform: translate(-50%,-50%);
    opacity: 1;
  }
}
</style>
