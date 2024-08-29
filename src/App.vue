<template>
  <div class="flex justify-center">
    <div class="font-bagel max-w-[600px] bg-gray-100 min-h-screen w-full">
      <Header />
      <Input @submit-event="inputValue" />
      <List
        :todos="todos"
        @complete-event="completeTodo"
        @delete-event="deleteTodo"
      />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Input from "./components/Input.vue";
import List from "./components/List.vue";

export default {
  components: {
    Header,
    Input,
    List,
  },
  data() {
    return {
      todos: [].sort((a, b) => b - a),
    };
  },
  methods: {
    inputValue(event) {
      this.todos.push(event);
    },
    completeTodo(id) {
      const updateTodos = this.todos.map((item) => {
        if (item.id === id) {
          return { ...item, complete: !item.complete };
        }
        return item;
      });

      this.todos = updateTodos;
    },
    deleteTodo(id) {
      const deleteTodos = this.todos.filter((item) => item.id !== id);
      this.todos = deleteTodos;
    },
  },
};
</script>
