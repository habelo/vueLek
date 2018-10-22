<template>
  <div >

      <input type="checkbox" value="leka" v-model="checkarray">Leka
      <input type="checkbox" value="smeka" v-model="checkarray">Smeka
      <input type="checkbox" value="dela" v-model="checkarray">Dela
      <input type="checkbox" value="friska"  v-model="checkarray">Friska

        <!-- skriva ut en array med join -->
      <p>{{checkarray.join(', ')}}</p>
      <!-- lägga till string -->
      <p v-if="checkarray.length < 1">{{'du har inte ' + text}}</p>
      <p v-else-if="checkarray.length < 4">{{'nu har du '+text}}</p>
      <p v-else>{{'allt är '+text}}</p>

            
      <div v-for="(objekt, index) in objarray" :key="objekt">
          {{objekt.id}} : {{objekt.name}} : har han cred : {{objekt.streedcred}} index: {{index}}
      </div>

      <div :style="firstcss" @mouseover="firstcss.backgroundColor='black'" @mouseout="firstcss.backgroundColor='grey'">
lite text
      </div>

      <!-- för att göra samma fast med class så skickar man in klassen, sedan en boolean för att säga omd en används eller inte -->
  <div class="storgrön" :class="{storblå: grönBlå}">
    <button :style="'padding: 10px; width: 20px'" @click="grönBlå=true"></button>
  </div>



  </div>
</template>

<script>
export default {
  name: "Jonas3",
  data(){
      return{

        grönBlå: false,

        firstcss:{
          fontSize: '25px',
          padding: '10px',
          marginTop: '30px',
          backgroundColor: 'grey'
        },

        text: 'valt något',
        // automatiskt checka en checkbox:
        checkarray:['dela'],
        objarray:[
            { 
          id: 1,
          name: 'olle',
          streedcred: true
          },
          { 
          id: 2,
          name: 'molle',
          streedcred: false
          },
          { 
          id: 3,
          name: 'troll',
          streedcred: true
          }
      ]
      }
  }
};
</script>

<style>
.storgrön{
  padding: 50px;
  background-color: greenyellow;
}
.storblå{
  padding: 50px;
  background-color: midnightblue;
}
</style>
