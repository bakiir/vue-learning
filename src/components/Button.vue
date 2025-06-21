<template>
  <button @click="$emit('changeCount')">{{name}}</button>
</template>

<script >
export default {
  name: 'Button',
  emits:['changeCount'],
  props: ['count', 'name']
}

</script>

<style >

</style>