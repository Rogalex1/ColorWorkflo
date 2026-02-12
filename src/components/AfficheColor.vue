<script setup>
import { ref } from 'vue';
const props = defineProps({
    colors: Array,
    vuColor: String,
});
const emit = defineEmits(['afficheC'])
function afficheColor(color){
    emit("afficheC", color)
}

</script>


<template>
<div>
    
    <div>
        <button  v-for="color in colors" @click="afficheColor(color)" >{{ color.name }}</button>
    </div>

    <div class="colorBack" v-if="vuColor" :style="{backgroundColor: vuColor}">
        
    </div>



</div>
</template>


<style scoped>

div {
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Container des boutons */
div > div:first-child {
  margin-bottom: 30px;
}

/* Boutons modernes */
button {
  margin: 8px;
  padding: 12px 22px;
  border: none;
  border-radius: 30px;
  letter-spacing: 1px;
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(0,0,0,0.2);
}


/* Click animation */
button:hover {
  transform: scale(1.5);
}

/* Box couleur */
.colorBack {
  width: 280px;
  height: 200px;
  border-radius: 20px;
  margin-top: 20px;
  transition: background-color 0.5s ease, transform 0.4s ease;
  animation: fadeInBox 0.6s ease;
  box-shadow: 0 15px 35px rgba(0,0,0,0.3);
}

/* Animation apparition */


</style>
