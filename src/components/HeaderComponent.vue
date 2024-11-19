<script setup lang="ts">

import IconMap from '@/components/icons/IconMap.vue'
import NavBar from '@/components/NavBar.vue'
import IconBike from '@/components/icons/IconBike.vue'
import IconBag from '@/components/icons/IconBag.vue'
import IconSearch from '@/components/icons/IconSearch.vue'
</script>

<template>
  <header>
    <NavBar/>
    <div class="w-full flex bg-green-700 justify-between px-24 pt-32">
      <div class="w-7/12 flex flex-col pr-32">
        <h1 class="text-white text-7xl font-bold">
          Avez vous faim ?
        </h1>
        <p class="text-base mt-3">
          Trouvez en quelques clics des menus délicieux près de chez vous.
        </p>
        <div class="card bg-white w-full py-6 rounded-lg mt-8">
          <div class="flex gap-4 font-bold px-5">
            <button type="button" class="flex items-center gap-2 pl-2 pr-4 py-1 text-green-700 bg-green-500/20 rounded-md">
              <IconBike class="h-5"/>
              Livraison
            </button>
            <button type="button" class="flex items-center gap-2 pl-2 pr-4 py-1">
              <IconBag class="h-5"/>
              Récupération
            </button>
          </div>

          <div class="flex gap-3 mt-6 px-5 border-t border-green-700/20 pt-4 pb-4">
            <div class="flex flex-1">
              <form action="" method="post" class="flex w-full relative">
                <IconMap class="absolute top-0 mt-3 h-6 left-2 text-green-700"/>
                <input type="text"
                       class="h-full w-full pl-10 bg-gray-300/40 rounded text-xl"
                       placeholder="Entrez votre adresse"
                       name="adresse" />
              </form>
            </div>

            <div class="">
              <button type="submit" class="button-primary bg-gradient-to-r from-green-800 to-green-700 rounded-md px-8 py-3 flex items-center text-white font-bold">
                <IconSearch class="mr-2"/>
                Chercher un menu
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="flex relative mt-8">
        <img alt="Food" class="" src="@/assets/headerfood.svg" />
      </div>
    </div>
  </header>
</template>

<style scoped>

</style>
