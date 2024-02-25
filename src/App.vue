  <template>
    <div id="app">
      <h1>Calculadora Aritmética</h1>
      
      <div>
        <label for="num1">Número 1:</label>
        <input type="number" v-model="num1" @input="calcularResultado" />
      </div>

      <div>
        <label for="num2">Número 2:</label>
        <input type="number" v-model="num2" @input="calcularResultado" />
      </div>

      <div>
        <label for="operacao">Operação:</label>
        <select v-model="operacao" @change="calcularResultado">
          <option value="+">Soma</option>
          <option value="-">Subtração</option>
          <option value="*">Multiplicação</option>
          <option value="/">Divisão</option>
        </select>
      </div>

      <div>
        <label for="resultado">Resultado:</label>
        <input type="number" :value="resultado" readonly />
      </div>
    </div>
  </template>

  <script>
  export default {
    data() {
      return {
        num1: 0,
        num2: 0,
        operacao: '+',
        resultado: 0
      };
    },
    methods: {
      calcularResultado() {
        switch (this.operacao) {
          case '+':
            this.resultado = this.num1 + this.num2;
            break;
          case '-':
            this.resultado = this.num1 - this.num2;
            break;
          case '*':
            this.resultado = this.num1 * this.num2;
            break;
          case '/':
            this.resultado = this.num1 / this.num2;
            break;
        }
      }
    }
  };
  </script>

  <style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  div {
    margin-bottom: 10px;
  }

  label {
    margin-right: 10px;
  }
  </style>
