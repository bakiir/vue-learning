<template>

  <Count :count="count"/>
  <br>
  <Button name="Add" @changeCount="count += 1"/>
    <Button name="Sub" @changeCount="count -= 1"/>

  </template>

<script>
import Count from "@/components/Count.vue";
import Button from "@/components/Button.vue";

export default {
  name: 'App',
  components: {
    Count, Button
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
