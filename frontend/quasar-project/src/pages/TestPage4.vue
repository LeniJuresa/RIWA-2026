<template>
  <q-page padding>

    <div class="q-pa-md row items-start q-gutter-md">
      <q-card class="my-card">
        <q-card-section>
          <div class="text-h4">{{ dodaj }}</div>
        </q-card-section>

        <q-separator />
        <q-card-actions vertical>
          <q-btn push color="white" icon="+1" text-color="primary" label="Uvečaj" @click="uvecaj()"></q-btn>
          <q-btn push color="red" icon="delete" label="Resetiraj" @click="resetiraj()"></q-btn>
        </q-card-actions>
      </q-card>
    </div>

    <br>
    <div>
      <q-input style="max-width: 300px" v-model="unos1" label="Unesi 1. broj" />
      <q-input style="max-width: 300px" v-model="unos2" label="Unesi 2. broj" />

      <q-btn push color="white" icon="+1" v-model="zbrajanje" text-color="primary" label="zbroji"
        @click="zbroji()"></q-btn>
      <q-card-section>
        <div class="text-h4">Rezultat <br>{{ zbrajanje }}</div>
      </q-card-section>
    </div>

    <br>
    <br>
    <div>
      <q-input style="max-width: 300px" v-model="tekst" label="unos teksta" />

      <q-btn push color="white" v-model="tekst" text-color="primary" label="unos teksta"
        @click="spremi()"></q-btn>

      <q-card-section class="text-h4" v-for="t in tekstovi" key="t">
        {{ t }}
      </q-card-section>
    </div>

  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const dodaj = ref(0)
const zbrajanje = ref(0)
const unos1 = ref('')
const unos2 = ref('')
const tekst = ref('')

const tekstovi = ref([])


function uvecaj() {
  dodaj.value += 1;
  console.log("Uvećaj ")
}
function resetiraj() {
  console.log("Resetiraj " + dodaj.value + ", vraćeno na 0")
  dodaj.value = 0;
}

function zbroji() {
  zbrajanje.value = Number(unos1.value) + Number(unos2.value)
  console.log("ispis zbrajanja = " + zbrajanje.value)
}

function spremi() {
  tekstovi.value.push(tekst.value)
  console.log("uspješno je dodan u listu" + tekstovi.value)
}



</script>
