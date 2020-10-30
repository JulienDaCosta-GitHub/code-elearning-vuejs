<template>
    <div class="flex justify-center">
    <mon-panier 
      :mesCours="mesCours"
    >
    </mon-panier>

    <div>
    <unCours-card
    v-for="(unCours, index) in ensemble.cours"
    :key="index"
    :unCours="unCours"
    @ajout-uncours="ajoutCoursPanier"
    >
    </unCours-card>
    </div>
  </div>
</template>

<script>
import ensembleData from '../data/cours.json'
import unCoursCard from '../components/CoursCard.vue'
import MonPanier from '../components/MonPanier.vue'


export default {
    name: 'unCours-view',
  components: {
    unCoursCard,
    MonPanier

  },
  data() {
        return {
            ensemble: ensembleData,
            mesCours: []
        }
    },
    methods: {
      ajoutCoursPanier(unCours) {
        this.mesCours.push(unCours)
      }
    }
}

</script>

<style>

</style>