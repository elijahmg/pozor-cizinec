<script>
  import {names} from '../utils/names.ts';

  let text = '';

  $: parsedText = text.toUpperCase().split('')

</script>

<svelte:head>
  <title>
    Pozor Cizinec
  </title>
</svelte:head>

<div class="flex justify-center items-center flex-col mt-20 w-4/5 mx-auto">
  <h1 class="uppercase text-gray-700 mb-8 text-4xl drop-shadow-lg">
    Pozor cizinec
  </h1>
  <p class="text-center mb-4">
    Have you ever struggled to get you name or surname understand by czech person on the phone?
  </p>
  <p class="mb-4 text-center">
    Here you go, no more phone battles
  </p>
  <div class="mb-6 md:w-1/2 sm:w-4/5">
    <label for="price" class="block text-sm font-medium leading-6 text-gray-900 text-center">Text to decode</label>
    <div class="relative mt-2 rounded-md shadow-sm">
      <input bind:value={text} type="text" name="price" id="price"
             class="block w-full rounded-md border-0 py-1.5 px-3 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-gray-400 sm:text-sm sm:leading-6">
    </div>
  </div>
  <div class="flex flex-col items-center">
  {#each parsedText as letter}
    <span class="mb-1 tracking-wider">{names[letter]}</span>
  {/each}
  </div>
</div>
