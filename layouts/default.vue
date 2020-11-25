<template>
  <v-app dark>
    <v-app-bar hide-on-scroll fixed flat app color="#272727">   
      <v-app-bar-nav-icon class="d-block d-md-none"></v-app-bar-nav-icon>
      <v-toolbar-title class="text-button text-uppercase">kbr3, the creator!</v-toolbar-title>
      <v-spacer></v-spacer>
      <div class="app-search" v-click-outside="onClickOutside"
            @click="active = true"
            :class="active ? 'app-search' : 'collapse'">
        <div class="search-wrapper">
          <v-text-field 
            hide-details="auto" 
            dense 
            single-line 
            outlined 
            rounded 
            label="Searching for something"
            append-icon="mdi-magnify"
            color="white"
          >
          </v-text-field>
        </div>
      </div>
    </v-app-bar>

    <v-main>
      <nuxt />
    </v-main>

    <v-footer class="grey--text text--darken-3 pt-8 grey lighten-3" inset>
      <v-container>
        <v-row no-gutters>
          <v-col class="text-body-2 font-italic mb-md-0 mb-6 col-md-6 col-12">
            Frontend Dev since 2018
            <br>
            Based in Phnom Penh moved from Siem Reap
            <br>
            Currently working full-time as a fullstack developer on both Earth and Mars.
          </v-col>

          <v-col class="text-sm-right text-left col-md-6 col-12">
            <v-btn class="grey--text text--darken-3" rounded text small fab href="https://www.facebook.com/kit.bunrong.1" target="_blank">
              <v-icon class="mdi mdi-facebook" style="font-size: 22px"></v-icon>
            </v-btn>
            <v-btn class="grey--text text--darken-3" rounded text small fab href="https://www.instagram.com/bunrongkit/" target="_blank">
              <v-icon class="mdi mdi-instagram" style="font-size: 22px"></v-icon>
            </v-btn>
            <v-btn class="grey--text text--darken-3" rounded text small fab href="https://twitter.com/KitBunrong" target="_blank">
              <v-icon class="mdi mdi-twitter" style="font-size: 22px"></v-icon>
            </v-btn>
            <v-btn class="grey--text text--darken-3" rounded text small fab href="https://kh.linkedin.com/in/kit-bunrong-1b8126193?trk=public_profile_samename-profile_profile-result-card_result-card_full-click" target="_blank">
              <v-icon class="mdi mdi-linkedin" style="font-size: 22px"></v-icon>
            </v-btn>
          </v-col>

          <v-row class="text-caption mt-6 no-gutters">
            <v-col class="col-md-6 col-12">
              Website made with 
              <a href="https://nuxtjs.org/" target="_blank">nuxtjs</a>
              &
              <a href="https://vuetifyjs.com/" target="_blank">vuetifyjs</a>
              , api driven using 
              <a href="https://ghost.org/" target="_blank">ghost.</a>
            </v-col>
            <v-col class="col-md-6 col-12 text-right">
              <span>KBR3, THE CREATOR! 2018-21©</span>
            </v-col>
          </v-row>
        </v-row>
      </v-container>
    </v-footer>
  </v-app>
</template>

<script>

export default {
  data: () => ({
    active: false,
  }),
  methods: {
      onClickOutside () {
        this.active = false
      },
    },
}
</script>

<style lang="scss" scoped>

.app-search{
  transition: width .5s;
  width: 100%;
}
.collapse{
  width: 40%;
}
.search-wrapper{
  position: relative;
}

@media (min-width: 600px){
  .app-search{
    width: 30%
  }
}
@media (min-width: 600px){
  .collapse{
    width: 18%;
  }
}

</style>
