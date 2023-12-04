<template>
  <v-dialog transition="dialog-top-transition" max-width="600">
    <template v-slot:activator="{ on, attrs }">
      <v-btn color="primary" v-bind="attrs" v-on="on">Add new projects</v-btn>
    </template>
    <template v-slot:default="dialog">
      <v-card>
        <v-toolbar color="primary" dark>Form new project</v-toolbar>
        <v-card-text>
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-text-field v-model="name" :counter="10" :rules="nameRules" label="Name" required></v-text-field>

            <v-text-field v-model="email" :rules="emailRules" label="Title" required></v-text-field>

            <v-select v-model="select" :items="items" :rules="[v => !!v || 'Item is required']" label="Item"
              required></v-select>

            <v-menu v-model="menu2" :close-on-content-click="false" max-width="290">
              <template v-slot:activator="{ on, attrs }">
                <v-text-field :value="computedDateFormattedDatefns" clearable label="Formatted with datefns" readonly
                  v-bind="attrs" v-on="on" @click:clear="date = null"></v-text-field>
              </template>
              <v-date-picker v-model="date" @change="menu2 = false"></v-date-picker>
            </v-menu>

            <v-checkbox v-model="checkbox" :rules="[v => !!v || 'You must agree to continue!']" label="Do you agree?"
              required></v-checkbox>

            <v-btn :disabled="!valid" color="success" class="mr-4" @click="validate">
              Validate
            </v-btn>

            <v-btn color="error" class="mr-4" @click="reset">
              Reset Form
            </v-btn>

            <v-btn color="warning" @click="resetValidation">
              Reset Validation
            </v-btn>
          </v-form>
        </v-card-text>
        <v-card-actions class="justify-end">
          <v-btn text @click="dialog.value = false">Close</v-btn>
        </v-card-actions>
      </v-card>
    </template>
  </v-dialog>
</template>
<script>
import { format, parseISO } from 'date-fns'
export default {
  data: () => ({
    valid: true,
    due: null,
    name: '',
    nameRules: [
      v => !!v || 'Name is required',
      v => (v && v.length <= 10) || 'Name must be less than 10 characters',
    ],
    email: '',
    emailRules: [
      v => !!v || 'Title is required',
      v => (v && v.length <= 10) || 'Title must be less than 10 characters',
    ],
    select: null,
    items: [
      'ongoing',
      'complete',
      'overdue',
      'expired',
    ],
    date: format(parseISO(new Date().toISOString()), 'yyyy-MM-dd'),
    menu2: false,
  }),
  computed: {
    computedDateFormattedDatefns () {
        return this.date ? format(parseISO(this.date), 'do MMM yyyy') : ''
      },
  },
  methods: {
    validate() {
      this.$refs.form.validate()
    },
    reset() {
      this.$refs.form.reset()
    },
    resetValidation() {
      this.$refs.form.resetValidation()
    },
  },
}
</script>