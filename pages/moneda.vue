<template>
    <v-layout row justify-center align-center wrap>
   
    <v-flex xs11>
  
      <v-card>
        
          <v-toolbar dark color="blue">
            <v-toolbar-title>Moneda</v-toolbar-title>
          </v-toolbar>
        
        <v-card-text>
        
        <v-form v-model="valid">
          
          <v-select
            :items="items"
            item-text="name"
            item-value="iso"
            v-model="moneda"
            label="Select"
            single-line
          ></v-select>

          <v-text-field
              v-model="name"
              :rules="nameRules"
              :counter="10"
              label="Nombre"
              required
          ></v-text-field>

           <v-text-field
              v-model="email"
              :rules="emailRules"
              label="E-mail"
              required
          ></v-text-field>

        </v-form>
              
        </v-card-text>
      </v-card>

    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data: () => {
    return {
      valid: false,
      moneda: null,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => v.length <= 10 || 'Name must be less than 10 characters'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
      ],
      items: [
        {'iso': 'USD', 'name': 'dolar'},
        {'iso': 'VEF', 'name': 'bolivar'}
      ]
    }
  }
}
</script>

<style>

</style>
