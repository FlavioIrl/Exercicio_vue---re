<script setup>
    const props = defineProps(['resultado'])
</script>

<template>
    <div class="mt-5 mostra-resultado">
        <h1>Resultado</h1>
        <button class="btn btn-resultado">{{ resultado }}</button>
    </div>
</template>

<style scoped>
.mostra-resultado {
  justify-content: center;
  align-items: center;
  justify-items: center;
}  


.btn:hover {
  background-color: #0f53c7;
}

.btn {
  padding: 5px 25px;
  color: #fff;
  background-color: #2d5fb4;
  font-size: 1.5rem;
}

.btn-resultado {
  padding-inline: 50px;
}
</style>