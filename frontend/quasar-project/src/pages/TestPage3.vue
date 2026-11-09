<template>
  <q-page padding>




    <!-- QBadge -->
    <div class="q-pa-md q-gutter-sm">
      <q-btn push color="white" text-color="primary" label="Add" @click="addMail()">
        <q-badge color="orange" v-model="addmsg" floating>{{ addmsg }}</q-badge>
      </q-btn>
      <q-btn dense color="red" label="remove" @click="delMail()">
        <q-badge color="red" v-model="delmsg" floating>{{ delmsg }}</q-badge>
      </q-btn>

    </div>


        <!-- QCard -->
    <div class="q-pa-md row items-start q-gutter-md">
      <q-card class="my-card bg-secondary text-white" v-for="item in msg" :key="item">
        <q-card-section>
          <div class="text-h6">{{ item.title }}</div>
          <div class="text-subtitle2">by {{ item.author }}</div>
        </q-card-section>
        <q-card-section>
          {{ item.text }}
        </q-card-section>

        <q-separator dark />
        <q-card-actions>
          <q-btn flat @click="naslov()">Naslov</q-btn>
          <q-btn flat @click="autor()">Autor</q-btn>
          <q-btn flat @click="tekst()">Tekst</q-btn>
        </q-card-actions>
      </q-card>
    </div>

  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const addmsg = ref(0)
const delmsg = ref(20)


const input = ref('')
input.value = "";


function addMail() {
  addmsg.value += 1;
  console.log("read " + addmsg.value)
}
function delMail() {
  delmsg.value -= 1;
  console.log("delete " + delmsg.value)
}

const lorem = "hello"


const msg = [
  {
    title: 'Changing planet',
    author: 'John Doe',
    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, ...'
  },
  {
    title: 'New planet',
    author: 'Johndoe',
    text: 'Lorem ipsum.'
  },
  {
    title: 'New update',
    author: 'Doe',
    text: 'Lorem.'
  },
]

</script>
