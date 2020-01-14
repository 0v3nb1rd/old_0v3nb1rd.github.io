<template>
  <nav>
    <v-navigation-drawer
      class="primary"
      color="indigo"
      v-model="drawer"
      width="220"
      floating
      app
    >
      <div class="d-flex flex-column align-center mt-10">
        <v-avatar size="100" class="align-center">
          <img src="@/assets/ava.jpg" />
        </v-avatar>
        <p class="mt-1 white--text">Nazar Khaylo</p>
        <Portfolio />
      </div>

      <v-list nav>
        <v-list-item
          v-for="(link, index) of links"
          :key="index"
          :to="link.roure"
        >
          <v-list-item-action>
            <v-icon class="white--text">{{ link.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title class="white--text">{{
              link.text
            }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app flat>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-spacer></v-spacer>

      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn text color="grey" v-on="on">
            <v-icon>mdi-chevron-down</v-icon>
            <span>Menu</span>
          </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="link in links" :key="link.text" :to="link.roure">
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn text color="grey">
        <span>Sign Out</span>
        <v-icon right>mdi-exit-to-app</v-icon>
      </v-btn>
    </v-app-bar>
  </nav>
</template>

<script>
import Portfolio from "./Portfolio";
export default {
  components: {
    Portfolio
  },
  props: {
    source: String
  },

  data: () => ({
    drawer: null,
    links: [
      { icon: "mdi-home", text: "Home", roure: "/" },
      { icon: "mdi-briefcase", text: "Portfolio", roure: "/portfolio" },
      { icon: "mdi-xml", text: "Skills", roure: "/skills" },
      { icon: "mdi-information", text: "About", roure: "/about" },
      { icon: "mdi-account-box", text: "Contacts", roure: "/contacts" }
    ]
  })
};
</script>
