<script setup>
import { reactive, computed } from 'vue';

const estado = reactive ({
  primeiroNumero: '',
  segundoNumero: '',
  operador: '',
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
      return numero2 !== 0 ? numero1 / numero2 : "Erro" 
  }

})  


</script>

<template>
  <div class="fundo">
    <div class="container">
      <h1 class="text-center title mt-5">Exercicio VueJS</h1>
      <div class="row mt-5">
        <div class="col-5">
          <input type="number" v-model="estado.primeiroNumero" placeholder="numero-1" class="form-control p-2" />
        </div>
        <div class="col-2">
          <select v-model="estado.operador" class="operador form-select text-center">
              <option value="+">+</option>
              <option value="-">-</option>
              <option value="/">/</option>
              <option value="*">x</option>
          </select>
        </div>
        <div class="col-5">
          <input type="number" v-model="estado.segundoNumero" placeholder="numero-2" class="form-control p-2" />
        </div>
      </div>
      <div class="mt-5 row">
        <div class="col-5">
          <h1 class="ms-4">Resultado :</h1>
        </div>
        <div class="col-4">
          <button class="btn btn-resultado">{{ resultado }}</button>
        </div>
      </div>
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

.form-select option {
    text-align: left; 
}

.operador {
  text-align: center;
  border-radius: 8px;
  font-size: 1.5rem;
  padding: 3px 40px;
  color: #fff;
  background-color: #2d5fb4;
}

.btn:hover {
  background-color: #0f53c7;
}

.btn {
  padding: 5px 25px;
  color: #fff;
  background-color: #2d5fb4;
  font-size: 0,3rem;
}

.btn-resultado {
  padding-inline: 50px;
}
</style>
