<template>
<div>
    <div
    class="border m-4 p-4 flex justify-between"
    >
        <div>
            <h1 class="text-lg font-bold">{{ coursMajuscule }}</h1>
            <img :src="'../assets/img/' + unCours.image" />
            <h2> Difficulté : {{ unCours.difficulté }}</h2>
            <p> Description : {{ unCours.description }}</p>
            <p> Prix : {{ unCours.prix }}</p>
        </div>
        <base-button
            text="Ajouter au panier"
            @click="ajoutMesCours"
        >
        </base-button>
    </div>
</div>
</template>

<script>

export default {
    name: "unCours-card",
    props: ['unCours'],
    data(){
        return {
            mesCours: []
        }
    },
    computed: {
        coursMajuscule() {
            return this.unCours.nom.toUpperCase()
        }
    },
    methods: {
        ajoutMesCours() {
            this.$emit('ajout-uncours', this.unCours)
        }
    }
}
</script>

<style scoped>

</style>