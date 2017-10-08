<template>
  <v-app id="e3" standalone>
    <main>
      <v-layout row wrap>
        <v-flex 
          xs8
          lg8
          offset-xs2
        >
          <v-card class="blue-grey darken-2 white--text">
            <v-card-title primary-title>
              <div class="headline">Unlimited music now</div>
              <div>Listen to your favorite artists and albums whenenver and wherever, online and offline.</div>
            </v-card-title>
            <v-card-actions>
              <v-btn flat dark>Listen now</v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </main>
  </v-app>
</template>

<script>
export default {
  name: 'Main'
}
</script>

<!--<style scoped> Scoped to limit the css only for this class
 
</style>
-->