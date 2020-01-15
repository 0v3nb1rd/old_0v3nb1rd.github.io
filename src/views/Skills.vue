<template>
  <div class="skills">
    <h1 class="body-1 grey--text">Skills</h1>
    <v-container fluid class="my-5">
      <v-row dense>
        <v-col v-for="(card,i) in cards" :key="i" class="d-flex child-flex" cols="2">
          <v-card flat tile shaped>
            <v-img :src="card.src" aspect-ratio="1" contain>
              <template v-slot:placeholder>
                <v-row class="fill-height ma-0" align="center" justify="center">
                  <v-progress-circular indeterminate color="secondary"></v-progress-circular>
                </v-row>
              </template>
            </v-img>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    cards: [
      {
        title: "Pre-fab homes",
        src: "/skills/html.png"
      },
      {
        title: "Favorite road trips",
        src: "/skills/css.png"
      },
      {
        title: "Favorite road trips",
        src: "/skills/sass.png"
      },
      {
        title: "Best airlines",
        src: "/skills/bootstrap.png"
      },
      {
        title: "Best airlines",
        src: "/skills/materialize.png"
      },
      {
        title: "Favorite road trips",
        src: "/skills/jquery.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/gulp.png"
      },
      {
        title: "Best airlines",
        src: "/skills/js.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/es6.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/ajax.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/git.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/firebase.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/nodejs.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/npm.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/yarn.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/webpack.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/vue.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/vuex.png"
      },
      {
        title: "Pre-fab homes",
        src: "/skills/vuetify.png"
      }
    ]
  })
};
</script>

<style>
</style>
