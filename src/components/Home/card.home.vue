<template>
  <div class="recommend-container">
    <div class="text-center">
      <v-icon>grid_view</v-icon>
      <v-icon>view_stream</v-icon>
    </div>

    <br />

    <v-row no-gutters align="center" justify="center">
      <v-col cols="12" xl="4" lg="4" />
      <v-col cols="12" xl="4" lg="4">
        <div class="pa-2 tab2">
          <div>
            <v-row>
              <span class="tab-width">
                <v-btn
                  @click="imgAll"
                  color="#FFFFFF"
                  style="height: 100%"
                  elevation="0"
                  class="mr-1 pink--text btn font-7"
                  dark
                  >All</v-btn
                >
              </span>
              <span class="tab-width">
                <v-btn
                  @click="imgPar"
                  color="#FFFFFF"
                  style="height: 100%"
                  elevation="0"
                  class="mr-1 pink--text btn font-7"
                  dark
                  >Par</v-btn
                >
              </span>
              <span class="tab-width">
                <v-btn
                  @click="imgImpar"
                  color="#FFFFFF"
                  style="height: 100%"
                  elevation="0"
                  class="mr-1 pink--text btn font-7"
                  dark
                  >Impar</v-btn
                >
              </span>
            </v-row>
          </div>
        </div>
      </v-col>
      <v-col cols="12" xl="4" lg="4" />
    </v-row>

    <br />

    <div class="contenedorCard">
    <v-row v-if="itsall">
      <v-col v-for="i in recommends" :key="i.id" cols="12" xl="4" lg="4">
        <card :img="i" />
      </v-col> </v-row
    ><v-row v-if="itspar">
      <v-col v-for="i in recommendsPar" :key="i.id" cols="12" xl="4" lg="4">
        <card :img="i" />
      </v-col> </v-row
    ><v-row v-if="itsimpar">
      <v-col v-for="i in recommendsImpar" :key="i.id" cols="12" xl="4" lg="4">
        <card :img="i" />
      </v-col>
    </v-row>
    <v-spacer></v-spacer>
    <div class="text-center showButton">
      <v-btn elevation="2" class="mr-1 pink--text font-7">Show Me More</v-btn>
    </div>
    </div>
  </div>
</template>

<script>
import card from "./utilities/card.vue";
import axios from "axios";

export default {
  components: {
    card,
  },

  data() {
    return {
      itsall: true,
      itspar: false,
      itsimpar: false,
      recommends: null,
      recommendsPar: [],
      recommendsImpar: [],
    };
  },

  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/albums/1/photos")
      .then((response) => {
        this.recommends = response.data;

        for (const key in this.recommends) {
          console.log(this.recommends[key].id % 2);
          if (this.recommends[key].id % 2 == 0) {
            this.recommendsPar.push(this.recommends[key]);
          } else {
            this.recommendsImpar.push(this.recommends[key]);
          }
          
        }
      })

      .catch((error) => console.log(error));
  },

  methods: {
    imgAll() {
      this.itsimpar = false;
      this.itsall = true;
      this.itspar = false;
    },
    imgPar() {
      this.itsimpar = false;
      this.itsall = false;
      this.itspar = true;
      console.log("pares");
    },
    imgImpar() {
      this.itspar = false;
      this.itsall = false;
      this.itsimpar = true;
      console.log("impares");
    },
  },
};
</script>

<style>
.contenedorCard{
  height: 50%;
}

.showButton {
  margin-top: 60px;
}
.btn {
  text-transform: none !important;
  width: 100%;
  height: 6vh !important;
}
.tab-width {
  width: 33% !important;
}
.v-icon {
  margin: 0 15px;
}
.recommend-container {
  padding: 4%;
}
.tab2 {
  margin: 0 8%;

  height: 8vh;
  border-radius: 13px;
}
@media screen and (max-width: 600px) {
  .recommend-container {
    padding: 12%;
  }
}
</style>