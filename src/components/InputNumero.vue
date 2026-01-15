<script setup>
defineProps({
    modelValue: String,
    placeholder: String
})

defineEmits(['update:modelValue'])
</script>

<template>
    <input type="number" class="campo" :placeholder="placeholder" :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)">
</template>

<style scoped>
.campo {
    width: 100%;
    padding: 0.75rem;
    margin: 0.6rem 0;
    border: 1px solid #f8b6c8;
    border-radius: 20px;
    font-size: 1rem;
}
</style>
