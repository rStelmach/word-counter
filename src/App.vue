<template>
  <div class="container bg-gray-600 min-w-full min-h-screen bg-opacity-70">
    <header class="text-6xl tracking-wide text-center text-white	font-semibold	pt-28">
      word cou<span class="text-yellow-400">n</span>ter
    </header>
    <div class="text flex flex-col  m-10 mt-20 px-56">
      <label for="text" class="font-semibold text-white p-2">Type here</label>
      <textarea
        name="text"
        id="text"
        rows="20"
        cols="10"
        maxlength="600"
        class="resize-none p-1 rounded-md border-opacity-0	focus:outline-none"
      ></textarea>
    </div>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,300;0,400;0,700;0,900;1,300&display=swap');
* {
  font-family: 'Lato', sans-serif;
}
</style>
