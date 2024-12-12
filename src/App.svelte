<script lang="ts">
  import Header from './lib/Header.svelte';
  import Hero from './lib/Hero.svelte';
  import About from './lib/sections/About.svelte';
  import Features from './lib/sections/Features.svelte';
  import Menu from './lib/sections/Menu.svelte';
  import DailySpecials from './lib/sections/DailySpecials.svelte';
  import Gallery from './lib/sections/Gallery.svelte';
  import Atmosphere from './lib/sections/Atmosphere.svelte';
  import SpecialEvents from './lib/sections/SpecialEvents.svelte';
  import Testimonials from './lib/sections/Testimonials.svelte';
  import FAQ from './lib/sections/FAQ.svelte';
  import Contact from './lib/sections/Contact.svelte';
  import Footer from './lib/Footer.svelte';
</script>

<Header />
<main>
  <Hero />
  <About />
  <Features />
  <Menu />
  <DailySpecials />
  <Gallery />
  <Atmosphere />
  <SpecialEvents />
  <Testimonials />
  <FAQ />
  <Contact />
</main>
<Footer />

<style>
  :global(html) {
    scroll-behavior: smooth;
  }
</style>