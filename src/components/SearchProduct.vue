<script setup lang="ts">
import IconChevronRight from '@/components/icons/IconChevronRight.vue'

interface Product {
  id: string|number,
  name: string,
  image: string|null,
  description: string|null,
  price: string|number|null,
}

interface Props {
  products?: Array<Product>,
}

const props = withDefaults(defineProps<Props>(), {
  products: () => [
    {
      id: 1,
      name: 'Pizza',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 12.99,
      image: 'Pizza.png',
    },
    {
      id: 2,
      name: 'Burger',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 8.2,
      image: 'Burger.png',
    },
    {
      id: 3,
      name: 'Noodles',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 8.93,
      image: 'Spaghetti.png',
    },
    {
      id: 4,
      name: 'Sub-sandwich',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 7.64,
      image: 'Sandwich.png',
    },
    {
      id: 5,
      name: 'Chowmein',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 6.2,
      image: 'Chowmein.png',
    },
    {
      id: 6,
      name: 'Steak',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 3.5,
      image: 'Steak.png',
    },
  ],
});

function getImageUrl(productImage: string|null = null): string {
  let _url = '../assets/FoodPhoto.png';
  if (productImage) {
    _url = '../assets/' + productImage;
  }

  return new URL(_url, import.meta.url).href;
}
</script>

<template>
  <div class="flex">
    <div class="flex w-full justify-between">
      <div>
        <h2 class="font-bold text-4xl">
          Rechercher un repas
        </h2>
      </div>

      <div class="flex gap-3">
        <a href="#" class="flex items-center">
          Voir tout
          <IconChevronRight class="ml-1" />
        </a>

        <button type="button" class="bg-white rounded-full text-green-700 p-3">
          <IconChevronRight class="rotate-180" />
        </button>

        <button type="button" class="bg-white rounded-full text-green-700 p-3">
          <IconChevronRight />
        </button>
      </div>
    </div>

    <div class="flex gap-3 mt-16">
      <a href="#" class="flex items-center flex-col" v-for="product in props.products" v-bind:key="product.id">
        <div class="flex items-center flex-col w-[12rem] rounded-full overflow-hidden relative">
          <!--            <span :style="{background: `${new URL('../assets/FoodPhoto.png', import.meta.url).href}`}" class="text-green-700 block h-[12rem] object-contain"></span>-->
          <img :src="getImageUrl(product.image)" class="text-green-700 h-[12rem] object-cover" alt="Map icon"/>
        </div>
        <div class="mt-4">
          <span class="font-semibold text-lg">
            {{ product.name}}
          </span>
        </div>
      </a>
    </div>
  </div>
</template>

<style scoped>

</style>
