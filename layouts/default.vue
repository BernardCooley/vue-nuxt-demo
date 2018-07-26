<template>
  <div class="bodyContainer">
    <navigation/>
    <nuxt/>
  </div>
</template>

<script>
import Navigation from '~/components/Navigation.vue'

export default {
  components: {
    Navigation
  }
}
</script>


<style>

@import url('https://fonts.googleapis.com/css?family=Work+Sans');

body {
  font-family: 'Work Sans', Arial, sans-serif;
  background-image: url("~/assets/images/light-background.jpeg");
  background-repeat: no-repeat;
  background-size: 100% 100%;
}

.bodyContainer {
  height: 700px;
}


</style>

