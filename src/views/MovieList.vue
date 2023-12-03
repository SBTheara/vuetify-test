<template>
    <div>
        <v-container class="my-5 pa-10">

            <v-layout row wrap>
                <v-flex xs12 sm6 md4 lg3 v-for="person in team" :key="person.name">
                    <v-card flat class="pa-10 green text-xs-center ma-3">
                        <v-responsive class="pt-4">
                            <v-avatar size="80" class="yellow">
                                <v-img :src="`${person.avatar}`"></v-img>
                            </v-avatar>
                        </v-responsive>
                        <v-card-text>
                            <div class="subheading">
                                {{ person.name }}
                            </div>
                            <div class="grey--text caption">{{ person.role }}</div>
                        </v-card-text>
                        <v-card-action>
                            <v-btn flat color="grey">
                                <v-icon small left>mdi-message</v-icon>
                                <span>Message</span>
                            </v-btn>
                        </v-card-action>
                    </v-card>
                </v-flex>
            </v-layout>
        </v-container>

    </div>
  </template>
  <script>
    export default {
        data: () => ({
            team: [
                { name: 'Tony Stark', role: 'Developer',avatar:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSRlx_ZxZnn33pT4_Ydh5Z8ehzIm4x6FgE_Qw&usqp=CAU' },
                { name: 'Kratos', role: 'Developer',avatar:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTF5xtThYcgH7ftAuxhrx-I83QkHQ0grVkULQ&usqp=CAU' },
            ]
        }),
    } 
  </script>