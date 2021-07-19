<template>
  <div
    id="result"
    class="container min-w-full min-h-screen bg-gray-500 bg-opacity-70 flex flex-col items-center py-24 "
  >
    <h1>Results</h1>
    <div class=" overflow-auto overscroll-auto resultArray w-2/4 min-h-150 max-h-240 bg-gray-200 rounded-md ">
      <li v-for="word in wordsCount" :key="word" class="list-none py-1 px-3 font-semibold">
        {{ word.name }} {{ word.counter }}
      </li>
    </div>
    <button class="text-xl" @click="siemaa">KLIKNIJ</button>
  </div>
</template>

<script>
import { computed } from 'vue';

export default {
  props: {
    results: {
      type: Array,
      required: true,
    },
  },
  setup(props) {
    const wordsCount = computed(() =>
      props.results.reduce((wordsByCount, currentWord) => {
        const existingWordEntity = wordsByCount.find(wordByCount => wordByCount.name === currentWord);

        if (!existingWordEntity) {
          const newWordByCountEntry = {
            name: currentWord,
            counter: 1,
          };

          wordsByCount.push(newWordByCountEntry);
          return wordsByCount;
        }

        existingWordEntity.counter += 1;
        const indexOfExistingEntity = wordsByCount.findIndex(
          wordByCount => wordByCount.name === existingWordEntity.name,
        );
        wordsByCount.splice(indexOfExistingEntity, 1);
        wordsByCount.push(existingWordEntity);

        return wordsByCount;
      }, []),
    );

    // const siema = computed(() =>
    //   props.results.reduce((a, b) => {
    //     if (a.indexOf(b) < 0) a.push(b);
    //     return a;
    //   }, []),
    // );

    // function siemaa() {
    //   console.log(siema.value);
    // }

    return { wordsCount };
  },
};
</script>

<style></style>
