<script lang="ts">
  export let title: string;
  export let subtitle: string;
  export let align: 'left' | 'center' = 'center';
</script>

<div class="mb-20" class:text-center={align === 'center'}>
  <h2 class="section-title">{title}</h2>
  <p class="section-subtitle" class:mx-0={align === 'left'}>{subtitle}</p>
</div>