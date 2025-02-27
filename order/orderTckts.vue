<template> 
  <div id="ticket-container">
   <div id="ticket-controls">
     <button @click="ticketCount = Math.max(1, ticketCount -1)">-</button>
     <button @click="ticketCount++">+</button>
  </div>
   <button @click="buyTickets" :disabled="isLoading" id="buy-button">
    {{ isLoading ? "Verwerken..." : `Koop ${ticketCount} Ticket(s)` }}
   </button>
  </div>
</template>


<script>
import { ref } from vue; 

const ticketCount = ref(1);
const isLoading = ref(false); 
const apiUrl = "Your-api-address;"

const buyTickets  { 



}
</script> 


<style scoped>

</style>
