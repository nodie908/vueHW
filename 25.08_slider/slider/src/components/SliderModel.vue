<template>
  <div class="slider-container">
    <button @click="prevSlide">Предыдущий слайд</button>
    <button @click="nextSlide">Следующий слайд</button>
    <slide :slideData="currentSlideData"></slide>
  </div>
</template>

<script>

import Slide from './SlideModel.vue'

export default {
  name: 'SliderModel',
  components: {
    Slide
  },
  data() {
    return {
      currentSlideIndex: 0,
      slides: [
        { title: "Гепард", text: "является самым быстрым наземным животным на планете, способным развивать скорость до 100 километров в час на короткие дистанции." },
        { title: "Окунь", text: " это пресноводная рыба, способная изменять цвет своей кожи в зависимости от окружающей среды, чтобы скрыться от хищников и обмануть свою добычу." },
        { title: "Колибри", text: "это единственные птицы, способные летать задом наперёд. Это возможно благодаря быстрому и мощному метаболизму, который позволяет им развивать высокую частоту махов крыльев." },
        { title: "Крокодилы", text: "имеют один из самых мощных прикусов среди всех животных. Они могут закрывать свои челюсти с такой силой, что даже жертвы, которые оказались в их укусе, трудно освободиться." },
      ]
    }
  },
  computed: {
    currentSlideData() {
      return this.slides[this.currentSlideIndex];
    }
  },
  methods: {
    prevSlide() {
      if (this.currentSlideIndex > 0) {
        this.currentSlideIndex--;
      }
    },
    nextSlide() {
      if (this.currentSlideIndex < this.slides.length - 1) {
        this.currentSlideIndex++;
      }
    }
  }
}
</script>

<style>
.slider-container {
  text-align: center;
  margin: 20px;
}

button {
  padding: 10px 20px;
  font-size: 16px;
  background-color: #007BFF;
  color: #fff;
  border: none;
  cursor: pointer;
  margin: 5px;
}
</style>
