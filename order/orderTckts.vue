<template> 
  <div id="ticket-container">
   <div id="ticket-controls">
     <button @click="ticketCount = Math.max(1, ticketCount -1)">-</button>
         <span>{{ ticketCount }}</span>
     <button @click="ticketCount++">+</button>
  </div>
   <button @click="buyTickets" :disabled="isLoading" id="buy-button">
    {{ isLoading ? "Verwerken..." : `Koop ${ticketCount} Ticket(s)` }}
   </button>
  </div>
</template>


<script>
import { ref } from "vue"; 
import axios from "axios"; 

const ticketCount = ref(1);
const isLoading = ref(false); 
const apiUrl = "https://www.your-api-address.net";

const buyTickets = async () =>  { 
    try {
     isLoading.value = true; 

      const response = await axios.post(apiUrl, {
        customerId: 1234567890, 
        tickets: ticketCount.value, 
      });

      alert(`Succesvol ${ticketCount.value} tickets gekocht!`);
      } catch (error) { 
        alert("Fout bij het aanschaffen van tickets. Probeer het opnieuw.");
      }
      finally {
        isLoading.value = false; 
      }
 
  };
</script> 


<style scoped>

#ticket-container { 
  display: flex; 
  flex-direction: column; 
  align-items: center; 
}

#ticket-controls {
  display: flex; 
  align-items: center; 
  gap: 1em; 
}

#buy-button
  padding: 1.5em; 
  background-color: dodgerblue; 
  color: ghostwhite; 
  border: none; 
  cursor: pointer; 

#buy-button:disabled { 
  background-color: red; 
}
</style>
