<template>
    <v-layout align-center justify-center>
          <v-flex xs12 sm8 md4>
            
            <v-card class="elevation-12">
              
              <v-toolbar dark color="red">
                <v-toolbar-title>Acceso</v-toolbar-title>
                <v-spacer></v-spacer>
              </v-toolbar>

              <v-card-text>
               
                <v-form v-model="valid">

                  <v-text-field 
                    prepend-icon="person" 
                    label="Usuario" 
                    type="text"
                    v-model.trim="form.usuario"
                    @input="$v.form.usuario.$touch()"
                    @blur="$v.form.usuario.$touch()"
                    :errors="formErrors.usuario"
                  ></v-text-field>
                  
                  <v-text-field 
                    prepend-icon="lock" 
                    name="password" 
                    label="Password" 
                    type="password"
                    v-model.trim="form.password"
                    @input="$v.form.password.$touch()"
                    @blur="$v.form.password.$touch()"
                    :errors="formErrors.password"
                  ></v-text-field>
               
                </v-form>
                <pre>{{$v.usuario}}</pre>
              </v-card-text>

              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn color="primary">Login</v-btn>
              </v-card-actions>

            </v-card>
          </v-flex>
    </v-layout>
</template>

<script>

import { required } from 'vuelidate/lib/validators'
import fieldErrMixin from 'vuetifylidate-mixin'

export default {
  layout: 'login',
  mmixins: [fieldErrMixin],
  data: () => ({
    valid: true,
    form: {
      usuario: '',
      password: ''
    },
    formErrors: {
      usuario: [],
      password: [] // The array (must be array required by vuetify)
    }
  }),
  validations: {
    form: {
      usuario: {
        required
      },
      password: {
        required
      }
    }
  }
}
</script>

<style>

</style>
