<template>
  <div class="app">
    <like v-bind:photoId="1"></like>
  </div>
</template>

<script>
import like from "./components/like.vue";

export default {
  name: "App",
  components: { like }
};
</script>
