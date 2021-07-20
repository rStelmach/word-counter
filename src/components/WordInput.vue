<template>
  <div class="container bg-gray-600 min-w-full min-h-screen bg-opacity-70">
    <header class="filter drop-shadow-lg text-6xl tracking-wide text-center text-white	font-semibold	pt-20">
      word cou<span class="text-yellow-400">n</span>ter
    </header>
    <form @submit.prevent="countWords">
      <div class="text flex flex-col  mx-36 mt-20 px-56">
        <label for="text" class="filter drop-shadow-lg font-semibold text-white text-xl p-2">Type here</label>
        <textarea
          name="text"
          id="text"
          rows="20"
          cols="10"
          maxlength="10000"
          class="resize-none p-2 rounded-md border-opacity-0 text-md  focus:outline-none font-bold tracking-wide bg-gray-200 "
          v-model="inputWords"
        ></textarea>
        <button
          class="filter drop-shadow-lg text-base my-4 mx-96 p-2 font-bold rounded-md text-white bg-gray-600 uppercase"
        >
          see the results
        </button>
      </div>
    </form>
  </div>
  <Result :results="results" />
</template>
<script>
import { computed, ref } from 'vue';
import Result from './Result.vue';

export default {
  components: { Result },
  setup() {
    const inputWords = ref('');
    const results = computed(() =>
      inputWords.value
        .toLowerCase()
        .replace(/\./g, ' ')
        .split(/(?:,| | {2})+/),
    );

    return { inputWords, results };
  },
};
</script>
