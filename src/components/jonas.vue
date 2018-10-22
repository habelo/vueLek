<template>
  <div class="hello">
    <h1>Detta är sida "jonas" </h1>
    <ul>
      <li v-for="s in jArray" :key="s">{{ikryss ? s.se : s}}</li>
    </ul>
    <!-- i for-loopen så har jag gjort en if/else beroende på ifall den är ikryssad -->
    <input type="checkbox" name="Va" id="va" v-model="ikryss"> Gör om listan lide?
  </div>
</template>

<script>
export default {
  name: "Jonas",
  data(){
    return{
      ikryss: false,
      jArray:[
        {"se": "höger"},
        {"se": "vänster"},
        {"se": "neråt"}
      ]
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style src="./jonasCss.css">
</style>
