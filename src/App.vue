<script setup>
import { ref } from 'vue'
import qrCode from './assets/images/qrcode.png'

const product = ref('Socks')
const image = ref(qrCode)
const website = ref('https://main.d3fxshzbjh5gns.amplifyapp.com/')

</script>

<template>
  <div class="nav-bar"></div>
  <div class="product-display">
    <div class="product-container">
      <div class="product-image">
         <a v-bind:href="website"><img v-bind:src="image"></a>
      </div>
      <div class="product-info">
        <h1>{{ product }}</h1>
      </div>
    </div>
  </div>
</template>