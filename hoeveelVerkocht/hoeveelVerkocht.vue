<template>

<div id="vk-container">
<button @click="addTicket">Koop een ticket</button>
<button @click="resetCount">Reset</button>
<p>Het aantal tickets dat al werd verkocht: {{ count }} </p>
</div> 
  
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'; 

const count = ref(0); 
const tickets = ref ([]);

let interval = null; 

const addTicket = () => {
  tickets.value.push({ id: tickets.value.length + 1, timestamp: new Date()});
  count.value = tickets.value.length; 
}

const startCounting = () => { 
  if (!interval) { 
      interval = setInterval(addTicket, 2200);
  }
}

const stopCounting = () => {
  if (interval) { 
    clearInterval(interval) 
    interval = null; 
  }
}
  

const resetCount = () => {
  tickets.value = [];
  count.value = 0; 
}

onMounted(startCounting);
onUnmounted(stopCounting); 
  
</script>

<style scoped>

body { 
  margin: 0; 
  padding: 0; 
  height: 100vh; 
  width: 100%; 
  display: flex; 
  justify-content: center; 
  align-items: center; 
  background-color: #222; 
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif; 
  color: ghostwhite; 
}


</style>
