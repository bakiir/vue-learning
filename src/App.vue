<template>
  <p  >Hi {{ name }}</p>
  <p v-text="question"></p>
  <p v-html="htmlData" v-bind:id:="''" v-bind:class="id" v-bind:style="style"></p>
  <button @click="name = 'Araika' ">Change name </button>

  <!--Counter app -->
  <h2>{{count}}</h2>
  <button @click = "increase(5)"> + </button>
  <button @click = "decrease(5)"> - </button>

  <!-- Conditions -->

  <h2 v-if="num === 0">Zero</h2>
  <h2 v-else-if="num > 0">Positive</h2>
  <h2 v-else-if="num < 0">Negative</h2>
  <h2 v-else>No Zero</h2>
  <h2 v-show = "isVisible">Data is visible </h2> <!--u can look at dev mode, it just adds style display:none -->
  <h2 v-if = "isVisible">Data is visible </h2> <!--u can't look at dev mode-->

  <!--u can use conditions with templates also-->
  <!--Components-->

  <Greet/>

  <!-- Props -->
  <Greet name = "Bakr"/>
  <Greet :name = "name"/>


  <!-- Emitters -->
  <button @click = "isPopupVisible = true">Show popup</button>
  <Popup v-if="isPopupVisible" @close = "isPopupVisible = false" />


  <!--Slots and Scoped Slots-->
<Card>This is our first slot</Card>

</template>

<script>

import Greet from "@/components/Greet.vue";
import Popup from "@/components/Popup.vue";
import Card from "@/components/Card.vue";

export default {
  name: 'App',
  components: {
    Greet,
    Popup,
    Card
  },
  data(){
    return{
      name: "Bakir", question: "How are u?", htmlData: "  <p>Whats up?</p>\n",
      id: "new", style:{color:'red'},
      count: 0,
      num:0, isVisible: false,
      isPopupVisible:false
    }
  },
  methods:{
    increase(num){
      this.count += num
    },
    decrease(num){
      this.count -= num
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
