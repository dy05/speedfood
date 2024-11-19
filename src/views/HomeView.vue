<script setup lang="ts">
import ValidateCommand from '@/components/ValidateCommand.vue'
import ProductCard from '@/components/ProductCard.vue'
import IconChevronRight from '@/components/icons/IconChevronRight.vue'
import SearchProduct from '@/components/SearchProduct.vue'
import CardItem from '@/components/CardItem.vue'
</script>

<template>
  <div class="bg-white pt-20">
    <div class="flex gap-3 pb-8 px-24">
      <ProductCard promotion-percent="15"
                   product-image="../assets/FoodPhoto.png"
                   product-name="Greys Vage" time-remaining="4"/>
      <ProductCard promotion-percent="10"
                   product-image="../assets/Pasta.png"
                   product-name="Greys Vage" time-remaining="4"/>
      <ProductCard promotion-percent="25"
                   product-image="../assets/Fruits.png"
                   product-name="Greys Vage" time-remaining="4"/>
      <ProductCard promotion-percent="20"
                   product-image="../assets/Soup.png"
                   product-name="Greys Vage" time-remaining="4"/>
    </div>

    <div class="py-16 px-24 flex flex-col items-center mt-8 bg-green-600/30">
      <h2 class="text-green-700 font-bold text-4xl">
        Comment ca marche ?
      </h2>
      <div class="mt-12 flex">
        <div class="flex items-center flex-col w-72">
          <img src="@/assets/MapMarker.svg" class="text-green-700 h-24" alt="Map icon"/>
          <div>
            <span class="font-semibold">
            Choisir la localisation
            </span>
          </div>
          <p class="mt-3 text-center">
            Choisir l'adresse de livraison
          </p>
        </div>
        <div class="flex items-center flex-col w-72">
          <img src="@/assets/Command.svg" class="text-green-700 h-24" alt="Command icon"/>
          <div>
            <span class="font-semibold">
              Sélectionner la commande
            </span>
          </div>
          <p class="mt-3 text-center">
            Vous pouvez avoir plusieurs commandes
          </p>
        </div>
        <div class="flex items-center flex-col w-72">
          <img src="@/assets/Invoice.svg" alt="Invoice icon" class="h-24"/>
          <div>
            <span class="font-semibold">
              Payer en plusieurs tranches
            </span>
          </div>
          <p class="mt-3 text-center">
            Vous pouvez plusieurs méthodes de paiement
          </p>
        </div>
        <div class="flex items-center flex-col w-72">
          <img src="@/assets/Donut.svg" alt="Donut icon" class="h-24"/>
          <div>
            <span class="font-semibold">
            Manger équilibré
            </span>
          </div>
          <p class="mt-3 text-center">
            Manger des menus de qualité
          </p>
        </div>
      </div>
    </div>

    <div class="py-16 px-24 flex flex-col items-center mt-8">
      <h2 class="text-green-900 font-bold text-4xl">
        Menus populaires
      </h2>
      <div class="mt-5 flex justify-center">
      </div>
    </div>

    <div class="py-16 px-24 flex flex-col items-center mt-8">
      <h2 class="text-green-900 font-bold text-4xl">
        Nos restaurants
      </h2>
      <div class="mt-5 flex justify-center">
      </div>

      <a href="#" class="text-white font-bold px-8 py-3 bg-green-700 rounded-md shadow-lg shadow-green-900 flex items-center">
        Voir tout
        <IconChevronRight class="ml-1"/>
      </a>
    </div>

    <div class="py-16 px-24 flex flex-col mt-8 bg-green-600/30 text-white">
      <SearchProduct class=""/>
    </div>

    <div class="pt-16 px-24 flex flex-col mt-8 bg-download">
      <div class="card bg-white shadow-xl rounded-xl p-4 mx-32 gap-4 flex items-center justify-center text-green-800 font-bold text-lg">
        <div class="flex gap-2 items-center">
          <img src="@/assets/DiscountIcon.svg" alt="Discount"/>
          <span class="w-1/3">
            Réductions Journalières
          </span>
        </div>

        <div class="border-r h-24 mx-4"></div>

        <div class="flex gap-2 items-center">
          <img src="@/assets/MapIcon.svg" alt="Map"/>
          <span class="w-1/3">
            Live Tracking
          </span>
        </div>

        <div class="border-r h-24 mx-4"></div>

        <div class="flex gap-2 items-center">
          <img src="@/assets/TimerIcon.svg" alt="Timer"/>
          <span class="w-1/3">
            Livraison Rapide
          </span>
        </div>
      </div>
      <div class="flex justify-between mt-12">
        <div>
          <img src="@/assets/Phones.svg" alt="Phones App"/>
        </div>
        <div class="w-2/5 px-5 flex flex-col pb-32">
          <h3 class="text-4xl text-green-700 font-bold">
            Installer l'application
          </h3>
          <p>
            C’est plus facile de commander sur notre application en profitant de fonctionnalités diverses.
          </p>
          <div class="flex gap-2">
            <a href="#">
              <img src="@/assets/GooglePlayDownload.svg" class="w-24 h-16" alt="GooglePlay Button"/>
            </a>
            <a href="#">
              <img src="@/assets/AppStoreDownload.svg" class="w-24 h-16" alt="AppleStore Button"/>
            </a>
          </div>
        </div>
      </div>
    </div>

    <div class="py-16 px-24 flex flex-col mt-8">
      <CardItem photo-label="Sandwich" item-description="Profiter des meilleurs sandwiches aux meilleurs coûts."
                item-image="CroissantItem.png">
        Manger les meilleurs <span class="text-green-900">Sandwiches</span>
      </CardItem>
    </div>

    <div class="py-16 px-24 flex flex-col mt-8 bg-green-600/30">
      <CardItem photo-label="Chicken" item-description="Accompagner avec des compléments à votre choix."
                item-image="ChickenItem.png" align-text="right">
        Manger le meilleur <span class="text-green-900">Poulet Rôti ?</span>
      </CardItem>
    </div>

    <div class="py-16 px-24 flex flex-col mt-8">
      <CardItem photo-label="Pizza" item-description="Partager une pizza épicé avec vos proches."
                item-image="PizzaItem.png">
        <span class="pr-16">
          Voulez vous manger une délicieuse
        </span>
        <br/>
        <span class="text-green-900">Pizza ?</span>
      </CardItem>
    </div>

    <ValidateCommand/>
  </div>
</template>

<style scoped>
.bg-download {
  background-image: url('../assets/Download.svg');
  background-position: center;
  background-size: cover;
  width: 100%;
}
</style>
