<template>
  <div>

    <navigation-bar
    @change-component="changeSelectedComponent">

    </navigation-bar>

  <keep-alive include="player-view">
        <component
          :is="selectedComponent"
          v-bind="currentProps"
          @child-event="mesCoursMaj"
          >

          </component>
  </keep-alive>
    </div>
</template>

<script>

import CoursView from './components/CoursView.vue'
import mesCoursList from './components/mesCoursList.vue'
import NavigationBar from './components/navigation/NavigationBar.vue'

export default {
  name: 'App',
  components: {
    CoursView,
    mesCoursList,
    NavigationBar
  },
  data() {
    return {
      selectedComponent: 'cours-view',
      coursPanier: []
    }
  },
  computed: {
    currentProps() {
      if(this.selectedComponent == "mesCours-list") {
      return { mesCours: this.coursPanier }
      }
      return false
    }
  },
  methods: {
    changeSelectedComponent(value) {
      this.selectedComponent = value
    },
    mesCoursMaj(value) {
      this.coursPanier.push(value)
    }
  }
}
</script>

<style>


</style>
