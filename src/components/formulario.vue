<script setup>
const props = defineProps(['numero1', 'numero2',  'Operação', 'Multiplicar', 'Dividir','Subtrair', 'Somar', 'Resultado']);
</script>'
<template>
<div class="col-md-6 m-0 form">
    <form @submit.prevent  class="form-control">
        <div class="col-6">
        <label class="form-label" for="">Numero 1</label>
        <input @change="props.numero1" class="form-control" type="number" name="" id="">
        <label class="form-label" for="">Numero 2</label>
        <input  @change="props.numero2"  class="form-control"   type="number" name="" id="">
        </div>
        <div class="col-6">
            <select  @change="props.Operação"  class="form-select" name="" id="">
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
            <div v-if="props.Operação == 1 " class="div__multi" >  
                <h2>Seu Resultado e:</h2>
                {{ props.Multiplicar }} 
                <h1  class="h1__div">{{ props.Resultado}}</h1>
            </div>
            <div v-if="props.Operação == 2" class="div__somar">
              <h2>Seu Resultado e:</h2>
              {{ props.Somar }}
              <h1  class="h1__div">{{ props.Resultado }}</h1>
            </div>
            <div v-if="props.Operação == 3" class="div__dividir">
              <h2>Seu Resultado e:</h2>
              {{ props.Dividir }}
              <h1  class="h1__div">{{ props.Resultado }}</h1>
            </div>
            <div v-if="props.Operação == 4" class="div__sub">
              <h2>Seu Resultado e:</h2>
              {{ props.Subtrair}}  
              <h1  class="h1__div">{{ props.Resultado }}</h1>
            </div>
            <div v-if="props.Operação == 0" class="div__else">
                <h3>Escolha uma operação</h3>
                <img src="../components/OlympicaMath.png"alt="">
            </div>
      </div>
</template>

