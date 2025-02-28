<template>

  
<button @click="addTicket">Koop een ticket</button>
<button @click="resetCount">Reset</button>
<p>Het aantal tickets dat al is verkocht: {{ count }} </p>
</template>

<script>
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
