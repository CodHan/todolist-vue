<template>
  <div class="flex px-4">
    <form @submit.prevent="submitHandler" class="w-full">
      <input
        type="text"
        v-model="inputValue.content"
        placeholder="Type what you have to do"
        class="w-[90%] rounded-md p-2 text-center h-full"
      />
      <button
        :class="{
          'text-white text-xl  p-2 w-[10%] rounded-sm': true,
          'bg-violet-500': !isDisabled,
          'bg-gray-500': isDisabled,
        }"
        type="submit"
        :disabled="isDisabled"
      >
        +
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputValue: {
        id: 0,
        content: "",
        complete: false,
      },
      isDisabled: true,
    };
  },
  watch: {
    "inputValue.content": function (content) {
      this.isDisabled = content.length === 0;
    },
  },
  methods: {
    submitHandler() {
      const newTodo = {
        id: this.inputValue.id++,
        content: this.inputValue.content,
        complete: this.inputValue.complete,
      };
      this.$emit("submit-event", newTodo);
      this.inputValue.content = "";
    },
  },
};
</script>

<style lang="scss" scoped></style>
