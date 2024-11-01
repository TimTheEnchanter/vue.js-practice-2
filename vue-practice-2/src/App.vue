<script setup>
import { reactive, ref, onMounted, watch } from 'vue'
import ChildComp from './ChildComp.vue'

// component logic
// declare some reactive state here.
let id = 0

const counter = reactive({
  count: 0
})
const message = ref('Hello World!')
const titleClass = ref('title')
const count = ref(0)
const text = ref('')
const awesome = ref(true)
const pElementRef = ref(null)

const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'Learn HTML' },
  { id: id++, text: 'Learn JavaScript' },
  { id: id++, text: 'Learn Vue' }
])


console.log(message.value) // "Hello World!"
console.log(counter.count) // 0
counter.count++
message.value = 'Changed'


function increment() {
  // update component state
  count.value++
}

//Conditional Rendering
function toggle() {
  awesome.value = !awesome.value
}

//Rendering a list
function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value })
  newTodo.value = ''
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}

//Lifecycle hooks
onMounted(() => {
  pElementRef.value.textContent += " dudes!"
})

//Props
const greeting = ref('Hello from parent')

const props = defineProps({
  msg: String
})

//Emits
const childMsg = ref('No child msg yet')
const emit = defineEmits(['response'])
emit('response', 'hello from child')

//Watcher
watch(count, (newCount) => {

  console.log(`new count is: ${newCount}`)
})

</script>

<template>
  <h1 :class="titleClass">Make me red</h1>
  <h1>{{ message.split('').reverse().join('') }}</h1>
  <h1>{{ message }}</h1>
	<p>Count is: {{ counter.count }}</p>

  <button @click="increment">Count is: {{ count }}</button>

  <input v-model="text" placeholder="Type here">
  <p>{{ text }}</p>

  <button @click="toggle">Toggle</button>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Angular is da best</h1>


  <form @submit.prevent="addTodo">
    <input v-model="newTodo" required placeholder="new todo">
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>

  <p ref="pElementRef">Hello</p>

  <ChildComp :msg="greeting" @response="(msg) => childMsg = msg">
    Just slotting some content in here.
  </ChildComp>
  <p>{{ childMsg }}</p>
</template>

<style>
.title {
  color: red;
}
</style>
