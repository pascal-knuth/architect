<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const stats = [
    { number: '15+', label: 'Years of Service' },
    { number: '1000+', label: 'Happy Customers' },
    { number: '30+', label: 'Coffee Varieties' },
    { number: '100%', label: 'Fresh Ingredients' }
  ];
</script>

<section id="about" class="section bg-gray-50">
  <div class="container">
    <SectionTitle 
      title="Our Story"
      subtitle="A family-owned café bringing you the finest coffee and homemade treats since 2008"
    />

    {#if visible}
      <div class="grid md:grid-cols-2 gap-12 items-center" transition:fade>
        <!-- About Content -->
        <div class="space-y-6">
          <h3 class="text-2xl font-bold text-gray-800">
            Crafting Moments of Joy
          </h3>
          <p class="text-gray-600">
            At Café Aroma, we believe in creating more than just great coffee. We're passionate about crafting memorable experiences through our carefully selected beans, freshly baked pastries, and warm, welcoming atmosphere.
          </p>
          <div class="flex gap-4">
            <a href="#menu" class="btn btn-primary">Our Menu</a>
            <a href="#contact" class="btn bg-white border-2 border-primary text-primary hover:bg-primary hover:text-white">
              Find Us
            </a>
          </div>
        </div>

        <!-- Stats Grid -->
        <div class="grid grid-cols-2 gap-6">
          {#each stats as { number, label }}
            <div class="bg-white p-6 rounded-lg shadow-md text-center">
              <div class="text-3xl font-bold text-primary mb-2">{number}</div>
              <div class="text-gray-600">{label}</div>
            </div>
          {/each}
        </div>
      </div>
    {/if}
  </div>
</section>