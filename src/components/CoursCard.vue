<template>
<div>
    <div
    class="border m-4 p-4 flex justify-between border-black"
    :class="difficulteStyle"
    >
        <div>
            <h1 class="text-lg font-bold">{{ coursMajuscule }}</h1>
            <img class="mb-5" :src="require('../assets/img/' + unCours.image)" />
            <h2><span>Difficulté :</span> {{ unCours.difficulte }}</h2>
            <p><span>Durée : </span> {{ unCours.duree }}</p>
            <p><span>Description :</span> {{ unCours.description }}</p>
            <p><span>Prix :</span> {{ unCours.prix }}€</p>
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
        },
        difficulteMoyenne() {
            if(this.unCours.difficulte == "Moyen"){
                return true
            }
            return false
        },
        difficulteDifficile() {
            if(this.unCours.difficulte == "Difficile"){
                return true
            }
            return false
        },
        difficulteStyle() {
            return { 
                'bg-orange-500': this.difficulteMoyenne, 
                'bg-red-600': this.difficulteDifficile, 
            }
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

img {
    height: 100px;
}

span {
    font-weight: bold;
}

</style>