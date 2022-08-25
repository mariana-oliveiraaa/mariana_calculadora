<script>
export default {
  data() {
    return {
      pessoas: "",
      cont: "",
      valor_gorjeta: "",
  }},
  methods: {
    calcular(){
      const pessoas = this.pessoas;
      const cont = this.cont;
      const valor_gorjeta = this.valor_gorjeta;
      let valor_valor_gorjeta = 0;
      let resultado = {};
      valor_valor_gorjeta = cont * (valor_gorjeta / 100);
      resultado = (cont + valor_valor_gorjeta) / pessoas;
      resultado = Math.round(resultado);
      document.getElementById("resultado").innerHTML = resultado;
    }
  },
};
</script>

<template>
  <div class="conteudo">
    <h1>Calculadora de gorjetas</h1>
    <label> <p>Qual foi o valor da conta?</p>
      <input type="number" v-model="cont" id="cont">
    </label>

    <label>
      <p>Qual foi a qualidade do serviço?</p>
      <select v-model="valor_gorjeta">
        <option value="30">30% Excepcional</option>
        <option value="25">25% Muito bom</option>
        <option value="20">20% Bom</option>
        <option value="15">15% Ok</option>
        <option value="10">10% Ruim</option>
        <option value="5">5% Péssimo</option>
      </select>
    </label>

    <label><p>Quantas pessoass estão dividindo a conta?</p>
      <input type="number" v-model="pessoas" id="pessoas">
    </label>
    <button type="button" @click="calcular">R$:
      <span id="resultado"></span>
    </button>
  </div>
</template>
<style scoped>
h1{
  color: #e05db4;
  font-size:50px;
}

button{
  background-color: #bb3286;
  border:#ae569e;
  color: white;
  height:30px;
  width: 100px;
  border-radius:10px;
  margin:10px
}
</style>