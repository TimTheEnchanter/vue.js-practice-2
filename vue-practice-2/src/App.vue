<script setup>
import { reactive, ref } from 'vue'
// component logic
// declare some reactive state here.
const counter = reactive({
  count: 0
})
const message = ref('Hello World!')
const titleClass = ref('title')

console.log(message.value) // "Hello World!"
console.log(counter.count) // 0
counter.count++
message.value = 'Changed'
</script>

<template>
  <h1 :class="titleClass">Make me red</h1>
  <h1>{{ message.split('').reverse().join('') }}</h1>
  <h1>{{ message }}</h1>
	<p>Count is: {{ counter.count }}</p>
</template>

<style>
.title {
  color: red;
}
</style>
