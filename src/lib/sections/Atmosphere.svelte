<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const features = [
    {
      title: 'Indoor Seating',
      images: [
        {
          src: 'https://images.unsplash.com/photo-1521017432531-fbd92d768814',
          alt: 'Cozy indoor seating area',
          caption: 'Comfortable Spaces'
        },
        {
          src: 'https://images.unsplash.com/photo-1554118811-1e0d58224f24',
          alt: 'Window seating with natural light',
          caption: 'Natural Light'
        }
      ]
    },
    {
      title: 'Outdoor Terrace',
      images: [
        {
          src: 'https://images.unsplash.com/photo-1445116572660-236099ec97a0',
          alt: 'Beautiful outdoor terrace',
          caption: 'Garden Views'
        },
        {
          src: 'https://images.unsplash.com/photo-1523906834658-6e24ef2386f9',
          alt: 'Outdoor seating area',
          caption: 'Al Fresco Dining'
        }
      ]
    },
    {
      title: 'Workspace',
      images: [
        {
          src: 'https://images.unsplash.com/photo-1497366216548-37526070297c',
          alt: 'Dedicated workspace area',
          caption: 'Productive Environment'
        },
        {
          src: 'https://images.unsplash.com/photo-1554118811-1e0d58224f24',
          alt: 'Coffee and laptop friendly space',
          caption: 'Free Wi-Fi'
        }
      ]
    }
  ];
</script>

<section class="section bg-white">
  <div class="container">
    <SectionTitle 
      title="Experience Our Space"
      subtitle="Discover the perfect blend of comfort, style, and functionality in our carefully designed spaces"
    />

    {#if visible}
      <div class="space-y-24" transition:fade>
        {#each features as feature, i}
          <div class="grid md:grid-cols-2 gap-8 items-center" class:md:flex-row-reverse={i % 2 === 1}>
            <div class="space-y-8">
              <h3 class="text-3xl font-bold text-primary">{feature.title}</h3>
              <div class="grid grid-cols-2 gap-4">
                {#each feature.images as image}
                  <div class="group relative overflow-hidden rounded-lg">
                    <div class="aspect-w-4 aspect-h-3">
                      <img 
                        src={image.src} 
                        alt={image.alt}
                        class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-700"
                      />
                    </div>
                    <div class="absolute inset-0 bg-black bg-opacity-40 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                      <span class="text-white text-lg font-medium">{image.caption}</span>
                    </div>
                  </div>
                {/each}
              </div>
            </div>

            <div class="space-y-6">
              {#if i === 0}
                <p class="text-gray-600 leading-relaxed">
                  Step into our thoughtfully designed interior where comfort meets style. Our spacious seating areas feature plush chairs, ambient lighting, and plenty of natural sunlight, creating the perfect atmosphere for enjoying your favorite coffee or catching up with friends.
                </p>
              {:else if i === 1}
                <p class="text-gray-600 leading-relaxed">
                  Enjoy your coffee in our beautiful outdoor terrace, surrounded by greenery and fresh air. Perfect for sunny mornings or warm afternoons, our outdoor space offers a peaceful retreat from the busy city life.
                </p>
              {:else}
                <p class="text-gray-600 leading-relaxed">
                  Need a productive space to work or study? Our dedicated workspace areas offer comfortable seating, power outlets, and free high-speed Wi-Fi. Whether you're having a casual meeting or working solo, we've got the perfect spot for you.
                </p>
              {/if}
              <ul class="space-y-3">
                {#if i === 0}
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Comfortable seating arrangements</span>
                  </li>
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Ambient lighting</span>
                  </li>
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Climate controlled environment</span>
                  </li>
                {:else if i === 1}
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Garden views</span>
                  </li>
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Shaded seating areas</span>
                  </li>
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Pet-friendly space</span>
                  </li>
                {:else}
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Free high-speed Wi-Fi</span>
                  </li>
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Power outlets at every table</span>
                  </li>
                  <li class="flex items-center space-x-2">
                    <svg class="w-5 h-5 text-primary" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                    </svg>
                    <span>Quiet zones available</span>
                  </li>
                {/if}
              </ul>
            </div>
          </div>
        {/each}
      </div>

      <div class="mt-20 text-center">
        <a href="#contact" class="btn btn-primary">Visit Us Today</a>
      </div>
    {/if}
  </div>
</section>