<script setup>
import { projects } from '@/content/projects';
// const show = reactive(Object.fromEntries(projects.map((project) => [project.label, false])));
</script>

<template>
  <v-app id="inspire">
    <v-app-bar extended>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-app-bar-title>Application</v-app-bar-title>

      <v-spacer></v-spacer>

      <v-btn icon="mdi-dots-vertical">
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
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