<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import SuccessStory from '../components/SuccessStory.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const successStories = [
    {
      title: 'Digital Transformation Journey',
      client: 'TechCorp Industries',
      industry: 'Manufacturing',
      challenge: 'Legacy systems were causing inefficiencies and preventing scalability across 50+ global locations.',
      solution: 'Implemented a cloud-based enterprise platform with IoT integration and real-time analytics dashboard.',
      results: [
        'Reduced operational costs by 35%',
        'Improved production efficiency by 45%',
        'Achieved 99.9% system uptime',
        'ROI achieved within 8 months'
      ],
      image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?auto=format&fit=crop&q=80',
      logo: 'https://placehold.co/200x80/ffffff/1a365d.png?text=TechCorp'
    },
    {
      title: 'AI-Powered Customer Analytics',
      client: 'GlobalRetail',
      industry: 'Retail & E-commerce',
      challenge: 'Needed to personalize shopping experiences and optimize inventory across 1000+ stores.',
      solution: 'Developed an AI-powered analytics platform with predictive modeling and real-time recommendations.',
      results: [
        'Increased customer retention by 40%',
        'Boosted online sales by 150%',
        'Reduced inventory costs by 25%',
        'Improved customer satisfaction by 60%'
      ],
      image: 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&q=80',
      logo: 'https://placehold.co/200x80/ffffff/1a365d.png?text=GlobalRetail'
    },
    {
      title: 'Enterprise Security Overhaul',
      client: 'SecureBank',
      industry: 'Financial Services',
      challenge: 'Required a comprehensive security upgrade to meet regulatory requirements and protect customer data.',
      solution: 'Implemented advanced encryption, biometric authentication, and real-time threat detection systems.',
      results: [
        'Achieved ISO 27001 certification',
        'Zero security breaches in 24 months',
        'Reduced fraud attempts by 85%',
        'Compliance with all banking regulations'
      ],
      image: 'https://images.unsplash.com/photo-1563013544-824ae1b704d3?auto=format&fit=crop&q=80',
      logo: 'https://placehold.co/200x80/ffffff/1a365d.png?text=SecureBank'
    }
  ];
</script>

<section id="portfolio" class="section bg-gray-50">
  <div class="container">
    <SectionTitle 
      title="Success Stories"
      subtitle="Discover how we've helped leading businesses achieve remarkable results through digital transformation"
      align="left"
    />

    {#if visible}
      <div class="grid lg:grid-cols-3 gap-8" transition:fade>
        {#each successStories as story}
          <SuccessStory {...story} />
        {/each}
      </div>

      <div class="mt-20 text-center">
        <p class="text-xl text-gray-600 mb-8 max-w-2xl mx-auto">
          Ready to write your own success story? Let's discuss how we can help transform your business.
        </p>
        <a 
          href="#contact" 
          class="btn btn-primary text-lg px-10 py-4 shadow-lg shadow-primary/20 hover:shadow-xl hover:shadow-primary/30"
        >
          Start Your Transformation
        </a>
      </div>
    {/if}
  </div>
</section>