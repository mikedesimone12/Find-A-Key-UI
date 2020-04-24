<template>
  <v-app style="backgroundColor:#e6f2ff">
      <v-app-bar app fixed> <!-- TODO: fix this and use v-navigation-bar so it works on mobile -->
      <v-toolbar-title><b>Find-A-Key:</b> Your Music Theory Tool</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn text to='/'>Home</v-btn>
        <v-btn text to='/About'>About</v-btn>
      </v-toolbar-items>
    </v-app-bar>
    <v-content>
        <router-view></router-view>
    </v-content>
    <footer>Author: Michael DeSimone</footer>
  </v-app>
</template>
<script>

export default {
  name: 'App',
};
</script>
