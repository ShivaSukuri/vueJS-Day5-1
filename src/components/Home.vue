<template>
<h1>computed properties</h1><hr>
{{fullName}}
</template>
<script setup>
import {ref,reactive,computed} from 'vue';

const firstName = ref('Jai')
const lastName = ref('Sri ram')


const fullName = computed({

  get() {
    return firstName.value + ' ' + lastName.value
  },

  set(newValue) {
    [firstName.value, lastName.value] = newValue.split(' ')
  }
})

fullName.value="Shiva shekhar"
console.log(fullName.value)
</script>