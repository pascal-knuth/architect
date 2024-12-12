<script lang="ts">
  import { onMount } from 'svelte';
  export let logos: Array<{ src: string; alt: string; }>;
  
  let currentIndex = 0;
  let container: HTMLElement;
  
  const autoSlide = () => {
    if (container) {
      currentIndex = (currentIndex + 1) % logos.length;
      container.style.transform = `translateX(-${currentIndex * 100 / 4}%)`;
    }
  };

  onMount(() => {
    const interval = setInterval(autoSlide, 3000);
    return () => clearInterval(interval);
  });
</script>

<div class="relative overflow-hidden py-8">
  <!-- Gradient Overlays -->
  <div class="absolute left-0 top-0 w-32 h-full bg-gradient-to-r from-white to-transparent z-10"></div>
  <div class="absolute right-0 top-0 w-32 h-full bg-gradient-to-l from-white to-transparent z-10"></div>
  
  <div 
    bind:this={container}
    class="flex transition-transform duration-1000 ease-in-out"
  >
    {#each [...logos, ...logos] as logo}
      <div class="flex-none w-1/4 px-8">
        <img 
          src={logo.src} 
          alt={logo.alt}
          class="h-12 object-contain mx-auto filter grayscale hover:grayscale-0 transition-all duration-500 transform hover:scale-110"
        />
      </div>
    {/each}
  </div>
</div>