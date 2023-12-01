<template>
  <div class="home">
    <v-carousel hide-delimiters>
      <v-carousel-item v-for="(item, i) in cards" :key="i" :src="item.src"></v-carousel-item>
    </v-carousel>
    <v-spacer></v-spacer>
    <v-container>
      <v-card flat>
        <v-layout row my-3 wrap class="d-flex align-center pa-5">
          <v-flex xs12 md6 v-for="(item,i) in items" :key="i">
            <div>
              <v-img
                :src="item.img"
                position="center"
                cover>
              </v-img>
            </div>
          </v-flex>
          <v-divider></v-divider>
        </v-layout>
      </v-card>
    </v-container>
  </div>
</template>

<script>

export default {
  name: 'HomeView',
  data: () => ({
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
    items: [
      {title:"My bike",img: 'https://myer-media.com.au/wcsstore/MyerCatalogAssetStore/images/77/776/7855/1/1/959274370/959274370_2_720x928.webp'},
      {title:"My bike",img: 'https://www.voltes.eu/cdn/shop/files/bird-bike-stealth-black-1.png?v=1687364572'},
      {title:"My bike",img: 'https://www.fujibikes.com/cdn/shop/products/2022_FUJI_JARI_11_MATTEBLACK_FRONT.png?v=1670262316&width=580'},
    ]
  }),
}

</script>
