<template>
  <v-container fluid>
    <v-slide-y-transition mode="out-in">
      <v-layout row>
      <v-flex xs12 sm10 offset-sm1>
        <v-card>
          <v-toolbar flat color="blue" dark>
            <v-toolbar-title>Tracker</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-text> USD | EURO </v-text>
          </v-toolbar>
          <v-list width="100">
            <v-list-tile avatar style="width: 100%" v-for="(price, currency) in cryptocurrencies" :key="currency" @click="">
              <v-list-tile-avatar>
                <img :src="images[currency]">
              </v-list-tile-avatar>
              <v-list-tile-content>
                <v-list-tile-title v-text="currency"></v-list-tile-title>
              </v-list-tile-content>
              <v-list-tile-action>
                <span>${{price.USD}} | €{{price.EUR}}</span>
              </v-list-tile-action>
            </v-list-tile>
          </v-list>
        </v-card>
      </v-flex>
    </v-layout>
    </v-slide-y-transition>
  </v-container>
</template>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 40px 0 0;
}
a {
  color: #42b983;
}
</style>
<script>
  export default {
    props: ['cryptocurrencies'],
    data () {
      return {
        images: {
          BTC: 'https://www.cryptocompare.com/media/19633/btc.png',
          IOT: 'https://www.cryptocompare.com/media/1383540/iota_logo.png',
          ETH: 'https://www.cryptocompare.com/media/20646/eth_logo.png',
          XMR: 'https://www.cryptocompare.com/media/19969/xmr.png',
          LTC: 'https://www.cryptocompare.com/media/19782/litecoin-logo.png'
        }
      }
    }
  }
</script>
