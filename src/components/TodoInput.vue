<template>
  <div class="todoInput">
    <span class="todoInput__span">New todo:</span>
    <input class="todoInput__input" type="text"
           v-model="input">
    <button class="todoInput__button" @click="NewItemHandler(input)">
      Add
    </button>
  </div>
</template>

<script>
export default {
  name: "TodoInput",
  props: ['NewItemHandler'],
  data() {
    return {
      input: ''
    }
  }
}
</script>

<style>
.todoInput {
  display: flex;
  align-items: center;
  gap: 5px;
  margin-bottom: 10px;


}

.todoInput__input {
  flex-grow: 1;
  height: 20px;
}

.todoInput__button {
  margin-left: auto;
  padding: 5px 10px;
  font-weight: bold;
  background: transparent;
  border: 2px solid green;
  border-radius: 5px;
  outline: none;
  cursor: pointer;
}

.todoInput__button:hover {
  color: #FFF;
  background: green;
}

.todoInput__span {
  font-size: 1.25em;
}


</style>