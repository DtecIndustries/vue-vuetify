<template>
  <v-app>

    <!-- App bar -->
    <v-app-bar app dark color="primary lighten-1">
      <v-toolbar-title>Vuetify</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn 
        v-for="link in links"
        :key="`${link.label}-header-link`"
        text 
        rounded 
        :to="link.url"
      >{{ link.label }}</v-btn>

      <v-btn @click="toggleTheme" text rouded>Toggle theme</v-btn>
    </v-app-bar>

    <v-content>

      <router-view></router-view>

    </v-content>

    <!-- footer -->
    <v-footer
      color="primary lighten-1"
      padless
    >
      <v-row
        justify="center"
        no-gutters
      >
        <v-btn
          v-for="link in links"
          :key="`${link.label}-footer-link`"
          color="white"
          text
          rounded
          class="my-2"
          :to="link.url"
        >
          {{ link.label }}
        </v-btn>
        <v-col
          class="primary lighten-2 py-4 text-center white--text"
          cols="12"
        >
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-col>
      </v-row>
    </v-footer>

  </v-app>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    showPassword: false,
    links: [
      {
        label: 'Home',
        url: '/'
      },
      {
        label: 'Login',
        url: '/login'
      },
      {
        label: 'Signup',
        url: '/signup'
      },
      {
        label: 'Dashboard',
        url: '/dashboard'
      }
    ]
  }),
  methods: {
    toggleTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    }
  }
};
</script>
