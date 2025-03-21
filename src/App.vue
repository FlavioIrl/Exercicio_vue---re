<script setup>
</script>

<template>
  <div class="container">
    <h1 class="text-center title mt-5">Exercicio VueJS</h1>
    <div class="row mt-5">
      <div class="col-5">
        <input type="number" placeholder="numero-1" class="form-control p-2" />
      </div>
      <div class="col-2">
        <button class="btn ">+</button>
      </div>
      <div class="col-5">
        <input type="number" placeholder="numero-1" class="form-control p-2" />
      </div>
    </div>
    <div class="row">
      <div class="col-3">
        <h1 class="ms-4 ">Resultado</h1>
      </div>
      <div class="col-9">
        <button class="btn">30</button>
      </div>
    </div>

  </div>
</template>


<style scoped>

.btn {
  padding: 5px 25px;
  color: #fff;
  background-color: #315aa1;
  font-size: 1.2rem;
  transition: all 0.3s ease;
}
</style>
