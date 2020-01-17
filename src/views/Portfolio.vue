<template>
  <div class="portfolio">
    <h1 class="body-1 grey--text">Portfolio</h1>
    <v-container class="my-5">
      <v-row no-gutters>
        <v-col
          cols="12"
          sm="6"
          md="4"
          lg="3"
          v-for="person in team"
          :key="person.name"
        >
          <v-hover v-slot:default="{ hover }">
            <v-card
              flat
              :elevation="hover ? 12 : 2"
              :class="{ 'on-hover': hover }"
              class="text-center ma-3"
            >
              <!-- <v-responsive class="pt-4"> -->
              <!-- <v-avatar size="100"> -->
              <a href="#"
                ><v-img :src="person.avatar">
                  <div class="fill-height bottom-gradient"></div> </v-img
              ></a>

              <!-- </v-avatar> -->
              <!-- </v-responsive> -->
              <v-card-text>
                <div class="subheader">{{ person.name }}</div>
                <div class="grey--text">{{ person.role }}</div>
              </v-card-text>
              <v-card-actions class="justify-space-around flex-grow-1">
                <v-btn text color="grey darken-2" outlined class="flex-grow-1">
                  <v-icon small left>mdi-github-circle</v-icon>
                  <span>Code</span>
                </v-btn>
                <v-btn text color="grey darken-2" outlined class="flex-grow-1">
                  <v-icon small left>mdi-search-web</v-icon>
                  <span>Visit</span>
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    team: [
      {
        name: "Nazar Khaylo",
        role: "Front-end developer",
        avatar: "/portfolio/mishka/1.png"
      },
      {
        name: "Volodymir Yarmochenko",
        role: "Incourance agent",
        avatar: "/portfolio/glacy/1.png"
      },
      {
        name: "Ruslan Dembickiy",
        role: "Uber driver",
        avatar: "/portfolio/nerds/1.png"
      },
      {
        name: "Vasil Paral",
        role: "Polish worker",
        avatar: "/portfolio/sedona/1.png"
      },
      {
        name: "Ira Horchinska",
        role: "Administrator of restourant",
        avatar: "/portfolio/avatar_5.jpg"
      },
      {
        name: "Ira Horchinska",
        role: "Administrator of restourant",
        avatar: "/portfolio/avatar_1.jpg"
      },
      {
        name: "Ira Horchinska",
        role: "Administrator of restourant",
        avatar: "/portfolio/avatar_2.jpg"
      },
      {
        name: "Ira Horchinska",
        role: "Administrator of restourant",
        avatar: "/portfolio/avatar_3.jpg"
      },
      {
        name: "Ira Horchinska",
        role: "Administrator of restourant",
        avatar: "/portfolio/avatar_4.jpg"
      }
    ]
  })
};
</script>

<style lang="scss" scoped></style>
