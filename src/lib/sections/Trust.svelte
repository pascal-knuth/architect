<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import TrustBadge from '../components/TrustBadge.svelte';
  import LogoSlider from '../components/LogoSlider.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const trustBadges = [
    {
      icon: `<svg class="w-12 h-12 mx-auto" fill="currentColor" viewBox="0 0 24 24">
        <path d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z" />
      </svg>`,
      title: 'ISO Certified',
      value: 'ISO 27001'
    },
    {
      icon: `<svg class="w-12 h-12 mx-auto" fill="currentColor" viewBox="0 0 24 24">
        <path d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
      </svg>`,
      title: 'Security',
      value: 'Enterprise-Grade'
    },
    {
      icon: `<svg class="w-12 h-12 mx-auto" fill="currentColor" viewBox="0 0 24 24">
        <path d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
      </svg>`,
      title: 'Uptime',
      value: '99.99%'
    },
    {
      icon: `<svg class="w-12 h-12 mx-auto" fill="currentColor" viewBox="0 0 24 24">
        <path d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z" />
      </svg>`,
      title: 'Active Users',
      value: '1M+'
    }
  ];

  const clientLogos = [
    { src: 'https://upload.wikimedia.org/wikipedia/commons/a/a9/Amazon_logo.svg', alt: 'Amazon' },
    { src: 'https://upload.wikimedia.org/wikipedia/commons/2/2f/Google_2015_logo.svg', alt: 'Google' },
    { src: 'https://upload.wikimedia.org/wikipedia/commons/4/44/Microsoft_logo.svg', alt: 'Microsoft' },
    { src: 'https://upload.wikimedia.org/wikipedia/commons/5/51/IBM_logo.svg', alt: 'IBM' },
    { src: 'https://upload.wikimedia.org/wikipedia/commons/b/b1/Tesla_Motors.svg', alt: 'Tesla' },
    { src: 'https://upload.wikimedia.org/wikipedia/commons/0/08/Netflix_2015_logo.svg', alt: 'Netflix' },
    { src: 'https://upload.wikimedia.org/wikipedia/commons/f/fa/Apple_logo_black.svg', alt: 'Apple' },
    { src: 'https://upload.wikimedia.org/wikipedia/commons/2/24/Samsung_Logo.svg', alt: 'Samsung' }
  ];
</script>

<section id="trust" class="section bg-gradient-to-b from-gray-50 to-white">
  <div class="container">
    <SectionTitle 
      title="Trusted by Industry Leaders"
      subtitle="Join thousands of businesses that trust us with their digital presence"
    />

    {#if visible}
      <div class="grid md:grid-cols-4 gap-8 mb-20" transition:fade>
        {#each trustBadges as badge}
          <TrustBadge {...badge} />
        {/each}
      </div>

      <div class="bg-white rounded-3xl p-12 shadow-xl" transition:fade>
        <h3 class="text-3xl font-bold text-center mb-12 bg-gradient-to-r from-primary to-accent bg-clip-text text-transparent">
          Trusted by Global Brands
        </h3>
        <LogoSlider logos={clientLogos} />
      </div>
    {/if}
  </div>
</section>