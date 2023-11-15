<script setup>
let listaDeProductos=[{
  nameProduct:'caja',
  cantProduct:0,
  valorProduct:1000,
  diasRestantes:0
},{
  nameProduct:'vaso',
  cantProduct:4,
  valorProduct:3000,
  diasRestantes:56
},{
  nameProduct:'reloj',
  cantProduct:10,
  valorProduct:10000,
  diasRestantes:66
}

]

let total = 0

function calcularTotal(cantProduct, valorProduct) {
  total=cantProduct*valorProduct
  return total
}
</script>

<template>
  <div>
    <span v-for="(obj,index) in listaDeProductos" :key="index">
      <span v-if="!(obj.cantProduct == 0 || obj.diasRestantes == 0)">
        <h1>name: {{ obj.nameProduct }} <span v-if="obj.diasRestantes<5">Está por vencerse</span></h1>
        <h1>cantidad: {{ obj.cantProduct }}</h1>
        <h1>valor: {{ obj.valorProduct }}</h1>
        <h1>dias restantes: {{ obj.diasRestantes }}</h1>
        <h1>{{ calcularTotal(obj.cantProduct, obj.valorProduct) }}</h1>
      </span>
    </span>
    <h1>{{ total }}</h1>
  </div>
</template>

<style scoped>

</style>
