<script setup>
import { computed, ref } from "vue";

import InputNumero from "./components/InputNumero.vue";
import SelectOperacao from "./components/SelectOperacao.vue";
import Resultado from "./components/Resultado.vue";

const primeiroValor = ref('');
const segundoValor = ref('');
const operacao = ref("add");

const resultado = computed(() => {
  if (primeiroValor.value === '' || segundoValor.value === '') {
    return 'Por favor, insira ambos os valores.';
  }

  const a = Number(primeiroValor.value);
  const b = Number(segundoValor.value);

  switch (operacao.value) {
    case 'add':
      return `Resultado: ${a + b}`;
    case 'subtract':
      return `Resultado: ${a - b}`;
    case 'multiply':
      return `Resultado: ${a * b}`;
    case 'divide':
      return b === 0
        ? 'Erro: Divisão por zero não é permitida.'
        : `Resultado: ${a / b}`;
    default:
      return '';
  }
});
</script>

<template>
  <div class="container">
    <h1>
      <i class="bi bi-calculator"></i>
      Calculadora 🎀
    </h1>

    <InputNumero v-model="primeiroValor" placeholder="Digite o primeiro número" />

    <InputNumero v-model="segundoValor" placeholder="Digite o segundo número" />

    <SelectOperacao v-model="operacao" />

    <Resultado :texto="resultado" />
  </div>
</template>

<style scoped>
.container {
  max-width: 400px;
  margin: 60px auto;
  padding: 2rem;
  background-color: #fff0f5;
  border: 2px solid #f8b6c8;
  border-radius: 30px;
  text-align: center;
  font-family: Arial, sans-serif;
  box-shadow: 0 10px 25px rgba(214, 51, 132, 0.15);
}

h1 {
  margin-bottom: 2rem;
  color: #c2185b;
}

h1 {
  color: #d63384;
  margin-right: 0.4rem;
}

input,
select {
  width: 100%;
  padding: 0.75rem;
  margin: 0.6rem 0;
  border: 1px solid #f8b6c8;
  border-radius: 20px;
  font-size: 1rem;
  box-sizing: border-box;
  background-color: #ffffff;
}

input:focus,
select:focus {
  outline: none;
  border-color: #d63384;
  box-shadow: 0 0 0 2px rgba(214, 51, 132, 0.2);
}

p {
  margin-top: 1.5rem;
  font-size: 3rem;
  color: #c2185b;
  font-weight: bold;
}
</style>
