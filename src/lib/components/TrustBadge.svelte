<script lang="ts">
  import { onMount } from 'svelte';
  export let icon: string;
  export let title: string;
  export let value: string;
  
  let isVisible = false;
  
  onMount(() => {
    isVisible = true;
  });
</script>

<div 
  class="group bg-white p-8 rounded-2xl shadow-lg hover:shadow-2xl transition-all duration-500 transform hover:-translate-y-1"
  class:opacity-0={!isVisible}
  class:translate-y-4={!isVisible}
  class:opacity-100={isVisible}
  class:translate-y-0={isVisible}
>
  <div class="text-primary mb-4 transform group-hover:scale-110 transition-transform duration-300">
    {@html icon}
  </div>
  <div class="text-3xl font-bold bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent mb-2">
    {value}
  </div>
  <div class="text-gray-600 group-hover:text-gray-800 transition-colors">{title}</div>
</div>

<style>
  div {
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  }
</style>