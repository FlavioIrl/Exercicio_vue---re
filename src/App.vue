<script setup>
import { reactive, computed } from 'vue';
import Operacao from './components/Operacao.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive ({
  primeiroNumero: '',
  segundoNumero: '',
  operador: '+',
})

const resultado = computed (() => {
  const numero1 = parseFloat(estado.primeiroNumero)
  const numero2 = parseFloat(estado.segundoNumero)

  if (isNaN(numero1) || isNaN(numero2) || estado.operador === '') return '0'

  switch (estado.operador) {
    case '+':
      return numero1 + numero2;
    case '-':
      return numero1 - numero2;
    case '*':
      return numero1 * numero2;
    case '/':
      return numero2 !== 0 ? numero1 / numero2 : 'Não se divide por zero!'
  }
})

const atualizaSegundoNumero = (valor) => {
  estado.segundoNumero = valor
}

const atualizaOperador = (valor) => {
  estado.operador = valor
}

const atualizaPrimeiroNumero = (valor) => {
  estado.primeiroNumero = valor
}
</script>

<template>
  <div class="fundo">
    <div class="container">
      <h1 class="text-center title mt-5">Exercicio VueJS</h1>
      <Operacao :operador="estado.operador" 
        :primeiro-numero="estado.primeiroNumero" 
        :segundo-numero="estado.segundoNumero"
        :atualiza-primeiro-numero="atualizaPrimeiroNumero"
        :atualiza-segundo-numero="atualizaSegundoNumero"
        :atualiza-operador="atualizaOperador" />
      <Resultado :resultado="resultado"/>
    </div>
  </div>
</template>

<style scoped>

.fundo {
  background: radial-gradient(circle at center, #27416d, #0c0720 90%);
  position: absolute;
  width: 100%;
  height: 100%;
  color: #fff;
}

</style>
