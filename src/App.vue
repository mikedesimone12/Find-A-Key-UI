<template>
  <v-app style="backgroundColor:#e6f2ff">
      <v-app-bar app fixed scroll-target="#scroll"> <!-- TODO: fix this and use v-navigation-bar so it works on mobile -->
      <v-toolbar-icon>
        <v-img
          alt="App Logo"
          class="shrink mr-2"
          contain
          src="https://pixy.org/src/16/166349.png"
          transition="scale-transition"
          width="40"
        />
      </v-toolbar-icon>
      <v-toolbar-title><b>Find-A-Key:</b> Your Music Theory Tool</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn text to='/'>Home</v-btn>
        <v-btn text to='/About'>About</v-btn>
      </v-toolbar-items>
      <v-menu>
        <v-toolbar-side-icon slot="activator"></v-toolbar-side-icon>
        <v-list>
          <v-list-tile>
            <v-list-tile-content>
              <v-list-tile-title>Home</v-list-tile-title>
              <v-list-tile-title>About</v-list-tile-title>
             </v-list-tile-content>
          </v-list-tile>   
        </v-list>
      </v-menu>
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
