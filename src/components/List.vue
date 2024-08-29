<template>
  <ol class="px-4 mt-10 flex flex-col gap-2">
    <li class="bg-white rounded-sm p-3 flex justify-between items-center">
      <span class="cursor-pointer">
        <i class="fa-solid fa-check pr-2 text-green-400" />
        {{ todos }}</span
      >
      <i class="fa-solid fa-trash-can cursor-pointer text-red-600" />
    </li>
  </ol>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: {
    todos: Array,
  },
};
</script>
