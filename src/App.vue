<template>
  <div class="flex justify-center">
    <div class="font-bagel max-w-[600px] bg-gray-100 min-h-screen w-full">
      <Header />
      <Input @submit-event="inputValue" />
      <List :todos="todos" />
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
      todos: [],
    };
  },
  methods: {
    inputValue(event) {
      this.todos.push(event);
    },
  },
};
</script>
