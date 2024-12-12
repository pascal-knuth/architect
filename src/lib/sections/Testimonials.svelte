<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import TestimonialCard from '../components/TestimonialCard.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const testimonials = [
    {
      name: 'Sarah Johnson',
      role: 'CTO',
      company: 'TechCorp',
      image: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&q=80',
      quote: 'Working with XYZ transformed our digital presence. Their expertise and dedication to quality are unmatched.',
      rating: 5
    },
    {
      name: 'Michael Chen',
      role: 'Marketing Director',
      company: 'GlobalBrands',
      image: 'https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?auto=format&fit=crop&q=80',
      quote: 'The team at XYZ delivered beyond our expectations. Our conversion rates have increased by 150% since launch.',
      rating: 5
    },
    {
      name: 'Emma Thompson',
      role: 'CEO',
      company: 'Innovate Inc',
      image: 'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?auto=format&fit=crop&q=80',
      quote: 'Their strategic approach and technical expertise helped us achieve our digital transformation goals ahead of schedule.',
      rating: 5
    }
  ];
</script>

<section id="testimonials" class="section bg-gradient-to-br from-primary/5 to-accent/5">
  <div class="container relative">
    <!-- Background Elements -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute -top-20 -left-20 w-40 h-40 bg-primary/10 rounded-full blur-3xl"></div>
      <div class="absolute -bottom-20 -right-20 w-40 h-40 bg-accent/10 rounded-full blur-3xl"></div>
    </div>

    <SectionTitle 
      title="Client Success Stories"
      subtitle="Hear from our satisfied clients about their experience working with us"
    />

    {#if visible}
      <div class="grid md:grid-cols-3 gap-8 relative z-10" transition:fade>
        {#each testimonials as testimonial}
          <TestimonialCard {...testimonial} />
        {/each}
      </div>

      <div class="mt-20 text-center">
        <a 
          href="#contact" 
          class="btn btn-primary text-lg px-10 py-4 shadow-lg shadow-primary/20 hover:shadow-xl hover:shadow-primary/30"
        >
          Join Our Success Stories
        </a>
      </div>
    {/if}
  </div>
</section>