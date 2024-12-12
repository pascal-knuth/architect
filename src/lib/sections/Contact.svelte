<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  let formData = {
    name: '',
    email: '',
    company: '',
    message: ''
  };

  const handleSubmit = (e: Event) => {
    e.preventDefault();
    // Handle form submission
    console.log('Form submitted:', formData);
  };
</script>

<section id="contact" class="section bg-gray-50">
  <div class="container max-w-6xl">
    <SectionTitle 
      title="Let's Transform Your Business"
      subtitle="Schedule a consultation with our experts to discuss your digital transformation needs"
    />

    {#if visible}
      <div class="grid md:grid-cols-2 gap-12 items-start" transition:fade>
        <!-- Contact Form -->
        <div class="bg-white p-8 shadow-xl">
          <form on:submit={handleSubmit} class="space-y-6">
            <div>
              <label for="name" class="block text-sm font-medium text-gray-700">Name</label>
              <input
                type="text"
                id="name"
                bind:value={formData.name}
                class="mt-1 block w-full border-gray-300 shadow-sm focus:ring-primary focus:border-primary"
                required
              />
            </div>

            <div>
              <label for="email" class="block text-sm font-medium text-gray-700">Email</label>
              <input
                type="email"
                id="email"
                bind:value={formData.email}
                class="mt-1 block w-full border-gray-300 shadow-sm focus:ring-primary focus:border-primary"
                required
              />
            </div>

            <div>
              <label for="company" class="block text-sm font-medium text-gray-700">Company</label>
              <input
                type="text"
                id="company"
                bind:value={formData.company}
                class="mt-1 block w-full border-gray-300 shadow-sm focus:ring-primary focus:border-primary"
                required
              />
            </div>

            <div>
              <label for="message" class="block text-sm font-medium text-gray-700">Message</label>
              <textarea
                id="message"
                bind:value={formData.message}
                rows="4"
                class="mt-1 block w-full border-gray-300 shadow-sm focus:ring-primary focus:border-primary"
                required
              ></textarea>
            </div>

            <div>
              <button type="submit" class="btn btn-primary w-full">
                Schedule Consultation
              </button>
            </div>
          </form>
        </div>

        <!-- Contact Information -->
        <div class="space-y-8">
          <div>
            <h3 class="text-2xl font-bold mb-4">Get in Touch</h3>
            <p class="text-gray-600">Our team of experts is ready to discuss your digital transformation needs.</p>
          </div>

          <div class="space-y-4">
            <div class="flex items-start space-x-4">
              <svg class="w-6 h-6 text-primary mt-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
              </svg>
              <div>
                <h4 class="font-semibold">Phone</h4>
                <p class="text-gray-600">+1 (555) 123-4567</p>
              </div>
            </div>

            <div class="flex items-start space-x-4">
              <svg class="w-6 h-6 text-primary mt-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
              </svg>
              <div>
                <h4 class="font-semibold">Email</h4>
                <p class="text-gray-600">contact@xyz.com</p>
              </div>
            </div>

            <div class="flex items-start space-x-4">
              <svg class="w-6 h-6 text-primary mt-1" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>
              <div>
                <h4 class="font-semibold">Location</h4>
                <p class="text-gray-600">123 Business Avenue<br/>New York, NY 10001</p>
              </div>
            </div>
          </div>

          <div class="bg-primary/5 p-6">
            <h4 class="font-semibold mb-2">Response Time</h4>
            <p class="text-gray-600">We typically respond within 24 hours during business days.</p>
          </div>
        </div>
      </div>
    {/if}
  </div>
</section>