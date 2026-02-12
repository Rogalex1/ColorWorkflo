<script setup>

import AfficheColor from '@/components/AfficheColor.vue';
import { ref } from 'vue';
const colors = [
    {name: "red"},
    {name: "green"},
    {name: "yellow"},
    {name: "orange"},
]


const vuColor = ref('')
function showcolor(color){
    vuColor.value = color.name ;
}

</script>


<template>
<div>
    <h1>Color Site</h1>
    <p>Appuyez sur une couleur pour la voir</p>
    <AfficheColor :vuColor="vuColor" :colors="colors" @afficheC="showcolor"></AfficheColor>

</div>
</template>


<style scoped>

div {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  color: white;
  text-align: center;
  animation: fadeIn 1s ease-in-out;
  color: black;
}

/* Titre */
h1 {
    font-size: 3rem;
    margin-bottom: 10px;
    letter-spacing: 2px;
    animation: slideDown 0.8s ease;
}

/* Sous-texte */
p {
    font-size: 1.2rem;
    opacity: 0.9;
    margin-bottom: 30px;
    animation: fadeIn 1.5s ease;
}



</style>
