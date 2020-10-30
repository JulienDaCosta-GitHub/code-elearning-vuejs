<template>
    <div>
        <h1>Mes cours</h1>
        <p>Aucun cours ajouté</p>
        {{ mesCours }}
    </div>
  
</template>

<script>
export default {
    name: 'mesCours-list',
    props: ['mesCours']

}
</script>

<style>

</style>