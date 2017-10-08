<template>
  <v-layout id="menu" row>
    <v-flex xs12 sm12>
      <v-card>
        <v-card-title class="blue white--text">
          <span class="headline">{{title}}</span>
          <v-spacer></v-spacer>
          <v-menu bottom left>
            <v-btn icon slot="activator" dark>
              <v-icon>more_vert</v-icon>
            </v-btn>
            <v-list>
              <v-list-tile v-for="item in items" :key="item.title">
                <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              </v-list-tile>
            </v-list>
          </v-menu>
        </v-card-title>
      </v-card>
    </v-flex>
  </v-layout>  
</template>
<script>
  export default {
    name: 'Nav',
    data () {
      return {
        title: 'Criptomonedas',
        items: [
          {title: 'Titulo 1'},
          {title: 'Titulo 2'},
          {title: 'Titulo 3'}
        ]
      }
    }
  }
</script>
<style scoped>
  #menu{
    margin-bottom: 20px;
  }
</style>


