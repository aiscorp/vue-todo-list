<template>
  <div id="app">
    <h1>Very easy ToDo List in Vue</h1>
    <TodoList/>
  </div>
</template>

<script>
import TodoList from '@/components/TodoList'

export default {
  name: 'App',
  components: {
    TodoList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: grid;
  justify-items: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
