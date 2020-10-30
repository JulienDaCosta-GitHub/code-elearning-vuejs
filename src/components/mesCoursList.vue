<template>
    <div class="container w-4/5 mx-auto mt-4">
    <h1 class="text-lg font-bold">Mes cours :</h1>

    <div v-if="mesCours.length == 0">
      <p>Vous n'avez aucun cours</p>
    </div>
    <div v-else>
      <div
        v-for="unCours in mesCours"
        :key="unCours.nom" 
        class="border border-black my-4 p-2"
      >
        <h2 class="text-lg font-bold">{{ unCours.nom }}</h2>
        <img class="mb-5" :src="require('../assets/img/' + unCours.image)" />
        <h2><span>Difficulté :</span> {{ unCours.difficulte }}</h2>
        <p><span>Durée : </span> {{ unCours.duree }}</p>
        <p><span>Description :</span> {{ unCours.description }}</p>
        
      </div>
    </div>

  </div>
  
</template>

<script>
export default {
    name: 'mesCours-list',
    props: ['mesCours'],
}
</script>

<style scoped>

img {
    height: 100px;
}

span {
    font-weight: bold;
}

</style>