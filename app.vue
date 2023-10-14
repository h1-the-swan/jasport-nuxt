<script setup>
import { projects } from '@/content/projects';
import thumbHeadshot from "~/assets/jasport_cropped2_thumb.jpg";
import logoOurResearch from "~/assets/ourresearch-logo-icon.png";
// const show = reactive(Object.fromEntries(projects.map((project) => [project.label, false])));
</script>

<style scoped>
.v-list * {
  margin: 0;
  padding: 0;
}
</style>

<template>
  <v-app id="jasport">

    <v-main>
      <v-container>
        <v-row>
          <v-col cols="8">
            <h1 class="text-h2 pa-4">Jason Portenoy, PhD</h1>
            <p class="text-h5">Senior Data Engineer, User Engagement and Outreach</p>
            <a href="https://ourresearch.org" target="_blank">
              <div class="d-flex">
                <v-avatar><v-img :src="logoOurResearch" /></v-avatar>
                <p class="text-h5 px-2">OurResearch</p>
              </div>
            </a>
          </v-col>
          <v-col>
            <v-img class="rounded-e-xl rounded-ts-xl rounded-bs-circle" :src="thumbHeadshot" max-width="300px" />
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12">
            <v-list>
              <v-list-item-title>
                <a href="mailto:jason.portenoy@gmail.com">
                  ✉ jason.portenoy@gmail.com
                </a>
              </v-list-item-title>
              <v-list-item-title>
                <a href="/JasonPortenoy_resume20230126.pdf" target="_blank" rel="noopener noreferrer">
                  📄 Resume (one-pager)
                </a>
              </v-list-item-title>
              <v-list-item-title>
                <a href="/JasonPortenoy_CV20221207.pdf" target="_blank" rel="noopener noreferrer">
                  📜 Full CV
                </a>
              </v-list-item-title>
              <v-list-item-title>
                GitHub:
                <a href="https://github.com/h1-the-swan" target="_blank" rel="noopener noreferrer">
                  h1-the-swan
                </a>
              </v-list-item-title>
              <v-list-item-title>
                <a href="https://stackoverflow.com/users/6794572/h1-the-swan" target="_blank" rel="noopener noreferrer">
                  Stack Overflow
                </a>
              </v-list-item-title>
              <v-list-item-title>
                Twitter:
                <a href="http://twitter.com/jportenoy" target="_blank" rel="noopener noreferrer">
                  @jportenoy
                </a>
              </v-list-item-title>
              <v-list-item-title>
                <a href="https://www.linkedin.com/in/jason-portenoy/" target="_blank" rel="noopener noreferrer">
                  LinkedIn
                </a>
              </v-list-item-title>
            </v-list>
          </v-col>

        </v-row>
        <h3 class="text-h3 py-4">Projects</h3>
        <v-row>
          <v-col v-for="project in projects" :key="project.label" cols="4">
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