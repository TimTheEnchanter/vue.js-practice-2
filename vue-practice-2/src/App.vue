<script setup>
import { ref } from 'vue'
import { reactive } from 'vue'
// component logic
// declare some reactive state here.
const counter = reactive({
  count: 0
})
const message = ref('Hello World!')

console.log(message.value) // "Hello World!"
console.log(counter.count) // 0
counter.count++
message.value = 'Changed'
</script>

<template>
  <h1>{{ message.split('').reverse().join('') }}</h1>
  <h1>{{ message }}</h1>
	<p>Count is: {{ counter.count }}</p>
</template>
