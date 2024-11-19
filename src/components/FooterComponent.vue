<template>
  <div class="bg-indigo-950 pt-24 pb-16 px-24 text-white">
    <hr class="border-white/20 border-[0.025rem] rounded"/>

    <div class="flex justify-between my-8 pb-12">
      <div class="flex gap-16 columns-7">
        <div class="columns-4 flex flex-col font-semibold">
          <h3 class="font-bold">Pages</h3>
          <ul class="mt-3 flex flex-col gap-2">
            <li>
              <a href="#">
                À propos de nous
              </a>
            </li>
            <li>
              <a href="#">
                Équipe
              </a>
            </li>
            <li>
              <a href="#">
                Carrières
              </a>
            </li>
            <li>
              <a href="#">
                Blog
              </a>
            </li>
            <li>
              <a href="#">
              </a>
            </li>
          </ul>
        </div>
        <div class="columns-4 flex flex-col">
          <h3 class="font-bold">Contact</h3>
          <ul class="mt-3 flex flex-col gap-2">
            <li>
              <a href="#">
                Aide & support
              </a>
            </li>
            <li>
              <a href="#">
                Nos partenaires
              </a>
            </li>
          </ul>
        </div>
        <div class="columns-4 flex flex-col">
          <h3 class="font-bold">Mentions légales</h3>
          <ul class="mt-3 flex flex-col gap-2">
            <li>
              <a href="#">
                Conditions d'utilisation
              </a>
            </li>
            <li>
              <a href="#">
                Annulation & remboursement
              </a>
            </li>
            <li>
              <a href="#">
                Politique de confidentialité
              </a>
            </li>
            <li>
              <a href="#">
                Politique de cookies
              </a>
            </li>
          </ul>
        </div>
      </div>
      <div>
        <h3 class="font-bold uppercase text-white/50">
          Nous suivre
        </h3>
        <div class="flex gap-2 mt-1">
          <a href="#">
            <img
              class="w-8"
              src="https://img.icons8.com/fluent/48/000000/instagram-new.png" alt="Instagram"/>
          </a>
          <a href="#">
            <img
              class="w-8"
              src="https://img.icons8.com/fluent/48/000000/facebook-new.png" alt="Facebook"/>
          </a>
          <a href="#">
            <img
              class="w-8"
              src="https://img.icons8.com/fluent/48/000000/twitterx.png" alt="X"/>
          </a>
<!--          <a href="#">-->
<!--            <img src="https://img.icons8.com/fluent/48/000000/linkedin-filled.png" alt="LinkedIn"/>-->
<!--          </a>-->
        </div>
        <p class="text-white mt-8 font-semibold">
          Abonnez vous et recevez des offres exclusives.
        </p>
        <form action="" method="post" v-on:submit.prevent="">
          <div class="flex gap-2 mt-6">
            <div class="relative rounded">
              <IconLetter class="top-0 mt-2.5 left-2 absolute"/>
              <input type="text"
                     class="w-64 pl-10 rounded h-full text-white bg-white/50"
                     placeholder="Entrez votre email" name="email"
                     required/>
            </div>
            <button class="button-primary text-white bg-green-800/80 font-bold px-5 py-3 rounded">
              Souscrire
            </button>
          </div>
        </form>
      </div>
    </div>

    <hr class="border-white/20 border-[0.025rem] rounded mt-8"/>

    <p class="text-center pt-3">
      Tous droits réservés
      <span class="font-bold">
        &copy; Speed Food, {{ (new Date).getFullYear() }}
      </span>
    </p>
  </div>
</template>

<style scoped>

</style>

<script setup lang="ts">
import IconLetter from '@/components/icons/IconLetter.vue'
</script>
