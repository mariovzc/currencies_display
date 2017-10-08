<template>
  <v-app id="e3" standalone>
    <main>
      <v-layout row wrap>
        <v-flex
          v-for= '(currency,index) in currencies' 
          xs12
          lg6
          offset-lg3
        >
          <v-card class="blue darken-3 white--text">
            <v-card-title class="card-container" primary-title>
              <div class="headline">{{currency.name}}-{{currency.symbol}}</div>
              <div>USD: {{currency.price_usd | format }} | BTC: {{currency.price_btc | format }} | COP: {{currency.price_cop | format}}  </div>
            </v-card-title>
          </v-card>
          </br>
        </v-flex>
      </v-layout>
    </main>
  </v-app>
</template>

<script>
  import axios from 'axios'
  
  export default {
    name: 'Main',
    data () {
      return {
        currencies: []
      }
    },
    methods: {
      seedData () {
        const self = this
        axios.get('https://api.coinmarketcap.com/v1/ticker/?convert=COP&limit=10')
          .then(function (response) {
            self.currencies = response.data
            console.log(response.data)
          })
          .catch(function (error) {
            console.log(error)
          })
      }
    },
    filters: {
      format (value) {
        let parts = value.toString().split(',')
        parts[0] = parts[0].replace(/\B(?=(\d{3})+(?!\d))/g, ',')
        return parts.join('.')
      }
    },
    mounted () {
      this.seedData()
    }
  }
</script>

<style scoped>
.card-container{
  display: table !important;
  text-align: center;
  width: 100%;
}
</style>
