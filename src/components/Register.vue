<template>
<div>
Name:
<input type=text v-model="Iname">
email:<input type=text v-model="Iemail">
pass:<input type=text v-model="Ipassword">
<button @click="$emit('register',Iname,Iemail,Ipassword)">Register</button>
</div>
</template>
<script setup>
import {ref,reactive} from "vue"
const Iname=ref('');
const Iemail=ref('');
const Ipassword=ref('');
defineEmits(["register"]);

</script>