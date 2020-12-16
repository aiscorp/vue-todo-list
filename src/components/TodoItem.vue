<template>
  <div class="todoItem">
    <input class="todoItem__checker" type="checkbox"
           v-bind:checked="todo.completed" @change="ChangeHandler(todo)">
    <span class="todoItem__value"
          v-bind:class="{ todoItem__value_completed: todo.completed }">
      {{ todo.value }}
    </span>
    <button class="todoItem__button" @click="DeleteHandler(todo)">
      X
    </button>
  </div>
</template>

<script>

export default {
  name: 'TodoItem',
  props: ['todo', 'ChangeHandler', 'DeleteHandler'],
  methods: {}
}
</script>

<style>
.todoItem {
  display: flex;
  align-items: center;
  justify-content: start;
  gap: 20px;
}

.todoItem__checker {
  transform: scale(1.5);
  margin: 0;
  cursor: pointer;
  margin-left: 5px;
}

.todoItem__value {
  font-size: 1.25em;
}

.todoItem__value_completed {
  color: gray;
  text-decoration: line-through;
}

.todoItem__button {
  margin-left: auto;
  padding: 5px 10px;
  font-weight: bold;
  background: transparent;
  border: 2px solid red;
  border-radius: 5px;
  outline: none;
  cursor: pointer;
}

.todoItem__button:hover {
  color: #FFF;
  background: red;
}

</style>