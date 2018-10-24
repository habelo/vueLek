<template>
  <div>
      <input type="number" v-model.number="inNr">
    <p>{{inNr}} Gånger med {{inNr2}} = {{inNr*inNr2}}</p>
    <input type="text" v-model.number="inNr2">
    <!-- detta gör samma som ovan, fast det roliga är att computed cachar alla föregående grejjor, vilket gör så att det är smartare i uträkningar som du vet kommer göras om -->
    <p>Blir: {{multiplyC}}</p>

  </div>
</template>

<script>
export default {
  name: "tredje",
  data(){
      return{
      inNr: 0,
      inNr2: 0
    }
  },
  computed:{
      multiplyC: function(){
          return Math.round((this.inNr*this.inNr2));
      }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>
