<script setup>
import { reactive } from 'vue';

const estado = reactive({
  num1: 0,
  num2: 0,
  operadorInicial: '+',
});

const Calculadora = () => {
  const { num1, num2, operadorInicial } = estado;

  switch (operadorInicial) {
    case 'soma':
      return num1 + num2;
    case 'subtrai':
      return num1 - num2;
    case 'divide':
      return num1 / num2;
    case 'multiplica':
      return num1 * num2;
    default:
      return 0;
  }
};
</script>

<template>
  <div class="container">
    <header class="p-5 mb-4 mt-4 bg-light rounded-3">
      <h1>Calculadora aritmética</h1>
    </header>

    <form>
      <div class="row">
        <div class="col">
          <ul class="list-group">
            <li class="list-group-item">
              <select v-model="estado.operadorInicial" class="mb-2 form-control">
                <option value="soma">Adição (+)</option>
                <option value="subtrai">Subtração (-)</option>
                <option value="divide">Divisão (/)</option>
                <option value="multiplica">Multiplicação (x)</option>
              </select>
              <input v-model.number="estado.num1" class="p-1" type="number" placeholder="Digite aqui o 1º número">
              <input v-model.number="estado.num2" class="ms-3 p-1" type="number" placeholder="Digite aqui o 2º número">
              <label class="ms-3 me-3">
                {{ Calculadora() }}
              </label>
            </li>
          </ul>
        </div>
      </div>
    </form>
  </div>
</template>

<style scoped>
</style>
