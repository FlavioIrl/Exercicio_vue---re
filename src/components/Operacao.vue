<script setup>
    import { defineProps } from 'vue';

    const props = defineProps({
        operador: String,
        primeiroNumero: String,
        segundoNumero: String,
        atualizaPrimeiroNumero: Function,
        atualizaOperador: Function,
        atualizaSegundoNumero: Function,
})
    
</script>

<template>
    <div class="operacao mt-5">
      <input
        type="number"
        @input="props.atualizaPrimeiroNumero($event.target.value)"
        placeholder="Número 1"
        class="form-control p-2 input-1"
      />
      <select
        @change="props.atualizaOperador($event.target.value)"
        class="operador dropdown text-center"
      >
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="/">/</option>
        <option value="*">x</option>
      </select>
      <input
        type="number"
        @input="props.atualizaSegundoNumero($event.target.value)"
        placeholder="Número 2"
        class="form-control p-2 input-2"
      />
    </div>
  </template>
  

<style scoped>
.operacao {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
}

.dropdown {
  text-align: center;
}

.operador {
  border-radius: 8px;
  font-size: 1.5rem;
  color: #fff;
  background-color: #2d5fb4;
  padding: 5px 20px;
  width: 80px; 
  text-align: center;
}
</style>

