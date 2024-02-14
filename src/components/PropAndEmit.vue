<template>

<table>
    <tr>
     <td><label for="">Email</label></td>
    <td><input type="email" name="" value="" v-model="email" required></td>
    </tr>
    <tr>
    <td><label for="">password</label></td>
    <td><input type="password" name="" value="" v-model="password" required></td>
    </tr>
        <tr>
    <td></td>
    <td><button @click="$emit('logIn',email,password)">LogIn</button> <button @click="$emit('register')">Register</button></td>
   
    </tr>
    
</table>
</template>
<script setup>
import {ref,reactive,computed} from 'vue';
const email=ref('')
const password=ref('')
defineProps(["userName","password","visibility"])
defineEmits(["logIn","register"])
</script>