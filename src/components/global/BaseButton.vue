<template>
  <button class="btn-orange">
    {{ text }}
  </button>
</template>

<script>
export default {
    props: ['text']
}
</script>

<style scoped>
.btn-orange {
  @apply bg-orange-400 text-white font-bold py-2 px-4 rounded;
}
.btn-orange:hover {
  @apply bg-black;
}
</style>