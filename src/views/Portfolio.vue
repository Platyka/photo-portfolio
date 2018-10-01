<template>
  <div class="portfolio">
    <div class="container">
      <app-backdrop v-if="showImage" @click.native="showImage = false">
        <transition name="zoom" appear>
          <app-full-res-image :clickedImage="currentImage"></app-full-res-image>
        </transition>
      </app-backdrop>
      <app-gallery-grid>
        <app-gallery-element v-for="image in images" :source="image" :key="image.id" @click.native="clickedImage(image.fullRes)"></app-gallery-element>
      </app-gallery-grid>
    </div>
  </div>
</template>

<script>
import GalleryGrid from '../components/gallery/GalleryGrid'
import GalleryElement from '../components/gallery/GalleryElement'
import FullResImage from '../components/gallery/FullResImage'
import Backdrop from '../components/Backdrop.vue'
export default {
  data () {
    return {
      images: [
        { id: 1, imgUrl: require('../assets/images/portfolio/desktop/1_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/1.jpg') },
        { id: 2, imgUrl: require('../assets/images/portfolio/desktop/2_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/2.jpg') },
        { id: 3, imgUrl: require('../assets/images/portfolio/desktop/3_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/3.jpg') },
        { id: 4, imgUrl: require('../assets/images/portfolio/desktop/4_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/4.jpg') },
        { id: 5, imgUrl: require('../assets/images/portfolio/desktop/5_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/5.jpg') },
        { id: 6, imgUrl: require('../assets/images/portfolio/desktop/6_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/6.jpg') },
        { id: 7, imgUrl: require('../assets/images/portfolio/desktop/7_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/7.jpg') },
        { id: 8, imgUrl: require('../assets/images/portfolio/desktop/8_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/8.jpg') },
        { id: 9, imgUrl: require('../assets/images/portfolio/desktop/9_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/9.jpg') },
        { id: 10, imgUrl: require('../assets/images/portfolio/desktop/10_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/10.jpg') },
        { id: 11, imgUrl: require('../assets/images/portfolio/desktop/11_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/11.jpg') },
        { id: 12, imgUrl: require('../assets/images/portfolio/desktop/12_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/12.jpg') },
        { id: 13, imgUrl: require('../assets/images/portfolio/desktop/13_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/13.jpg') },
        { id: 14, imgUrl: require('../assets/images/portfolio/desktop/14_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/14.jpg') },
        { id: 15, imgUrl: require('../assets/images/portfolio/desktop/15_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/15.jpg') },
        { id: 16, imgUrl: require('../assets/images/portfolio/desktop/16_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/16.jpg') },
        { id: 17, imgUrl: require('../assets/images/portfolio/desktop/17_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/17.jpg') },
        { id: 18, imgUrl: require('../assets/images/portfolio/desktop/18_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/18.jpg') },
        { id: 19, imgUrl: require('../assets/images/portfolio/desktop/19_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/19.jpg') },
        { id: 20, imgUrl: require('../assets/images/portfolio/desktop/20_thumbnail.jpg'), fullRes: require('../assets/images/portfolio/desktop/20.jpg') }
      ],
      showImage: false,
      currentImage: ''
    }
  },
  components: {
    appGalleryGrid: GalleryGrid,
    appGalleryElement: GalleryElement,
    appBackdrop: Backdrop,
    appFullResImage: FullResImage
  },
  methods: {
    clickedImage (url) {
      this.showImage = true
      this.currentImage = url
    }
  }
}
</script>

<style lang="scss" scoped>
.portfolio {
  display: grid;
  grid-template-columns: 1fr;
  padding: 4rem 2rem;
  background-color: #34495e;
  @media only screen and (min-width: 1024px) {
    grid-template-columns: minmax(6rem, 1fr) repeat(12, minmax(min-content, 10rem)) minmax(6rem, 1fr);
    padding: 0;
  }
}
.container {
  @media only screen and (min-width: 1024px) {
    grid-column: 2 / -2;
    margin: 4rem 0;
  }
}
.zoom-enter-active {
  animation: zoom-in .6s ease forwards;
}
@keyframes zoom-in {
  from {
    transform: scale(.6);
  }
  to {
    transform: scale(1);
  }
}
</style>
