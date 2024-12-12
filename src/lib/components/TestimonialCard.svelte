<script lang="ts">
  import { onMount } from 'svelte';
  export let name: string;
  export let role: string;
  export let company: string;
  export let image: string;
  export let quote: string;
  export let rating: number;
  
  let isVisible = false;
  
  onMount(() => {
    isVisible = true;
  });
</script>

<div 
  class="group bg-white p-8 rounded-2xl shadow-lg hover:shadow-2xl transition-all duration-500"
  class:opacity-0={!isVisible}
  class:translate-y-4={!isVisible}
  class:opacity-100={isVisible}
  class:translate-y-0={isVisible}
>
  <div class="relative mb-8">
    <img 
      src={image} 
      alt={name}
      class="w-20 h-20 rounded-2xl object-cover group-hover:scale-105 transition-transform duration-500"
    />
    <div class="absolute -bottom-4 left-16 bg-primary text-white rounded-full px-4 py-1 text-sm">
      {#each Array(rating) as _}
        ★
      {/each}
    </div>
  </div>
  
  <blockquote class="text-gray-700 italic mb-6 text-lg leading-relaxed">
    "{quote}"
  </blockquote>
  
  <div>
    <h4 class="font-bold text-xl text-gray-900">{name}</h4>
    <p class="text-primary">{role} at {company}</p>
  </div>
  
  <div class="absolute top-6 right-8 text-8xl text-primary/10 font-serif">❝</div>
</div>

<style>
  div {
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  }
</style>