<template>
  <v-app style="backgroundColor:#e6f2ff">
     <v-toolbar class="blue-grey lighten-4" flat app>
       <v-app-bar-nav-icon @click="openDrawer = !openDrawer"></v-app-bar-nav-icon>
       <v-toolbar-title>
        <span>Find-A-Key:</span>
        <span class="font-weight-light"> Your Music Theory Tool</span>
       </v-toolbar-title>
       <v-spacer></v-spacer>
        <img class="mr-3" :src="require('@/assets/musicNote.png')" height="40"/>
     </v-toolbar>

    <v-navigation-drawer v-model="openDrawer" app class="blue-grey lighten-4">
      <v-list>

        <v-list-item router to="/">
      <v-list-item-action>
        <v-icon x-large>mdi-home</v-icon>
      </v-list-item-action>
      <v-list-item-content>
      <v-list-item-title>Home</v-list-item-title>
      </v-list-item-content>
        </v-list-item>


      <v-list-item router to="/about">
      <v-list-item-action>
        <v-icon x-large>mdi-information</v-icon>
      </v-list-item-action>
      <v-list-item-content>
      <v-list-item-title>About</v-list-item-title>
      </v-list-item-content>
        </v-list-item>


       <v-list-item href="https://github.com/mikedesimone12/Find-A-Key-UI" target="_blank">
      <v-list-item-action>
        <v-icon x-large>mdi-github</v-icon>
      </v-list-item-action>
      <v-list-item-content>
      <v-list-item-title>Source Code</v-list-item-title>
      </v-list-item-content>
        </v-list-item>
        
      </v-list>
    </v-navigation-drawer>

    <v-content>
        <router-view></router-view>
    </v-content>
    <footer>Author: Michael DeSimone</footer>
  </v-app>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      openDrawer: false
    }
  }
};
</script>
