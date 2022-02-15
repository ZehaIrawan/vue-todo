<script>
import TodoItem from "@/components/TodoItem.vue";

export default {
  data() {
    return {
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
};
</script>

<template>
  <TodoItem />
  <li v-for="item in todos">
    {{ item.name }}
    <input type="checkbox" v-model="item.done" />
  </li>
</template>
