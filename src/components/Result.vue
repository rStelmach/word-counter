<template>
  <div
    id="result"
    class="container min-w-full min-h-screen bg-gray-500 bg-opacity-70 flex flex-col items-center py-24 "
  >
    <h1>Result</h1>
    <div class=" overflow-auto overscroll-auto resultArray w-2/4 min-h-150 max-h-240 bg-gray-200 rounded-md ">
      <li v-for="result in results" :key="result" class="list-none py-1 px-3 font-semibold capitalize ">
        {{ result }} {{ counter }}
      </li>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  props: {
    results: {
      type: Array,
      required: true,
    },
  },
  setup() {
    const counter = ref(0);
    return { counter };
  },
};
</script>

<style></style>
