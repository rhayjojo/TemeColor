<script>
import { useDark, useToggle } from '@vueuse/core';
import { BeakerIcon, PencilSquareIcon } from '@heroicons/vue/24/solid';

const isDark = useDark();
const toggleDark = useToggle(isDark);

  export default {
    name: 'App',
    components: {
      PencilSquareIcon
    },
    data() {
      return {
        count: 0,
        isDisabled: false,
        theCount: 'the count button',
        isItalic: true,
        isRed: true,
      }
    },

    methods:  {
      increment(){
        this.count++
      }
    },

    mounted(){
      console.log(`la valeur initiale est de : ${this.count}`)
    }
  };
</script>


<template>
  <div class="max-w-96 flex gap-2 mx-auto mt-[50%] text-white">
    <div class="h-64 w-48 dark:bg-white bg-sky-950 text-white dark:text-sky-950">
      <PencilSquareIcon class="size-12 Dark:text-sky-950"/>
      <h1 class="m-4 text-2xl">Light mode</h1>
    </div>

    <div class="h-64 w-48 dark:bg-sky-950 bg-white dark:text-white text-sky-950">
      <PencilSquareIcon class="size-12 dark:text-white"/>
      <h1 class="m-4  text-2xl">Dark mode</h1>
    </div>
  </div>
</template>

<style>
  .red{
    color: red;
  }
  .italic{
    font-style: oblique;
  }
  html{
    box-sizing: border-box;
    scrollbar-width: none;
  }
  body{
    background: rgb(23, 23, 42);
  }
</style>