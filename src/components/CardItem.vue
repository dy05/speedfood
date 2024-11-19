<script setup lang="ts">
import IconChevronRight from '@/components/icons/IconChevronRight.vue'

interface Props {
  photoLabel: string,
  itemImage: string,
  itemDescription: string,
  itemLink: string,
  alignText?: string|null,
}

const props = withDefaults(defineProps<Props>(), {
  itemLink: '#',
  alignText: 'left',
});

function getImageUrl(): string {
  let _url = '../assets/FoodPhoto.png';
  if (props.itemImage) {
    _url = '../assets/' + props.itemImage;
  }

  return new URL(_url, import.meta.url).href;
}
</script>

<template>
  <div class="card flex relative overflow-hidden rounded-md bg-white shadow-lg">
    <div v-if="alignText === 'left'" class="px-8 pt-16 pb-4 w-2/5 flex flex-col justify-between">
      <div>
        <div class="font-bold text-5xl">
          <slot></slot>
        </div>
        <p class="text-gray-500 text-md mt-4">{{ itemDescription }}</p>
      </div>

      <a :href="itemLink" class="bg-green-900 shadow-green-800 shadow-lg rounded-lg text-white text-center w-full flex items-center justify-center py-4 mt-12 mb-8">
        <span class="font-bold">
          Commander
        </span>
        <IconChevronRight class="ml-1"/>
      </a>
    </div>
    <div class="flex-1">
      <img :src="getImageUrl()" :alt="photoLabel" class="object-cover w-full h-full" />
    </div>
    <div v-if="alignText !== 'left'" class="px-8 pt-16 pb-4 w-2/5 flex flex-col justify-between">
      <div>
        <div class="font-bold text-5xl">
          <slot></slot>
        </div>
        <p class="text-gray-500 text-md mt-4">{{ itemDescription }}</p>
      </div>

      <a :href="itemLink" class="bg-green-900 shadow-green-800 shadow-lg rounded-lg text-white text-center w-full flex items-center justify-center py-4 mt-12 mb-8">
        <span class="font-bold">
          Commander
        </span>
        <IconChevronRight class="ml-1"/>
      </a>
    </div>
  </div>
</template>

<style scoped>

</style>
