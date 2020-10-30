<template>
    <div class="flex justify-center">
    <div class="w-1/5">
      <mon-panier 
      :mesCours="mesCours"
      @change-component="changeSelectedComponent"
    >
    </mon-panier>
    </div>

    <div class="w-4/5">
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
        this.$emit('child-event', unCours)
      },
    }
}

</script>

<style>

</style>