<template>
  <v-app class="grey darken-4">
    <v-app-bar class="align-end" absolute height="100px" width="100%">
        <v-app-bar-nav-icon @click="drawer = !drawer" plain class="grey--text text--lighten-3"></v-app-bar-nav-icon>
        <v-toolbar-title class="font-weight-bold">
          <span class="grey--text text--darken-3">Movie</span>
          <span class="red--text text-darken-3">App</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-text-field
          class="mt-6"
          outlined
          rounded
          append-icon="mdi-magnify"
          dense
        >
      </v-text-field>
      <v-spacer></v-spacer>
        <v-btn flat plain><v-icon>mdi-share</v-icon></v-btn>
    </v-app-bar>
    <v-navigation-drawer
          v-model="drawer"
          app
        >
        </v-navigation-drawer>
    <v-main>
      <v-carousel class="px-14" hide-delimiters>
        <v-carousel-item
          v-for="(item,i) in cards"
          :key="i"
          :src="item.src"
        ></v-carousel-item>
      </v-carousel>
      <v-spacer></v-spacer>
      <v-container>
        <v-row>
          <v-col
            v-for="card in cards"
            :key="card"
            cols="4"
          >
            <v-card height="200"><v-img :src="card.src"></v-img></v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>

  export default {
    data: () => ({ 
      drawer: null ,
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
    
    }),
  }

</script>
