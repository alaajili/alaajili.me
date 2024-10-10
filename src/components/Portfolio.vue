<template>
  <div class="py-8 px-16 bg-neutral-50 dark:bg-neutral-700 text-neutral-700 dark:text-neutral-50">
    <h1 class="font-ubuntu text-2xl font-extrabold text-center py-4">Portfolio.</h1>
    <hr class="w-1/2 border-b border-neutral-300 mx-auto">
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-x-8 gap-y-4 pt-8">
      <div data-aos="fade-up" data-aos-once="true" data-aos-duration="1000" :data-aos-delay="project.id*100" class="rounded-lg overflow-hidden shadow-md bg-neutral-200 flex flex-col justify-between" v-for="project in projects" :key="project.id">
        <img class="w-full h-40 object-cover" :src="project.image" :alt="project.name">
        <div class="px-6 py-4">
          <div class="font-semibold text-xl mb-2 font-ubuntu text-center text-neutral-700">{{ project.name }}</div>
          <p class="text-gray-700 text-base text-center">{{ project.description }}</p>
        </div>
        <div class="flex flex-wrap justify-center mt-2 px-2">
            <span class="inline-block bg-green-400 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2" v-for="tech in project.techs" :key="tech">{{ tech }}</span>
        </div>
        <div class="px-6 pt-4 pb-2 flex justify-end">
          <a :href="project.link" target="_blank" class="inline-block text-neutral-500 hover:text-neutral-700 hover:underline font-ubuntu font-bold py-2 px-4 place-self-end">View Project</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { projects } from '../constants/projects.js';

export default {
  data() {
    return {
      projects
    };
  }
};
</script>
