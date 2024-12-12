<script lang="ts">
  export let title: string;
  export let client: string;
  export let industry: string;
  export let challenge: string;
  export let solution: string;
  export let results: string[];
  export let image: string;
  export let logo: string;
</script>

<div class="bg-white rounded-lg shadow-xl overflow-hidden group">
  <div class="relative aspect-w-16 aspect-h-9 overflow-hidden">
    <img 
      src={image} 
      alt={title}
      class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-700"
    />
    <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent">
      <div class="absolute bottom-6 left-6">
        <img src={logo} alt={client} class="h-12 bg-white rounded-lg p-2" />
      </div>
    </div>
  </div>
  
  <div class="p-8">
    <div class="text-sm text-primary font-semibold uppercase tracking-wider mb-2">
      {industry}
    </div>
    <h3 class="text-2xl font-bold mb-4">{title}</h3>
    
    <div class="space-y-6">
      <div>
        <h4 class="text-lg font-semibold mb-2">Challenge</h4>
        <p class="text-gray-600">{challenge}</p>
      </div>
      
      <div>
        <h4 class="text-lg font-semibold mb-2">Solution</h4>
        <p class="text-gray-600">{solution}</p>
      </div>
      
      <div>
        <h4 class="text-lg font-semibold mb-2">Key Results</h4>
        <ul class="space-y-2">
          {#each results as result}
            <li class="flex items-start">
              <svg class="w-5 h-5 text-primary mt-1 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
              </svg>
              <span class="text-gray-600">{result}</span>
            </li>
          {/each}
        </ul>
      </div>
    </div>
  </div>
</div>