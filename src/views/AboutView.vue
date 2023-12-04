<template>
  <div class="projects">
    <h1 class="subheading grey--text pa-10">Projects</h1>
    <v-container class="mt-5">
      <v-expansion-panels focusable>
        <v-expansion-panel v-for="(project, i) in projects" :key="i">
          <v-expansion-panel-header>{{ project.title }}</v-expansion-panel-header>
          <v-expansion-panel-content>
            {{ project.content }}
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>
  </div>
</template>
<script>
export default {
  data() {
    return {
      projects: [
        { title: 'Design a new website', person: 'Theara', due: '1st jan 2023', status: 'ongoing', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis ipsa error optio ea est veniam aliquid fugiat molestias voluptatibus magni? Praesentium tenetur vel quo eius, laborum architecto. Illum, quis quia.' },
        { title: 'Code up the home page', person: 'Rathea', due: '12th jan 2023', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis ipsa error optio ea est veniam aliquid fugiat molestias voluptatibus magni? Praesentium tenetur vel quo eius, laborum architecto. Illum, quis quia.' },
        { title: 'Design videothumbnails', person: 'Ruithea', due: '14th jan 2023', status: 'complete', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis ipsa error optio ea est veniam aliquid fugiat molestias voluptatibus magni? Praesentium tenetur vel quo eius, laborum architecto. Illum, quis quia.' },
        { title: 'Create a community forum', person: 'Thearui', due: '16th jan 2023', status: 'overdue', content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis ipsa error optio ea est veniam aliquid fugiat molestias voluptatibus magni? Praesentium tenetur vel quo eius, laborum architecto. Illum, quis quia.' },
      ]
    }
  }
}
</script>
