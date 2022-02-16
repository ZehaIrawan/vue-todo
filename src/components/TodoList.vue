<script>
// import TodoItem from "@/components/TodoItem.vue";

export default {
  data() {
    return {
      currentTodo: "",
      todos: [
        {
          name: "Learn Vue",
          done: false,
        },
        {
          name: "Buy Eggs",
          done: true,
        },
      ],
    };
  },
  methods: {
    addTodo() {
      this.todos.push({
        name: this.currentTodo,
        done: false,
      });
      this.currentTodo = "";
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<template>
  <!-- <TodoItem /> -->
  <li v-for="item in todos" :key="item.name">
    {{ item.name }}
    <input type="checkbox" v-model="item.done" />
    <button @click="removeTodo">X</button>
  </li>

  <input v-model="currentTodo" type="text" placeholder="Buy milk" />
  <button @click="addTodo">Add Task</button>
</template>
