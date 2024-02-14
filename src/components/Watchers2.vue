<template>
<h1>Watch</h1><hr>
<h1>
<button @click="decrement">-</button>
{{count}}
<button @click="increment">+</button>
</h1>
</template>
<script setup>
import {ref,watch,computed,reactive} from 'vue'
const count=ref(0);
const count1=ref(5);

const increment=()=>{
    count.value++;
}
const decrement=()=>{
    count.value--;
}
const movie=reactive({
    name:'',
    director:''
})
const movies=reactive(["HI Nanaa","salaar","asura"])


watch(count,(newCount,oldCount)=>{
    // console.log(newCount+""+oldCount)
    if(oldCount<newCount && newCount===5){
         alert("you have reached volume you may get hearing problem"+newCount)
    }
})
watch(movie,(newMovie)=>{
    console.log("Hiii"+newMovie.name)
},{deep:true,immediate:true})

watch(movies,(newMovies)=>{
    console.log(newMovies.toString());
},{deep:true,immediate:true})
</script>