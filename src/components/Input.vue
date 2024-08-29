<template>
  <div class="flex px-4">
    <form @submit.prevent="submitHandler" class="w-full">
      <input
        type="text"
        v-model="inputValue"
        placeholder="Type what you have to do"
        class="w-[90%] rounded-md p-2 text-center h-full"
      />
      <button
        class="text-white text-xl bg-violet-500 p-2 w-[10%] rounded-sm"
        type="submit"
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
      inputValue: "",
    };
  },
  methods: {
    submitHandler() {
      this.$emit("submit-event", this.inputValue);
      this.inputValue = "";
    },
  },
};
</script>

<style lang="scss" scoped></style>
