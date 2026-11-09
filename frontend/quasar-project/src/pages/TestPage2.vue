<template>
  <q-page padding>
    <div>
      <q-input color="purple_12" label="Unesi ime" v-model="input"></q-input>
      <br>
      <q-btn @click="dodajIme()">Dodaj</q-btn>
    </div>
    <br>
    <p v-for="imena in kolega" :key="imena">
    <p v-if="imena == 'ivan'" v-show="false">
      {{ imena }} *
    </p>
    <p v-else>
      {{ imena }}
    </p>
    </p>

    <!-- QBadge -->
    <div class="q-pa-md q-gutter-sm">
      <q-btn push color="white" text-color="primary" label="Add"@click="addMail()">
        <q-badge color="orange" v-model="addmsg" floating  >{{ addmsg }}</q-badge>
      </q-btn>
      <q-btn dense color="purple" icon="email" label="remove" @click="delMail()">
        <q-badge color="red" v-model="delmsg" floating >{{ delmsg }}</q-badge>
      </q-btn>

    </div>


  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const addmsg = ref(0)
const delmsg = ref(20)


const kolega = ['karol', 'alan', 'ratko', 'ivan', 'david']

const input = ref('')
input.value = "";


function dodajIme() {
  console.log(input.value);
}

function addMail(){
  addmsg.value += 1;
  console.log("read " + addmsg.value)
}
function delMail(){
  delmsg.value -= 1;
  console.log("delete " + delmsg.value)
}





</script>
