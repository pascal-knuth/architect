<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const images = [
    {
      src: 'https://images.unsplash.com/photo-1442512595331-e89e73853f31',
      alt: 'Fresh baked croissants',
      caption: 'Fresh Baked Daily'
    },
    {
      src: 'https://images.unsplash.com/photo-1509042239860-f550ce710b93',
      alt: 'Latte art',
      caption: 'Artisanal Coffee'
    },
    {
      src: 'https://images.unsplash.com/photo-1554118811-1e0d58224f24',
      alt: 'Café interior',
      caption: 'Cozy Atmosphere'
    },
    {
      src: 'https://images.unsplash.com/photo-1507133750040-4a8f57021571',
      alt: 'Coffee beans',
      caption: 'Premium Beans'
    },
    {
      src: 'https://images.unsplash.com/photo-1515823662972-da6a2e4d3002',
      alt: 'Pastry display',
      caption: 'Fresh Pastries'
    },
    {
      src: 'https://images.unsplash.com/photo-1445116572660-236099ec97a0',
      alt: 'Coffee brewing',
      caption: 'Expertly Crafted'
    }
  ];
</script>

<section id="gallery" class="section bg-white">
  <div class="container">
    <SectionTitle 
      title="Gallery"
      subtitle="A glimpse into our cozy café and delicious offerings"
    />

    {#if visible}
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8" transition:fade>
        {#each images as image}
          <div class="group relative overflow-hidden rounded-lg">
            <div class="aspect-w-4 aspect-h-3">
              <img 
                src={image.src} 
                alt={image.alt}
                class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-700"
              />
            </div>
            <div class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
              <span class="text-white text-xl font-semibold">{image.caption}</span>
            </div>
          </div>
        {/each}
      </div>

      <div class="mt-16 text-center">
        <a href="#contact" class="btn btn-primary">Visit Us Today</a>
      </div>
    {/if}
  </div>
</section>