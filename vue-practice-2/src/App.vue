<script setup>
import { reactive, ref } from 'vue'
// component logic
// declare some reactive state here.
const counter = reactive({
  count: 0
})
const message = ref('Hello World!')
const titleClass = ref('title')
const count = ref(0)
const text = ref('')

console.log(message.value) // "Hello World!"
console.log(counter.count) // 0
counter.count++
message.value = 'Changed'


function increment() {
  // update component state
  count.value++
}
</script>

<template>
  <h1 :class="titleClass">Make me red</h1>
  <h1>{{ message.split('').reverse().join('') }}</h1>
  <h1>{{ message }}</h1>
	<p>Count is: {{ counter.count }}</p>

  <button @click="increment">Count is: {{ count }}</button>

  <input v-model="text" placeholder="Type here">
  <p>{{ text }}</p>
</template>

<style>
.title {
  color: red;
}
</style>
