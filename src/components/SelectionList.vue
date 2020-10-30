<template>
    <div>
        <h1>Ma sélection</h1>
        <p>Aucun joueur sélectionné</p>
        {{ selection }}
    </div>
  
</template>

<script>
export default {
    name: 'selection-list',
    props: ['selection']

}
</script>

<style>

</style>