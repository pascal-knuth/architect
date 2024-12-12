<script lang="ts">
  export let icon: string;
  export let title: string;
  export let description: string;
</script>

<div class="bg-white p-10 shadow-lg hover:shadow-2xl transition-all duration-500 group">
  <div class="text-primary mb-6 transform group-hover:scale-110 transition-transform duration-500">
    {@html icon}
  </div>
  <h3 class="text-2xl font-bold mb-4">{title}</h3>
  <p class="text-gray-600 leading-relaxed">{description}</p>
  <div class="mt-8">
    <a href="#contact" class="text-primary font-semibold uppercase tracking-wider text-sm group-hover:text-accent transition-colors duration-300">
      Learn More →
    </a>
  </div>
</div>