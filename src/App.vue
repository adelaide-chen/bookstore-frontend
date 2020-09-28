<template>
  <v-app>
    <v-app-bar app>
      <v-spacer></v-spacer>
      <router-link to="/" tag="v-toolbar-title">
        <v-toolbar-title
            @click="numItems = 1"
            style="cursor: pointer"
        >
          Bookstore
        </v-toolbar-title>
      </router-link>
      <v-spacer></v-spacer>
      <v-btn
          color="primary"
          to="/checkout"
      >
        <v-icon>mdi-cart</v-icon>
        {{ numItems }}
      </v-btn>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-main>

      <!-- Provides the application the proper gutter -->
      <v-container>
        <!-- If using vue-router -->
        <router-view></router-view>
      </v-container>

    </v-main>

    <v-footer app>
      <!-- -->
    </v-footer>
  </v-app>
</template>

<script>

export default {
  name: 'app',
  data: () => ({
    items: [
      { title: 'Dashboard', icon: 'mdi-view-dashboard' },
      { title: 'Photos', icon: 'mdi-image' },
      { title: 'About', icon: 'mdi-help-box' },
    ],
    numItems: 0,
  }),
}

</script>