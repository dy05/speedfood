<script setup lang="ts">

import IconMap from '@/components/icons/IconMap.vue'
import IconSearch from '@/components/icons/IconSearch.vue'
import IconUser from '@/components/icons/IconUser.vue'

const props = withDefaults(defineProps<{
  addressLocation: string,
}>(), {
  addressLocation: '22 rue des Vignerons, Vincennes',
})

</script>

<template>
  <div class="bg-white shadow-lg flex justify-between px-24 py-4 items-center">
    <a href="#">
      <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="250" height="50" />
    </a>

    <div class="flex">
      <span>
        Livraison à
      </span>
      <span class="flex">
        <IconMap class="text-green-700 mt-0.5 h-4"/>
        <span>
          Adresse actuelle :&nbsp;
        </span>
      </span>

      <span class="font-bold">
        {{ props.addressLocation }}
      </span>
    </div>

    <div class="flex gap-4">
      <span class="flex items-center gap-2 font-semibold">
        <IconSearch class="text-green-700 mt-0.5 h-5"/>
        Chercher un menu
      </span>

      <button type="button" class="text-green-700 flex items-center gap-2 shadow-lg rounded px-4 py-2">
        <IconUser/>
        Se connecter
      </button>
    </div>
  </div>
</template>

<style scoped>

</style>
