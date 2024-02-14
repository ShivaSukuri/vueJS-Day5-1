<script setup lang="ts">
import Home from '@/components/Home.vue'
import Watchers2 from "@/components/Watchers2.vue"
import PropAndEmit from "@/components/PropAndEmit.vue"
import Register from "@/components/Register.vue"
import {ref,reactive} from 'vue';  

const logVisibility=ref(true);
const registerVisibility=ref(false);
const users=reactive([]);
const receiveEMit=(email,pass)=>{
users.map(user=>{
   if(email===user.email&& pass===user.password){
    alert("Hii "+user.name);
  }
})

}
const registerForm=()=>{
  console.log("Shiva");
  registerVisibility.value=!registerVisibility.value;

  logVisibility.value= ! logVisibility.value;
}
const registerUser=(Iname,Iemail,Ipassword)=>{
 const user={
        name:Iname,
        email:Iemail,
        password:Ipassword
    }
    users.push(user);
    console.log(users)
   registerVisibility.value=!registerVisibility.value;
  logVisibility.value= ! logVisibility.value;
}
</script>

<template>
  <Home />
  <Watchers2 />
  <PropAndEmit @log-in="receiveEMit" @register="registerForm" v-show="logVisibility"/>
  <Register v-show="registerVisibility" @register="registerUser"/>
</template>

<style scoped>
</style>
