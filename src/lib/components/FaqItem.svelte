<script lang="ts">
  export let question: string;
  export let answer: string;
  let isOpen = false;
</script>

<div class="border-b border-gray-200">
  <button
    class="w-full py-6 text-left focus:outline-none"
    on:click={() => isOpen = !isOpen}
  >
    <div class="flex items-center justify-between">
      <h3 class="text-lg font-semibold text-gray-900">{question}</h3>
      <span class="ml-6 flex-shrink-0">
        <svg
          class="w-6 h-6 transform transition-transform duration-300"
          class:rotate-180={isOpen}
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
        </svg>
      </span>
    </div>
    {#if isOpen}
      <p class="mt-4 text-gray-600 pr-12">{answer}</p>
    {/if}
  </button>
</div>