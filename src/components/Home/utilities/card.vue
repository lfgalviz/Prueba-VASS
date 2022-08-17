<template>
  <v-img :src="img.url">{{img.id}}</v-img>
</template>

<script>
export default {
  data() {
    return {
    };
  },
  props: ["img"],
};
</script>

<style>
</style>