<template>
  <div>
    <input v-model="number1" @keyup="calcular"  class="me-3" type="number" placeholder="Digite primeiro numero">
    <select v-model="operacao"> 
      <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>
    <input  v-model="number2" @keyup="calcular"  class="ms-3" type="number" placeholder="Digite segundo numero">
    <p>Resultado: {{ resultado }}</p>
    <button @click="reset">Reiniciar</button>
  </div>
</template>

<script> 
export default {
  data() {
      return {
        number1: 0,
        number2: 0,
        operacao: 'soma', 
        resultado: 0,
    };
  },
  methods: {
    calcular() {
      const num1 = parseFloat(this.number1);
      const num2 = parseFloat(this.number2);

      switch (this.operacao) {
        case 'soma':
          this.resultado = num1 + num2;
          break;
        case 'subtracao':
          this.resultado = num1 - num2;
          break;
        case 'multiplicacao':
          this.resultado = num1 * num2;
          break;
        case 'divisao':
          this.resultado = num1 / num2;
          break;
        default:
          this.resultado = 0;
        }
      },
      reset() {
          this.number1 = 0;
          this.number2 = 0;
          this.resultado = 0;
      }
    },
};

</script>

<style scoped>
.calculator {
  max-width: 200px;
  margin: 0 auto;
}



</style>
