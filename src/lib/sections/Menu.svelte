<script lang="ts">
  import SectionTitle from '../components/SectionTitle.svelte';
  import { fade } from 'svelte/transition';
  import { onMount } from 'svelte';

  let visible = false;
  onMount(() => {
    visible = true;
  });

  const menuCategories = [
    {
      title: 'Coffee & Espresso',
      items: [
        {
          name: 'Espresso',
          price: '3.50',
          description: 'Rich and bold single shot',
          image: 'https://images.unsplash.com/photo-1510707577719-ae7c14805e3a?auto=format&fit=crop&q=80'
        },
        {
          name: 'Cappuccino',
          price: '4.50',
          description: 'Espresso with steamed milk and foam',
          image: 'https://images.unsplash.com/photo-1572442388796-11668a67e53d?auto=format&fit=crop&q=80'
        },
        {
          name: 'Latte',
          price: '4.75',
          description: 'Espresso with lots of steamed milk and light foam',
          image: 'https://images.unsplash.com/photo-1461023058943-07fcbe16d735?auto=format&fit=crop&q=80'
        },
        {
          name: 'Americano',
          price: '3.75',
          description: 'Espresso with hot water',
          image: 'https://images.unsplash.com/photo-1551030173-122aabc4489c?auto=format&fit=crop&q=80'
        }
      ]
    },
    {
      title: 'Fresh Pastries',
      items: [
        {
          name: 'Croissant',
          price: '3.25',
          description: 'Buttery, flaky pastry',
          image: 'https://images.unsplash.com/photo-1555507036-ab1f4038808a?auto=format&fit=crop&q=80'
        },
        {
          name: 'Pain au Chocolat',
          price: '3.75',
          description: 'Chocolate-filled croissant',
          image: 'https://images.unsplash.com/photo-1608198093002-ad4e005484ec?auto=format&fit=crop&q=80'
        },
        {
          name: 'Cinnamon Roll',
          price: '4.25',
          description: 'Fresh-baked with cream cheese frosting',
          image: 'https://images.unsplash.com/photo-1509365465985-25d11c17e812?auto=format&fit=crop&q=80'
        },
        {
          name: 'Blueberry Muffin',
          price: '3.50',
          description: 'Made with fresh blueberries',
          image: 'https://images.unsplash.com/photo-1607958996333-41aef7caefaa?auto=format&fit=crop&q=80'
        }
      ]
    }
  ];
</script>

<section id="menu" class="section bg-gray-50">
  <div class="container max-w-6xl">
    <SectionTitle 
      title="Our Menu"
      subtitle="Handcrafted coffee and fresh-baked pastries made with love"
    />

    {#if visible}
      <div class="space-y-16" transition:fade>
        {#each menuCategories as category}
          <div>
            <h3 class="text-2xl font-bold mb-8 text-primary">{category.title}</h3>
            <div class="grid md:grid-cols-2 gap-8">
              {#each category.items as item}
                <div class="bg-white rounded-lg shadow-md hover:shadow-xl transition-all duration-300 overflow-hidden group">
                  <div class="aspect-w-16 aspect-h-9 overflow-hidden">
                    <img 
                      src={item.image} 
                      alt={item.name}
                      class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-700"
                    />
                  </div>
                  <div class="p-6">
                    <div class="flex justify-between items-start mb-2">
                      <h4 class="text-xl font-semibold">{item.name}</h4>
                      <span class="text-primary font-bold text-lg">${item.price}</span>
                    </div>
                    <p class="text-gray-600">{item.description}</p>
                  </div>
                </div>
              {/each}
            </div>
          </div>
        {/each}
      </div>

      <div class="mt-16 text-center">
        <p class="text-gray-600 mb-8">
          All our coffee beans are locally roasted and our pastries are baked fresh daily
        </p>
        <a href="#order" class="btn btn-primary">Order Now</a>
      </div>
    {/if}
  </div>
</section>