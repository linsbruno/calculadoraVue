<script setup>
import { reactive } from 'vue';


  const estado = reactive ({
    filtro:'+',
    resultado:'',
    n1:0,
    n2:0,
  })

  const resultado = () => {
    const {filtro} = estado;

    switch (filtro){
      case '+':
        return estado.n1 + estado.n2;
      case '-':
        return estado.n1 - estado.n2;
      case 'x':
        return estado.n1 * estado.n2;
      case ':':
        return estado.n1 / estado.n2;
      default:
        
    }
  }

</script>

<template>
  <div class="container">
    <input type="number" placeholder="digite o primeiro numero" @keyup="e => estado.n1 = parseFloat(e.target.value)">
    <div class="col-md-2">
      <select class="form-control" @change="evento  => estado.filtro = evento.target.value">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="x">x</option>
      <option value=":">/</option>
    </select>
    <input type="number" placeholder="digite o segundo numero" @keyup="w => estado.n2 = parseFloat(w.target.value)">
    <span>Resultado: {{ resultado() }}</span>
    </div>
  </div>
</template>

<style scoped>
</style>