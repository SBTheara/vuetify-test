<template>
  <div class="home">
    <v-carousel hide-delimiters class="d-flex justify-center" interval style="width: 100vw;">
      <v-carousel-item v-for="(item, i) in cards" :key="i" :src="item.src"></v-carousel-item>
    </v-carousel>
    <v-spacer></v-spacer>
    <v-container>
      <v-layout row class="my-5">
          <v-tooltip top>
            <template v-slot:activator="{ on, attrs }">
              <v-btn small color="transparent" @click="sortBy('title')" v-bind="attrs" v-on="on">
                <v-icon>mdi-folder</v-icon>
                <span class="caption text-lowercase">By project name</span>
              </v-btn>
            </template>
            <span>Sort by project name</span>
          </v-tooltip>
          <v-tooltip top>
            <template v-slot:activator="{ on, attrs }">
              <v-btn small color="transparent" @click="sortBy('person')" v-bind="attrs" v-on="on">
                <v-icon>mdi-account</v-icon>
                <span class="caption text-lowercase">By person</span>
              </v-btn>
            </template>
            <span>Sort by person</span>
          </v-tooltip>
      </v-layout>
      <v-card v-for="project in projects" :key="project.title">
        <v-layout row my-3 wrap :class="`d-flex align-center pa-5 project ${project.status}`">
          <v-flex xs12 md6>
            <div class="caption grey--text">Project title</div>
            <div>{{ project.title }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Person</div>
            <div>{{ project.person }}</div>
          </v-flex>
          <v-flex xs6 sm4 md2>
            <div class="caption grey--text">Due by</div>
            <div>{{project.due}}</div>
          </v-flex>
          <v-flex xs2 sm4 md2>
            <div style="width: 200px;">
              <v-chip small :class="`${project.status} white--text caption my-2`">
                {{ project.status }}
              </v-chip>
            </div>
          </v-flex>
        </v-layout>
        <v-divider></v-divider>
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
    ] ,
    projects: [
      {title: 'Design a new website',person: 'Theara',due: '1st jan 2023',status: 'ongoing'},
      {title: 'Code up the home page',person: 'Rathea',due: '12th jan 2023',status: 'complete'},
      {title: 'Design videothumbnails',person: 'Ruithea',due: '14th jan 2023',status: 'complete'},
      {title: 'Create a community forum',person: 'Thearui',due: '16th jan 2023',status: 'overdue'},
    ]
  }),
  methods:{
    sortBy(prop){
      this.projects.sort((a,b)=>a[prop] < b[prop] ? -1 : 1)
    }
  }
}

</script>
<style>
  .project.complete{
    border-left: 4px solid lightskyblue;
  }
  .project.ongoing{
    border-left: 4px solid orange;
  }
  .project.overdue{
    border-left: 4px solid tomato;
  }
  .v-chip.complete{
    border: 4px solid lightskyblue;
  }
  .v-chip.ongoing{
    border: 4px solid orange;
  }
  .v-chip.overdue{
    border: 4px solid tomato;
  }
</style>
