<template>
<h2>THIS IS POPUPS COMPONENT</h2>
  <button @click="$emit('close')">Close</button>
</template>

<script >
export default {
  name: "Popup",
  emits:["close"]
}
</script>
