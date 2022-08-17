<template>
  <div>
    <v-row align="center" justify="center" class="landing-page" no-gutters>
      <v-col cols="12" xl="2" lg="2" />
      <v-col cols="12" xl="8" lg="8">
        <v-container class="contenedor">
          <p class="font-1 font-title white--text">
            Discover Your Life, Travel Where You Want
          </p>
          <p class="font-4 font-desc white--text">
            Would you explore natur paradise in the world, let’s find the best
            destination in world with us.
          </p>
          <v-btn elevation="2">VIEW OUR WORK</v-btn>
        </v-container>
      </v-col>
      <v-col cols="12" xl="2" lg="2" />
    </v-row>
  </div>
</template>

<script>
export default {
  name: "LandingPage",

  components: {},
};
</script>
<style>
.contenedor{
  text-align: center;
}
.landing-page {
  height: 80vh;
  background: url("../../assets/images/fondo.png");
  background-size: cover;
}
.font-title {
  font-weight: 600;
  text-align: center;
}
.font-desc {
  font-weight: 500;
  text-align: center;
}

@media screen and (max-width: 600px) {
  .landing-page {
    height: 60vh;
    background: url("../../assets/images/fondo.png");
    background-size: cover;
    padding: 5%;
  }
  .font-title {
    text-align: left;
    line-height: 1.2;
  }

  .font-desc {
    font-weight: 500;
    text-align: left;
  }
}
</style>
