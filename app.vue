<script setup lang="ts">
import { projects } from '@/content/projects';
import thumbHeadshot from "~/assets/jasport_cropped2_thumb.jpg";
import logoOurResearch from "~/assets/ourresearch-logo-icon.png";
import Contacts from '~/components/Contacts.vue';
// const show = reactive(Object.fromEntries(projects.map((project) => [project.label, false])));
useHead({
  title: 'Jason Portenoy, PhD',
  meta: [
    { name: 'description', content: "Jason Portenoy's personal website." }
  ]
})
</script>

<style scoped>
#jasport {
  max-width: 1800px;
  margin: auto;
}
</style>

<template>
  <v-app id="jasport">

    <v-main>
      <v-container>
        <v-row>
          <v-col cols="8">
            <h1 class="text-h2 pa-4">Jason Portenoy, PhD</h1>
            <p class="text-h5">NYC-based data engineer/data scientist</p>
            <div class="py-4">
              <Contacts />
            </div>
          </v-col>
          <v-col>
            <v-img class="rounded-e-xl rounded-ts-xl rounded-bs-circle" :src="thumbHeadshot" max-width="300px" />
          </v-col>
        </v-row>
        <h3 class="text-h3 py-4">Projects</h3>
        <v-row>
          <v-col v-for="project in projects" :key="project.label" cols="12" sm="4">
            <v-card>
              <v-img :src="project.imgSrc" :alt="project.imgAltText" cover class="align-end" max-height="200px">
              </v-img>
              <v-card-title>
                {{ project.name }}
              </v-card-title>
              <v-card-text>
                <component :is="project.description" />
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>