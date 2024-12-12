<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import InfoCard from '../components/InfoCard.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const services = [
    {
      icon: `<svg class="w-16 h-16" fill="currentColor" viewBox="0 0 24 24">
        <path d="M2 15a1 1 0 011-1h16a1 1 0 110 2H3a1 1 0 01-1-1zm0-4a1 1 0 011-1h16a1 1 0 110 2H3a1 1 0 01-1-1zm0-4a1 1 0 011-1h16a1 1 0 110 2H3a1 1 0 01-1-1z"></path>
      </svg>`,
      title: 'Breakfast & Brunch',
      description: 'Start your day with our freshly baked pastries, hearty breakfast plates, and signature coffee blends.'
    },
    {
      icon: `<svg class="w-16 h-16" fill="currentColor" viewBox="0 0 24 24">
        <path d="M12 4c2.2 0 4 1.8 4 4v2H8V8c0-2.2 1.8-4 4-4zm6 6v2c0 3.3-2.7 6-6 6s-6-2.7-6-6v-2H4v2c0 4.4 3.6 8 8 8s8-3.6 8-8v-2h-2z"></path>
      </svg>`,
      title: 'Specialty Coffee',
      description: 'Expertly crafted coffee drinks using premium beans from around the world, roasted to perfection.'
    },
    {
      icon: `<svg class="w-16 h-16" fill="currentColor" viewBox="0 0 24 24">
        <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"></path>
      </svg>`,
      title: 'Fresh Pastries',
      description: 'Daily baked goods including croissants, muffins, and seasonal specialties made from scratch.'
    },
    {
      icon: `<svg class="w-16 h-16" fill="currentColor" viewBox="0 0 24 24">
        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-7 14h-2v-2h2v2zm0-4h-2V7h2v6z"></path>
      </svg>`,
      title: 'Events & Catering',
      description: 'Let us cater your next event with our delicious menu items and professional service.'
    }
  ];
</script>

<section id="menu" class="section bg-gray-50">
  <div class="container">
    <SectionTitle 
      title="Our Menu"
      subtitle="Discover our selection of handcrafted beverages and fresh-baked goods"
      align="left"
    />

    {#if visible}
      <div class="grid md:grid-cols-2 gap-px bg-gray-200" transition:fade>
        {#each services as service}
          <InfoCard {...service} />
        {/each}
      </div>

      <div class="mt-20 text-center">
        <a href="#contact" class="btn btn-primary">
          Order Now
        </a>
      </div>
    {/if}
  </div>
</section>