<template>
  <div class="todoContainer">

    <TodoInput v-bind:NewItemHandler="NewItemHandler"/>

    <TodoItem v-for="todo in todos"
              v-bind:key="todo.id"
              v-bind:todo="todo"
              v-bind:ChangeHandler="ItemChange"
              v-bind:DeleteHandler="DeleteHandler"
    />
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'
import TodoInput from '@/components/TodoInput'

export default {
  name: 'TodoList',
  data() {
    return {
      todos: [
        {id: '1', value: 'Установить VUE.js', completed: true},
        {id: '2', value: 'Сделать ToDo List на Vue за 4 часа', completed: true},
        {id: '3', value: 'Сделать магазин на VUE.js с корзиной и товарами', completed: false},
        {id: '4', value: 'Пройти собеседование', completed: false}
      ]
    }
  },
  components: {
    TodoItem, TodoInput
  },
  methods: {
    ItemChange(todo) {
      this.todos.find(i => i.id === todo.id).completed = !todo.completed
    },
    DeleteHandler(todo) {
      this.todos = this.todos.filter(el => el.id !== todo.id)
    },
    NewItemHandler(value) {
      if (value.trim().length > 0) {
        const newId = Math.random().toString(36).substr(2, 9)
        this.todos.push({id: newId, value: value.trim(), completed: false})
      }
    }
  }
}

</script>

<style>
.todoContainer {
  display: flex;
  flex-direction: column;
  gap: 10px;
  width: 50%;


}

</style>