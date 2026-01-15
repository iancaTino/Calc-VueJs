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

