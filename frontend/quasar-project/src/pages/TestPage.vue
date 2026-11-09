<template>
  <q-page padding>
    <p v-html="msgHtml"></p>
    {{ msgHtml }}
    <br>
    {{ msg }}
  <p v-text="msg"></p>

    <p v-for="item in days" :key="item">
      <button v-if="item=='Ponedjeljak'">
        {{item}} *
      </button>
      <button v-else-if="item=='Srijeda'">
        {{ item }} **
      </button>
      <button v-else>
        {{ item }} 
      </button>
    </p>

    <a :href="link.url" :target="link.target"> {{link.text}} </a>
    <br>
    

    <q-input color="purple_12" v-model="input" label="item name"></q-input>

  </q-page>
</template>

<script setup>

import { ref } from 'vue'
const msg = "MSG"
const msgHtml = "<h1>Naslov msgHtml</h1>"
const days = ['Ponedjeljak', 'Utorka', 'Srijeda', 'Četvrtak', 'Petak'];

const link = {
  url: 'http://www.google.com',
  target: '_blank',
  text: 'Googel'
}

const input = ref('')
input.value = "Hello"

</script>
