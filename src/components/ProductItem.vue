<script setup lang="ts">
interface Props {
  productName: string,
  productImage?: string,
  promotionPercent: string|number,
  timeRemaining?: string|number,
}

const props = withDefaults(defineProps<Props>(), {
  timeRemaining: 0,
});

function getImageUrl(): string {
  let _url = '../assets/FoodPhoto.png';
  if (props.productImage) {
    _url = props.productImage;
  }

  return new URL(_url, import.meta.url).href;
}
</script>

<template>
  <div class="card relative rounded">
    <div class="relative">
      <img alt="Food" class="w-80 rounded-lg object-contain" :src="getImageUrl()" />
      <div class="flex gap-1 text-white fond-bold absolute bottom-0 left-0 bg-green-800 p-2 rounded-bl-2xl rounded-tr-2xl">
        <span class="text-6xl">
          {{ promotionPercent }}
        </span>
        <div class="text-xl mt-1">
          <p>%</p>
          <p class="font-medium">Off</p>
        </div>
      </div>
    </div>
    <div class="font-semibold mt-4">
      <h3 class="text-lg">
        {{ productName }}
      </h3>
      <p v-if="parseInt(props.timeRemaining.toString()) > 0"
         class="bg-green-900 w-fit px-3 py-2 text-white font-bold rounded-md mt-3">
        {{ props.timeRemaining }}
        <template v-if="parseInt(props.timeRemaining.toString()) > 1">
          jours restants
        </template>
        <template v-else>
          jour restant
        </template>
      </p>
    </div>
  </div>
</template>

<style scoped>

</style>
