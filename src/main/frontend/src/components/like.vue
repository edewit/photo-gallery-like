<template>
  <div>
    <span class="fa-stack fa-sm" v-on:click="like()">
      <i class="fa fa-circle fa-stack-2x blue-icon" />
      <i v-bind:class="{ 'fa-thumbs-up': !done, 'fa-check-circle': done }" class="fa fa-stack-1x fa-inverse" />
    </span>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      done: false,
    };
  },
  props: {
    photoId: Number
  },
  methods: {
    like: function() {
      axios.post("/likes", {
        id: this.photoId,
        likes: 1
      }).then(() => this.done = true);
    }
  }
};
</script>

<style scoped>
span {
  cursor: pointer;
}
.blue-icon {
  color: #0099ff;
}
</style>