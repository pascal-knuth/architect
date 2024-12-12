<script lang="ts">
  import { onMount } from 'svelte';
  
  let isScrolled = false;
  let isMenuOpen = false;
  
  const handleScroll = () => {
    isScrolled = window.scrollY > 20;
  };
  
  onMount(() => {
    window.addEventListener('scroll', handleScroll);
    return () => {
      window.removeEventListener('scroll', handleScroll);
    };
  });

  const toggleMenu = () => {
    isMenuOpen = !isMenuOpen;
  };

  const menuItems = [
    { href: '#about', text: 'About' },
    { href: '#services', text: 'Services' },
    { href: '#portfolio', text: 'Portfolio' },
    { href: '#contact', text: 'Contact' }
  ];
</script>

<header 
  class="fixed w-full z-50 transition-all duration-300" 
  class:bg-white={isScrolled} 
  class:shadow-lg={isScrolled}
>
  <div class="container mx-auto px-4">
    <nav class="flex items-center justify-between h-20">
      <a href="/" class="text-2xl font-bold text-primary">STUDIO</a>
      
      <!-- Desktop Menu -->
      <div class="hidden md:flex items-center space-x-8">
        {#each menuItems as { href, text }}
          <a {href} class="hover:text-primary transition-colors">{text}</a>
        {/each}
        <a href="#contact" class="btn btn-primary">Get Started</a>
      </div>

      <!-- Mobile Menu Button -->
      <button 
        class="md:hidden p-2 focus:outline-none"
        on:click={toggleMenu}
        aria-label="Toggle menu"
      >
        <div class="w-6 h-6 relative flex items-center justify-center">
          <span 
            class="absolute w-full h-0.5 bg-gray-800 transform transition-all duration-300"
            class:rotate-45={isMenuOpen}
            class:translate-y-0={isMenuOpen}
            class:translate-y-[-6px]={!isMenuOpen}
          ></span>
          <span 
            class="absolute w-full h-0.5 bg-gray-800 transition-opacity duration-300"
            class:opacity-0={isMenuOpen}
          ></span>
          <span 
            class="absolute w-full h-0.5 bg-gray-800 transform transition-all duration-300"
            class:-rotate-45={isMenuOpen}
            class:translate-y-0={isMenuOpen}
            class:translate-y-[6px]={!isMenuOpen}
          ></span>
        </div>
      </button>
    </nav>
  </div>

  <!-- Mobile Menu -->
  <div 
    class="fixed top-0 right-0 w-64 h-full bg-white shadow-2xl transform transition-transform duration-300 ease-in-out z-50"
    class:translate-x-0={isMenuOpen}
    class:translate-x-full={!isMenuOpen}
  >
    <div class="p-6">
      <div class="flex justify-end mb-8">
        <button 
          class="p-2 focus:outline-none"
          on:click={toggleMenu}
          aria-label="Close menu"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
          </svg>
        </button>
      </div>
      <div class="flex flex-col space-y-4">
        {#each menuItems as { href, text }}
          <a 
            {href} 
            class="text-gray-800 hover:text-primary transition-colors py-2"
            on:click={toggleMenu}
          >
            {text}
          </a>
        {/each}
        <a 
          href="#contact" 
          class="btn btn-primary text-center mt-4"
          on:click={toggleMenu}
        >
          Get Started
        </a>
      </div>
    </div>
  </div>

  <!-- Overlay -->
  {#if isMenuOpen}
    <div 
      class="fixed inset-0 bg-black bg-opacity-50 z-40"
      on:click={toggleMenu}
    ></div>
  {/if}
</header>

<style>
  /* Prevent scroll when menu is open */
  :global(body.menu-open) {
    overflow: hidden;
  }
</style>