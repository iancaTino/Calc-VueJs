<script setup>
defineProps({
    modelValue: String
})

defineEmits(['update:modelValue'])
</script>

<template>
    <select class="campo" :value="modelValue" @change="$emit('update:modelValue', $event.target.value)">
        <option value="add">Soma (+)</option>
        <option value="subtract">Subtrair (-)</option>
        <option value="multiply">Multiplicar (X)</option>
        <option value="divide">Dividir (÷)</option>
    </select>
</template>

<style scoped>
.campo {
    width: 100%;
    padding: 0.75rem;
    margin: 0.6rem 0;
    border: 1px solid #f8b6c8;
    border-radius: 20px;
    font-size: 1rem;
    background-color: white;
}
</style>
