<template>
  <div class="portfolio">
    <h1 class="body-1 grey--text">Portfolio</h1>
    <v-container class="my-5">
      <v-row no-gutters>
        <v-col cols="12" sm="6" md="4" lg="3" v-for="person in team" :key="person.name">
          <v-card flat class="text-center ma-3">
            <v-responsive class="pt-4">
              <!-- <v-avatar size="100"> -->
              <v-img :src="person.avatar"></v-img>
              <!-- </v-avatar> -->
            </v-responsive>
            <v-card-text>
              <div class="subheader">{{ person.name }}</div>
              <div class="grey--text">{{ person.role }}</div>
            </v-card-text>
            <v-card-actions>
              <v-btn text color="grey">
                <v-icon small left>mdi-message</v-icon>
                <span>Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
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
        avatar: "/portfolio/avatar_1.jpg"
      },
      {
        name: "Volodymir Yarmochenko",
        role: "Incourance agent",
        avatar: "/portfolio/avatar_2.jpg"
      },
      {
        name: "Ruslan Dembickiy",
        role: "Uber driver",
        avatar: "/portfolio/avatar_3.jpg"
      },
      {
        name: "Vasil Paral",
        role: "Polish worker",
        avatar: "/portfolio/avatar_4.jpg"
      },
      {
        name: "Ira Horchinska",
        role: "Administrator of restourant",
        avatar: "/portfolio/avatar_5.jpg"
      }
    ]
  })
};
</script>

<style>
</style>