<template>
  <v-app class="grey darken-4">
    <v-app-bar class="grey darken-3 align-end" app height="100px" width="100%">
      <v-app-bar-nav-icon @click="drawer = !drawer" plain class="grey--text text--lighten-3"></v-app-bar-nav-icon>
      <v-toolbar-title class="font-weight-bold">
        <span class="grey--text text--lighten-3">Movie</span>
        <span class="red--text text-darken-3">App</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-text-field class="mt-6" outlined rounded append-icon="mdi-magnify" dense>
      </v-text-field>
      <v-spacer></v-spacer>
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="grey darken-3" dark v-bind="attrs" v-on="on">
            <v-icon left>mdi-menu</v-icon>
            Menu
          </v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in navItems" :key="index" router :to='item.to'>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-btn text plain><v-icon>mdi-share</v-icon></v-btn>
    </v-app-bar>
    <v-navigation-drawer class="grey darken-3" v-model="drawer" app>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title>
            <span class="text-h6 grey--text text--lighten-3 font-weight-bold">Movie</span>
            <span class="text-h6 red--text font-weight-bold">App</span>
          </v-list-item-title>
          <v-list-item-subtitle class="grey--text text--lighten-3 font-weight-bold">
            The best website movie in the pagoda
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
      <v-layout align-center column>
        <v-flex class="mt-5">
          <v-avatar size="100">
            <img
              src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSRlx_ZxZnn33pT4_Ydh5Z8ehzIm4x6FgE_Qw&usqp=CAU">
          </v-avatar>
          <p class="white--text mt-1">Tony Stark</p>
        </v-flex>
        <v-flex class="mt-3 mb-3">
          <PopupForm></PopupForm>
        </v-flex>
      </v-layout>
      <v-divider></v-divider>
      <v-list dense nav>
        <v-list-item v-for="item in navItems" :key="item.title" link class="grey--text text--lighten-3 font-weight-bold"
          router :to="item.to">
          <v-list-item-icon>
            <v-icon class="grey--text text--lighten-3 font-weight-bold">{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
import PopupForm from './component/PopupForm'
export default {
  name: 'App',
  components: {PopupForm},
  data: () => ({
    drawer: false,
    items: [
      {
        src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
      },
      {
        src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
      },
      {
        src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
      },
      {
        src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
      },
    ],
    cards: [
      { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
      { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
      { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
      { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
      { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
      { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
      { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
      { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
      { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },

    ],
    navItems: [
      { title: 'Dashboard', icon: 'mdi-view-dashboard', to: "/" },
      { title: 'Top movie', icon: 'mdi-movie', to: "/movie" },
      { title: 'About', icon: 'mdi-help-box', to: "/about" },
    ],

  }),
  mounted: {
    drawer : false
  }
}

</script>
