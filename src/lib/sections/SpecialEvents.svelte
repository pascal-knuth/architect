<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const events = [
    {
      title: "Live Music Fridays",
      description: "Join us every Friday evening for live acoustic performances by local artists while enjoying your favorite coffee and treats.",
      time: "Every Friday, 7-9 PM",
      image: "https://images.unsplash.com/photo-1415201364774-f6f0bb35f28f"
    },
    {
      title: "Coffee Tasting Workshop",
      description: "Learn about different coffee origins and brewing methods in our monthly tasting workshops led by our expert baristas.",
      time: "First Saturday of each month, 10 AM",
      image: "https://images.unsplash.com/photo-1495474472287-4d71bcdd2085"
    },
    {
      title: "Pastry Making Class",
      description: "Get hands-on experience making classic French pastries with our head baker in these intimate monthly classes.",
      time: "Last Sunday of each month, 9 AM",
      image: "https://images.unsplash.com/photo-1509440159596-0249088772ff"
    }
  ];
</script>

<section class="section bg-white">
  <div class="container">
    <SectionTitle 
      title="Special Events"
      subtitle="Join us for unique experiences that bring our community together"
    />

    {#if visible}
      <div class="grid md:grid-cols-3 gap-8" transition:fade>
        {#each events as event}
          <div class="group bg-white overflow-hidden shadow-lg hover:shadow-xl transition-shadow duration-300">
            <div class="aspect-w-16 aspect-h-9 overflow-hidden">
              <img 
                src={event.image} 
                alt={event.title}
                class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-700"
              />
            </div>
            <div class="p-6">
              <h3 class="text-xl font-bold mb-2">{event.title}</h3>
              <p class="text-gray-600 mb-4">{event.description}</p>
              <div class="flex items-center text-primary">
                <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
                <span class="text-sm font-semibold">{event.time}</span>
              </div>
            </div>
          </div>
        {/each}
      </div>

      <div class="mt-12 text-center">
        <a href="#contact" class="btn btn-primary">Book an Event</a>
      </div>
    {/if}
  </div>
</section>