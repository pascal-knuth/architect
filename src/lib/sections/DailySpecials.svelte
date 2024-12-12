<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const specials = [
    {
      day: "Today's",
      items: [
        {
          name: "Caramel Macchiato",
          price: "3.99",
          description: "Freshly pulled espresso with vanilla syrup and caramel drizzle",
          tag: "Drink Special"
        },
        {
          name: "Almond Croissant",
          price: "2.99",
          description: "Flaky croissant filled with almond cream and topped with sliced almonds",
          tag: "Pastry Special"
        }
      ]
    },
    {
      day: "Weekly",
      items: [
        {
          name: "Breakfast Bundle",
          price: "8.99",
          description: "Any coffee drink + pastry of your choice",
          tag: "Bundle Deal"
        },
        {
          name: "Afternoon Tea Set",
          price: "12.99",
          description: "Selection of pastries with your choice of premium tea",
          tag: "Set Menu"
        }
      ]
    }
  ];
</script>

<section class="section bg-gray-50">
  <div class="container max-w-5xl">
    <SectionTitle 
      title="Daily Specials"
      subtitle="Enjoy our carefully selected daily and weekly special offers"
    />

    {#if visible}
      <div class="grid md:grid-cols-2 gap-12" transition:fade>
        {#each specials as special}
          <div>
            <h3 class="text-2xl font-bold mb-6 text-primary">{special.day} Specials</h3>
            <div class="space-y-6">
              {#each special.items as item}
                <div class="bg-white p-6 shadow-md hover:shadow-lg transition-shadow duration-300">
                  <div class="flex justify-between items-start mb-2">
                    <div>
                      <h4 class="text-xl font-semibold">{item.name}</h4>
                      <span class="inline-block px-3 py-1 bg-primary/10 text-primary text-sm font-medium rounded-full mt-1">
                        {item.tag}
                      </span>
                    </div>
                    <span class="text-2xl font-bold text-primary">${item.price}</span>
                  </div>
                  <p class="text-gray-600 mt-3">{item.description}</p>
                </div>
              {/each}
            </div>
          </div>
        {/each}
      </div>

      <div class="mt-16 text-center">
        <p class="text-gray-600 mb-6">Specials change regularly. Visit us to discover new flavors!</p>
        <a href="#order" class="btn btn-primary">Order Now</a>
      </div>
    {/if}
  </div>
</section>