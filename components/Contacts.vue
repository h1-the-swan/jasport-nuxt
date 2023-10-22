<template>
  <v-list v-for="item in contacts">
    <v-list-item-title>
      {{ item.title }}
      <a v-if="item.newTab" :href="item.url" target="_blank" rel="noopener noreferrer">
        {{ item.text }}
      </a>
      <a v-else :href="item.url">
        {{ item.text }}
      </a>
    </v-list-item-title>
  </v-list>
</template>

<script lang="ts" setup>
import contacts from '@/content/contact.json';
</script>

<style scoped>
.v-list {
  margin: 0;
  padding: 0;
}
</style>
