<script lang="ts">
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });
</script>

<section class="relative py-24 overflow-hidden">
  <!-- Background Image -->
  <div class="absolute inset-0">
    <img 
      src="https://images.unsplash.com/photo-1497366216548-37526070297c?auto=format&fit=crop&q=80" 
      alt="Office" 
      class="w-full h-full object-cover"
    />
    <div class="absolute inset-0 bg-primary/90 mix-blend-multiply"></div>
  </div>

  {#if visible}
    <div class="container relative" transition:fade>
      <div class="max-w-3xl mx-auto text-center text-white">
        <h2 class="text-4xl md:text-5xl font-bold mb-6">
          Ready to Transform Your Business?
        </h2>
        <p class="text-xl mb-10 text-white/90">
          Join industry leaders who trust us with their digital transformation. Schedule a consultation today and discover how we can elevate your business.
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center">
          <a href="#contact" class="btn bg-white text-primary border-white hover:bg-transparent hover:text-white">
            Schedule Consultation
          </a>
          <a href="#portfolio" class="btn border-white text-white hover:bg-white hover:text-primary">
            View Our Work
          </a>
        </div>
      </div>
    </div>
  {/if}
</section>