<template>
  <div>
   <landingPage />
  <div class="bg-1">
    <v-container class="cont">
       <cardHome />
    </v-container>
  </div>
  </div>
</template>

<script>
import landingPage from '../components/Home/landing.page.vue'
import cardHome from '../components/Home/card.home.vue'



  export default {
    name: 'Home',

    components: {
      landingPage,
      cardHome,
    },
  }
</script>
<style>
.cont{
  width: 70%;
}
</style>
