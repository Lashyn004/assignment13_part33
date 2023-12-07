<template>
  <div class="main">
    <carousel :itemsToShow="1.5">
      <slide v-for="(list, index) in lists" :key="index">
        <img :src="require(`/Users/lashynnnsh004/Desktop/Assignment133/part3/src/assets/${list.photo}`)" alt="Slide" class="carousel-image" />
        
      </slide>

      <template #addons>
        <navigation />
        <pagination />
      </template>
    </carousel>
  </div>
</template>

<script>
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

export default {
  name: 'App',
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
  data() {
    return {
      lists: [
        { photo: '1.jpeg' },
        { photo: '2.jpeg' },
        { photo: '3.jpeg' },
        { photo: '4.jpeg' },
        { photo: '5.jpeg' },
        { photo: '6.jpeg' },
      ],
    };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

.main {
  padding: 50px;
  background-color: #f5f5f5;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.carousel-image {
  width: 100%;
  max-width: 500px;
  height: auto;
  border-radius: 10px;
  outline: none;
  border: none;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.carousel-nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 20px;
}

.carousel-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #3498db;
  margin: 0 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.carousel-dot.active {
  background-color: #2c3e50;
}
</style>
