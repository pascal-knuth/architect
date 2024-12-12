<script lang="ts">
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';
  import SectionTitle from '../components/SectionTitle.svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });
</script>

<section class="section bg-white">
  <div class="container">
    <SectionTitle 
      title="Experience Café Aroma"
      subtitle="Where every cup tells a story and every visit creates a memory"
    />

    {#if visible}
      <!-- Feature 1: Image Left, Text Right -->
      <div class="grid md:grid-cols-2 gap-12 items-center mb-24" transition:fade>
        <div class="relative">
          <div class="aspect-w-4 aspect-h-3 rounded-lg overflow-hidden">
            <img 
              src="https://images.unsplash.com/photo-1495474472287-4d71bcdd2085?auto=format&fit=crop&q=80" 
              alt="Cozy café interior"
              class="w-full h-full object-cover transform hover:scale-105 transition-transform duration-700"
            />
          </div>
          <div class="absolute -bottom-4 -right-4 w-24 h-24 bg-primary/10 rounded-full blur-xl"></div>
        </div>
        <div class="space-y-6">
          <h3 class="text-3xl font-bold">Cozy Atmosphere</h3>
          <p class="text-gray-600 leading-relaxed">
            Step into our warm and inviting space, where the aroma of freshly brewed coffee meets modern comfort. Our café offers the perfect setting for everything from quiet mornings alone to lively afternoon gatherings with friends.
          </p>
          <ul class="space-y-3">
            {#each ['Comfortable seating', 'Natural lighting', 'Free Wi-Fi', 'Climate controlled'] as feature}
              <li class="flex items-center space-x-3">
                <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                </svg>
                <span>{feature}</span>
              </li>
            {/each}
          </ul>
        </div>
      </div>

      <!-- Feature 2: Text Left, Image Right -->
      <div class="grid md:grid-cols-2 gap-12 items-center" transition:fade>
        <div class="space-y-6 order-2 md:order-1">
          <h3 class="text-3xl font-bold">Artisanal Coffee & Pastries</h3>
          <p class="text-gray-600 leading-relaxed">
            Indulge in our selection of carefully crafted beverages and freshly baked pastries. Each item is made with premium ingredients and prepared with passion by our skilled baristas and bakers.
          </p>
          <ul class="space-y-3">
            {#each ['House-roasted coffee beans', 'Fresh-baked daily', 'Seasonal specialties', 'Dietary options available'] as feature}
              <li class="flex items-center space-x-3">
                <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                </svg>
                <span>{feature}</span>
              </li>
            {/each}
          </ul>
        </div>
        <div class="relative order-1 md:order-2">
          <div class="aspect-w-4 aspect-h-3 rounded-lg overflow-hidden">
            <img 
              src="https://images.unsplash.com/photo-1579494376631-9363b9c48359?auto=format&fit=crop&q=80" 
              alt="Coffee and pastries"
              class="w-full h-full object-cover transform hover:scale-105 transition-transform duration-700"
            />
          </div>
          <div class="absolute -bottom-4 -left-4 w-24 h-24 bg-primary/10 rounded-full blur-xl"></div>
        </div>
      </div>
    {/if}
  </div>
</section>