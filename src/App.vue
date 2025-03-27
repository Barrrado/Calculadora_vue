<script setup>

import{reactive} from  'vue';

const estado = reactive({
  filtro : '',
  NumeroA : 0,
  NumeroB: 0,
  Resultado: 0,
})

const  Somar = () => {
  estado.Resultado = (parseFloat(estado.NumeroA)+ parseFloat(estado.NumeroB))
}
const Subtrair = () => {
estado.Resultado = (estado.NumeroA  -  estado.NumeroB)
}
const Multiplicar = () => {
  estado.Resultado = (estado.NumeroA*estado.NumeroB);
}  
const Dividir = () => {
  estado.Resultado = (estado.NumeroA  /  estado.NumeroB).toFixed(1);
}
</script>
<template>
<h1>Calculadora</h1>
<div class="row g-0">
  <div class="col-md-6 m-0 form">
      <form @submit.prevent  class="form-control">
              <div class="col-6">
                <label class="form-label" for="">Numero 1</label>
                <input @change="evento => estado.NumeroA = evento.target.value" class="form-control" type="number" name="" id="">
                <label class="form-label" for="">Numero 2</label>
                <input  @change="evento => estado.NumeroB = evento.target.value"  class="form-control"   type="number" name="" id="">
              </div>
              <div class="col-6">
                    <select  @change="evento => estado.filtro = evento.target.value"  class="form-select" name="" id="">
                    <option selected value= 0>Escolha a operação</option>
                    <option value= 1>Multiplicar</option>
                    <option value= 2>Somar</option>
                    <option value= 3>Dividir</option>
                    <option value= 4>Subtrair</option>
                    </select>
              </div>
      </form>
  </div>
      <div class="col-md-6 m-0">
            <div v-if="estado.filtro == 1 " class="div__multi" >  
                <h2>Seu Resultado e:</h2>
                {{ Multiplicar() }} 
                <h1  class="h1__div">{{ estado.Resultado }}</h1>
            </div>
            <div v-if="estado.filtro == 2" class="div__somar">
              <h2>Seu Resultado e:</h2>
              {{ Somar()}}
              <h1  class="h1__div">{{ estado.Resultado }}</h1>
            </div>
            <div v-if="estado.filtro == 3" class="div__dividir">
              <h2>Seu Resultado e:</h2>
              {{ Dividir() }}
              <h1  class="h1__div">{{ estado.Resultado }}</h1>
            </div>
            <div v-if="estado.filtro == 4" class="div__sub">
              <h2>Seu Resultado e:</h2>
              {{ Subtrair()}}  
              <h1  class="h1__div">{{ estado.Resultado }}</h1>
            </div>
            <div v-if="estado.filtro == 0" class="div__else">
                <h3>Escolha uma operação</h3>
                <img src="../src/components/OlympicaMath.png"alt="">
            </div>
      </div>
</div>
</template>
<style scoped>

form{
  display: flex;
  flex-direction: column;
  align-items: center;
  border:0;
  background-color: transparent;
  color:#cc8b00;
}

</style>
