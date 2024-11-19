<script setup lang="ts">

import IconMap from '@/components/icons/IconMap.vue'

interface Product {
  id: string|number,
  name: string,
  image: string|null,
  description: string|null,
  location: string|null,
  price: number,
}

interface Props {
  products?: Array<Product>,
}

const props = withDefaults(defineProps<Props>(), {
  products: () => [
    {
      id: 1,
      name: 'Cheese Burger',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 3.88,
      location: 'Gosormo Burger',
      image: 'Pizza.png',
    },
    {
      id: 2,
      name: 'Gateau de Toffe',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 4.00,
      location: 'Tata Solange',
      image: 'Cake1.png',
    },
    {
      id: 3,
      name: 'Dancake',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 1.99,
      location: 'Cake World',
      image: 'Dancake.png',
    },
    {
      id: 4,
      name: 'Sandwitche',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 3.00,
      location: 'Dagobest Food',
      image: 'Sandwitche.png',
    },
    {
      id: 5,
      name: 'Soup Thai',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 13.40,
      location: 'Ma\'a Magne',
      image: 'SoupThai.png',
    },
  ],
});

const formattedPrice = (price: number) => {
  return new Intl.NumberFormat('fr-FR', {
    style: 'currency',
    currency: 'EUR',
    minimumFractionDigits: 2,
    maximumFractionDigits: 2,
  }).format(price).toString();
};

function getImageUrl(productImage: string|null = null): string {
  let _url = '../assets/FoodPhoto.png';
  if (productImage) {
    _url = '../assets/' + productImage;
  }

  return new URL(_url, import.meta.url).href;
}
</script>

<template>
  <div class="grid grid-cols-5 justify-center gap-3">
    <div class="" v-for="product in props.products" v-bind:key="product.id">
      <a href="#" class="flex flex-col">
        <div class="flex items-center flex-col w-full rounded-lg overflow-hidden relative">
          <!--            <span :style="{background: `${new URL('../assets/FoodPhoto.png', import.meta.url).href}`}" class="text-green-700 block h-[12rem] object-contain"></span>-->
          <img :src="getImageUrl(product.image)" class="text-green-700 w-full h-56 object-cover" :alt="product.name"/>
        </div>
        <div class="mt-4">
          <span class="font-semibold text-lg">
            {{ product.name}}
          </span>
        </div>
      </a>

      <p class="text-green-700 font-semibold mt-3">
        <span class="flex -ml-1.5">
          <IconMap />
          {{ product.location }}
        </span>
      </p>

      <p class="font-semibold mt-3">
        {{ formattedPrice(product.price) }}
<!--        €-->
      </p>

      <button type="button" class="bg-green-800 text-white py-3 w-full rounded-md mt-5 font-bold">
        Commander
      </button>
    </div>
  </div>
</template>

<style scoped>

</style>
