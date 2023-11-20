<script setup>
import Reels from './reels.json'

const icons = [
  { name: 'mdi-instagram', link: 'https://www.instagram.com/__zaahaar__/' },
  { name: 'mdi-facebook', link: 'https://www.facebook.com/zakhar.bihun' },
  { name: 'mdi-mail', link: 'mailto:12zahar34@gmail.com' }
]
</script>

<template>
  <header class="header">
    <v-btn width="272px" height="54px" rounded="xl" class="reel-btn">Reels Compare</v-btn>
    <v-menu :close-on-content-click="false">
      <template v-slot:activator="{ props }">
        <v-btn v-bind="props" width="272px" height="54px" rounded="xl" class="reel-btn">
          Add reel
        </v-btn>
      </template>

      <!-- <v-list class=""> -->
      <v-list-item v-for="(item, i) in Reels" :key="i">
        <v-btn rounded="xl" class="reel-list-btn bg-none" variant="plain">{{ item.name }}</v-btn>
      </v-list-item>
      <!-- </v-list> -->
    </v-menu>
  </header>

  <main class="main"></main>

  <footer class="footer d-flex align-center justify-space-evenly px-4">
    <v-btn
      v-for="icon in icons"
      :key="icon"
      class="mx-4"
      :icon="icon.name"
      variant="plain"
      size="x-large"
      target="_blank"
      :href="icon.link"
    >
    </v-btn>
  </footer>
</template>

<style scoped>
.reel-btn {
  color: #272a30;
  text-align: center;
  text-shadow: 0px 4px 20px rgba(6, 65, 215, 0.4);
  font-family: sans-serif;
  font-size: 25px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  background: var(--Button, rgba(64, 210, 255, 0.76));
  box-shadow: 0px 0px 5px 5px rgb(38, 63, 129);
}
.reel-list-btn {
  color: #272a30;
  text-align: center;
  text-shadow: 0px 4px 20px rgba(6, 65, 215, 0.4);
  font-family: sans-serif;
  font-size: 15px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  background: var(--Button, rgba(97, 255, 134, 0.76));
}
</style>
