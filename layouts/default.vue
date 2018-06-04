<template>
 
  <v-app>
    
    <!-- Menu Izquierdo -->
    <v-navigation-drawer dark  :mini-variant.sync="miniVariant" clipped v-model="drawer" fixed app>

     
      <v-list>
        
        <v-list-tile router :to="item.to" :key="i" v-for="(item, i) in items" exact>
          
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        
        </v-list-tile>

      </v-list>

  
 
    </v-navigation-drawer>
    
    <!-- Menu Superior -->
    <v-toolbar color="red" dark fixed clipped-left app>

      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      
      <v-toolbar-title v-text="title"></v-toolbar-title>

      <v-btn icon @click.stop="miniVariant = !miniVariant" >
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn icon  @click.stop="1" >
        <v-icon>notification_important</v-icon>
      </v-btn>
      
      <v-btn icon  @click.stop="1" >
        <v-icon>help</v-icon>
      </v-btn>

      <v-btn icon  @click.stop="1" >
        <v-icon>account_circle</v-icon>
      </v-btn>

    </v-toolbar>
    
    <!-- Contenido  -->
    <v-content>

      <v-container fluid>
        
       <nuxt/>

      </v-container>
    
    </v-content>
    
    <v-footer app>
      Bandes 2018
    </v-footer>

</v-app>

</template>


<script>
  export default {
    data () {
      return {
        drawer: true,
        items: [
          { icon: 'attach_money', title: 'Moneda', to: '/moneda' },
          { icon: 'bubble_chart', title: 'Inspire', to: '/inspire' }
        ],
        miniVariant: true,
        title: 'Bandes'
      }
    }
  }
</script>
