<template>
  <v-app
    style="background-color: #FBAB7E;
           background-image: linear-gradient(62deg, #FBAB7E 0%, #F7CE68 100%);"
  >
    <v-container fill-height fluid>
      <v-row align="center" justify="center">
        <v-col v-if="is_hide" cols="5">
          <span class="text-h1 white--text font-weight-bold">Today is a Special Day ,</span>
          <br />
          <span
            @click="surprise"
            role="button"
            class="text-h1 pink--text font-weight-bold border-why"
          >But Why</span>
          <span class="text-h1 white--text font-weight-bold">?!</span>

          <!-- <h1 class="text-h1 white--text font-weight-bold text-decoration-underline" role="button">Why ?</h1> -->
          <!-- <v-btn color="warning" rounded x-large>Why ?</v-btn> -->
        </v-col>
        <v-col v-if="!is_hide" xl="4" lg="4" md="5" sm="6" cols="6">
          <v-card class="card">
            <v-img
              class="mx-center mt-n15"
              contain
              :src="require('./assets/birthday.svg')"
              height="100"
            />
            <!-- <v-card-subtitle class="text-center">
              <span class="text-h6 white--text pa-0 ma-0">1997-11-21</span>
            </v-card-subtitle>-->
            <v-card-title class="mx-auto pa-0 ma-0">
              <h1 class="mx-auto text-h3 font-weight-bold pink--text my-5">Happy Birthday !</h1>
              <span class="text-h4 mx-auto white--text white--text">Mohammed</span>
            </v-card-title>
            <v-card-actions class="text-center">
              <span
                class="mx-auto text-h6 text-title stork white--text"
              >You have Made it into Another Year , We Wish You All The Best</span>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>

export default {
  data() {
    return {
      is_hide: true
    }
  },
  methods: {
    surprise() {
      this.is_hide = !this.is_hide
      this.start();
    },
    start() {
      this.$confetti.start()
    },

    stop() {
      this.$confetti.stop()
    }
  },
  mounted() {
    // this.start();
  }
}
</script>
<style lang="scss">
.card {
  background: rgba(255, 255, 255, 0.25) !important;
  box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37) !important;
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px) !important;
  border-radius: 10px !important;
  border: 1px solid rgba(255, 255, 255, 0.18) !important;
}

.v-btn:hover:before {
  background-color: transparent;
}
.border-why {
  border-bottom: 10px solid white;
}
</style>
