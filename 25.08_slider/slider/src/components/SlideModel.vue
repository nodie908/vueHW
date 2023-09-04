<template>
  <div class="slide">
    <h1>{{ slideData.title }}</h1>
    <p>{{ slideData.text }}</p>
  </div>
</template>

<script>

export default {
  name: 'SlideModel',
  props: {
    slideData: {
      type: Object,
      required: true
    }
  }
}  

</script>


<style scoped>
.slide {
  border: 1px solid #ddd;
  padding: 20px;
  background-color: #f9f9f9;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin: 10px;
}
</style>
