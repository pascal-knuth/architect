<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import FaqItem from '../components/FaqItem.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const faqs = [
    {
      question: "What industries do you specialize in?",
      answer: "We specialize in serving enterprise clients across manufacturing, finance, healthcare, retail, and technology sectors. Our solutions are tailored to meet industry-specific challenges while maintaining the highest standards of security and compliance."
    },
    {
      question: "How long does a typical digital transformation project take?",
      answer: "Project timelines vary based on scope and complexity. Typically, our enterprise solutions are delivered in phases over 3-12 months. We work closely with clients to establish realistic timelines and ensure minimal disruption to ongoing operations."
    },
    {
      question: "What security measures do you implement?",
      answer: "We implement enterprise-grade security measures including end-to-end encryption, multi-factor authentication, regular security audits, and compliance with ISO 27001 standards. Our solutions are designed with security-first architecture."
    },
    {
      question: "Do you provide ongoing support after implementation?",
      answer: "Yes, we offer comprehensive post-implementation support including 24/7 monitoring, maintenance, updates, and dedicated technical support. We also provide training and documentation to ensure your team can effectively manage the system."
    },
    {
      question: "What makes your solutions different from competitors?",
      answer: "Our solutions stand out through their enterprise-grade scalability, cutting-edge technology stack, and proven track record of success. We focus on delivering measurable ROI while ensuring seamless integration with existing systems."
    }
  ];
</script>

<section id="faq" class="section bg-white">
  <div class="container max-w-4xl">
    <SectionTitle 
      title="Frequently Asked Questions"
      subtitle="Get answers to common questions about our enterprise solutions and services"
    />

    {#if visible}
      <div class="space-y-2" transition:fade>
        {#each faqs as faq}
          <FaqItem {...faq} />
        {/each}
      </div>
    {/if}
  </div>
</section>