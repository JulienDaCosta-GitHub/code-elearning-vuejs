<template>
    <div>
        <div class="border border-black text-center m-4 p-4">
            <h2 class="text-lg font-bold">Votre panier</h2>
            <br>
            Nombre de cours : {{ mesCours.length }}
            <span>cours</span>
            <br>
            <br>
            <h2 class="text-lg font-bold">Liste des cours :</h2>
            <br>
            {{ nomCours }}

            <ul>
                <li v-for="unCours in mesCours"
                    :key="unCours.nom"
                >{{unCours.nom}} (Prix: {{unCours.prix}}€)
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "mon-panier",
    props: ['mesCours'],
    computed: {
        numberSelection() {
            if(this.selection < 2) {
                return true
            }
            return false
        },
    }
}
</script>

<style>

</style>