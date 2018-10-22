<template>
  <div class="hello">
    <h1>2: Detta är sida {{jonasProp}} </h1>

    
 <!-- EN animation som markeras av transition och döps "alert-in" -->
    <transition name="alert-in">
    <div v-bind:class="{ alert : ifAlert, 'andraKlass': !ifAlert}">

        <p v-bind:style="{padding: 2}">{{inputText}}</p>
    </div>
    </transition>


    <button v-on:click="switchAlert" v-if="ifAlert">Show or not to Show</button>
    <button v-on:click="switchAlert" v-if="!ifAlert">Show other button</button>

    <form @submit.prevent="addToList">

<input type="text" placeholder="skriv här fan" v-model="inputText">

<ul>
    <!-- animera listan -->
    <transition-group name="list" enter-active-class="animated bounceInUp" leave-active-class="animated bounceOutDown">

    <li v-for="text in inputArray" :key="text">{{text}}</li>

    </transition-group>
</ul>

<button @click="removeFromList
">Ta bort</button>

    </form>
  </div>
</template>

<script>
import Jonas from "@/components/jonas.vue";
export default {
  name: "Jonas2",
  data(){
      return{
          inputText: '',
          jonasProp: "jonas2 två",
          ifAlert: true,
          inputArray: []
      }
  },
  methods:{
      switchAlert(){
          this.ifAlert ? this.ifAlert= false : this.ifAlert = true
      },
      addToList(){
          this.inputArray.push(this.inputText)
          this.inputText = ''
      },
      removeFromList(){
          this.inputArray.splice(0,1)
      }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import "https://cdn.jsdelivr.net/npm/animate.css@3.5.1";
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.alert{
    background-color: #42b983;
       width: 100%;
    height: 50px;

}
.andraKlass{
           width: 100%;
    height: 40px;
    border: 5px solid black;
}

/* // bounce som ska animeras av transition leave & enter ska vara någon slags default kodning i något biblotek */
.alert-in-leave-active{
    animation: bounce-in .5s
}
.alert-in-enter-active{
    animation: bounce-in .5s
}

/* // från 0 i skala, till 1.5 (150% av size) till skala 1:1 */
@keyframes bounce-in {
    0%{
        transform: scale(0);
    }
    50%{
        transform: scale(1.5);
    }
    100%{
        transform: scale(1);
    }
}
</style>