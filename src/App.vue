<template>
  <v-app class="animate__animated animate__fadeIn animate__slow">
    <v-app-bar
      :color="color"
     
      class=""
      fixed
      style="padding:0 5%"
      dark
      flat
    >
      <div class="d-flex align-center">
     <p class="font-2 mb-n1"><img src="https://relaxed-stonebraker-e1b798.netlify.app/img/Logo.png" alt=""></p>
      </div>

      <v-spacer></v-spacer>
     <div class="d-none d-sm-flex">
       <div class="d-flex align-center">
        <v-btn style="text-transform:none" class="font-7 pink--text" text plain color="black">All</v-btn>
      <v-btn style="text-transform:none" class="font-7 pink--text" text plain color="black">Branding</v-btn>
      <v-btn style="text-transform:none" class="font-7 pink--text" text plain color="black">Web</v-btn>
      <v-btn style="text-transform:none" class="font-7 pink--text" text plain color="black">Photography</v-btn>
      <v-btn style="text-transform:none" class="font-7 pink--text" text plain color="black">App</v-btn>
      <img src="./assets/icon/baseline_search_black_24dp.png" alt="">
     </div>
     </div>
     <v-app-bar-nav-icon class="d-flex d-sm-none"/>
    </v-app-bar>
    <v-main>
      <router-view/>
    </v-main>
    <v-footer class="bg-1 ">
     <v-container>
             <p class="font-7 text-center">© 2016 - Sneak All Right Reserved</p>
               <div class="footer-links">
                <v-icon>facebook</v-icon>
                <v-icon>language</v-icon>
            </div>
     </v-container>
    </v-footer>
  </v-app>
</template>

<script>
import "./css/fonts.css"
export default {
  name: 'App',

  data: () => ({
    //
    color: "white",
    colo: "black",
  }),
  mounted() {
  },
};
</script>
<style>
.footer-links{
    text-align: center;
}
.footer{
  padding:4%;
}
@media screen and (max-width:600px) {
 .footer{
  padding:10%;
} 

}
</style>
