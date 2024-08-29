<template>
  <ol class="px-4 mt-10 flex flex-col gap-2">
    <li
      v-for="todo in todos"
      :key="todo.id"
      class="bg-white rounded-sm p-3 flex justify-between items-center"
    >
      <span
        :class="{ 'cursor-pointer': true, 'line-through': todo.complete }"
        @click="completeHandler(todo.id)"
      >
        <i class="fa-solid fa-check pr-2 text-green-400" />
        {{ todo.content }}</span
      >
      <i
        @click="deleteHandler(todo.id)"
        class="fa-solid fa-trash-can cursor-pointer text-red-600"
      />
    </li>
  </ol>
  <span v-if="todos.length === 0" class="flex justify-center"
    >Add a todo, please...</span
  >
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    todos: Array,
  },
  emits: ["complete-event", "delete-event"],
  methods: {
    completeHandler(id) {
      this.$emit("complete-event", id);
    },
    deleteHandler(id) {
      this.$emit("delete-event", id);
    },
  },
};
</script>
