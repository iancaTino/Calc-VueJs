<script setup>
defineProps({
    texto: String
})
</script>

<template>
    <p class="resultado">{{ texto }}</p>
</template>

<style scoped>
.resultado {
    margin-top: 1.5rem;
    font-size: 1.1rem;
    color: #c2185b;
    font-weight: bold;
}
</style>
