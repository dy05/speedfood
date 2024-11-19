<script setup lang="ts">
import IconStar from '@/components/icons/IconStar.vue'
import IconTimer from '@/components/icons/IconTimer.vue'
import IconDiscount from '@/components/icons/IconDiscount.vue'

interface Product {
  id: string|number,
  name: string,
  image: string|null,
  companyImage: string|null,
  description: string|null,
  review: string|number|null,
  discount: string|number|null,
  regularity: string|number|null,
  availability: number,
  price: number,
}

interface Props {
  products?: Array<Product>,
}

const props = withDefaults(defineProps<Props>(), {
  products: () => [
    {
      id: 1,
      name: 'Foodworld',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 3.88,
      availability: 0,
      review: 46,
      discount: 20,
      companyImage: 'FoodworldLogo.png',
      image: 'Foodworld.png',
      regularity: 'Fast',
    },
    {
      id: 2,
      name: 'Pizzahub',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 4.00,
      availability: 0,
      review: 40,
      discount: 15,
      companyImage: 'PizzahubLogo.png',
      image: 'Pizzahub.png',
      regularity: 'Fast',
    },
    {
      id: 3,
      name: 'Pancakes',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 1.99,
      availability: 1,
      regularity: '',
      review: 20,
      discount: 10,
      companyImage: 'DonutsHutLogo2.png',
      image: 'Pancakes.png',
    },
    {
      id: 4,
      name: 'Donuts Hut',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 3.00,
      availability: 1,
      review: 30,
      discount: 15,
      companyImage: 'DonutsHutLogo.png',
      image: 'DonutsHut.png',
      regularity: 'Fast',
    },
    {
      id: 5,
      name: 'Ruby Tuesday',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 13.40,
      availability: 1,
      review: 35,
      discount: 10,
      companyImage: 'RubyLogo.png',
      image: 'Ruby.png',
      regularity: 'Fast',
    },
    {
      id: 6,
      name: 'Kuakata Fried Chicken',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 13.40,
      availability: 1,
      review: 53,
      discount: 25,
      companyImage: 'KfcLogo.png',
      image: 'FriedChicken.png',
      regularity: 'Fast',
    },
    {
      id: 7,
      name: 'Red Square',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 13.40,
      availability: 1,
      review: 45,
      discount: 10,
      companyImage: 'RedLogo.png',
      image: 'RedSquare.png',
      regularity: 'Fast',
    },
    {
      id: 8,
      name: 'Taco Bell',
      description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
      price: 10,
      availability: 1,
      review: 35,
      discount: 10,
      companyImage: 'TacoLogo.png',
      image: 'TacoBell.png',
      regularity: 'Fast',
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
  <div class="grid grid-cols-4 justify-center gap-3 w-full">
    <div class="mb-12" v-for="product in props.products" v-bind:key="product.id">
      <a href="#" class="flex flex-col">
        <div class="relative flex items-center flex-col w-full rounded-lg overflow-hidden">
          <!--            <span :style="{background: `${new URL('../assets/FoodPhoto.png', import.meta.url).href}`}" class="text-green-700 block h-[12rem] object-contain"></span>-->
          <img :src="getImageUrl(product.image)" class="text-green-700 w-full h-64 object-cover" :alt="product.name"/>
          <div class="absolute bg-white/10 inset-0"></div>
          <div class="absolute z-10 top-4 left-4 flex gap-2 text-white font-bold">
            <span class="p-2 flex items-center justify-center bg-green-950 rounded-md" v-if="product.discount">
              <IconDiscount class="h-4"/>
              {{ product.discount }} % off
            </span>
            <span class="p-2 flex items-center justify-center bg-green-800 rounded-md" v-if="product.regularity">
              <IconTimer class="h-4"/>
              {{ product.regularity }}
            </span>
          </div>
        </div>
        <div class="mt-5 flex">
          <img :src="getImageUrl(product.companyImage)" class="text-green-700 w-12 h-12 object-cover" :alt="product.name"/>
          <div class="pl-4">
            <span class="font-semibold text-lg">
              {{ product.name}}
            </span>
            <span class="font-semibold text-green-800 text-lg flex gap-1 -ml-1.5 items-center -mt-1">
              <IconStar class="h-4"/>
              {{ product.review}}
            </span>
          </div>
        </div>
      </a>

<!--      <p class="font-semibold mt-3">-->
<!--        {{ formattedPrice(product.price) }}-->
<!--&lt;!&ndash;        €&ndash;&gt;-->
<!--      </p>-->

      <button type="button" class="bg-green-800 text-white py-1 px-2 w-fit rounded-2xl mt-5 font-bold" v-if="product.availability">
        Commander
      </button>
      <button type="button" class="bg-green-800 text-white py-1 px-2 w-fit rounded-2xl mt-5 font-bold" v-else>
        Réserver
      </button>
    </div>
  </div>
</template>

<style scoped>

</style>
