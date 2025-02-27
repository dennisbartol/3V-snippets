<template> 
  <div id="ticket-container">

  </div>

  <button @click="buyTickets" :disabled="isLoading" id="buy-button">
    {{ isLoading ? "Verwerken..." : `Koop ${ticketCount} Ticket(s)` }}
  </button>
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
