<template>
  <div class="hello">
   Peso: 
   <input type="number" v-model="peso"/>
   Altura: 
   <input type="number" v-model="altura"/>
   <p>{{resultado}}</p>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  data(){
    return {
      peso: 0.0,
      altura: 0.0
    }
  },
  computed: {
    resultado () {
      const IMC =  parseFloat(this.peso)  / (parseFloat(this.altura)*parseFloat(this.altura));
      if (!this.peso) {
        return "Preencha com um valor válido o peso"; 
      } else if (!this.altura){
        return "Preencha com um valor válido a altura";
      } else if(IMC < 18.5) {
        return "Abaixo do peso"
      } else if (IMC < 25) {
        return "Peso Normal"
      } else if (IMC < 30 ) {
        return "Sobrepeso"
      } else if (IMC < 35) {
        return "Obesidade grau 1"
      } else if (IMC < 40) {
        return "Obesidade grau 2"
      } else if (IMC >= 40) {
        return "Obesidade grau 3 ou Mórbida"
      }
      return "Digite os valores"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
