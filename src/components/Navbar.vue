<template>
  <div>
    <nav class="fixed top-0 z-10 w-screen font-ubuntu flex flex-wrap bg-neutral-100 dark:bg-neutral-800 justify-between items-center py-4 px-8 sm:px-16 md:px-32 border-b border-neutral-400">
      <a @click="scrollTo('profile')" class="flex text-neutral-700 dark:text-neutral-100 text-xl font-extrabold line-through hover:underline hover:cursor-pointer">
        alaajili<p class="text-green-500">.me</p>
      </a>
      <div class="hidden md:flex">
        <ul class="flex space-x-8 font-bold hover:cursor-pointer text-neutral-400">
          <li @click="scrollTo('skills')" class="hover:text-neutral-700 hover:dark:text-neutral-100 hover:scale-110">
            <a >Skills</a>
          </li>
          <li @click="scrollTo('portfolio')" class="hover:text-neutral-700 hover:dark:text-neutral-100 hover:scale-110">
            <a>Portfolio</a>
          </li>
          <li @click="scrollTo('contact')" class="hover:text-neutral-700 hover:dark:text-neutral-100 hover:scale-110">
            <a>Contact</a>
          </li>
          <li>
            <button @click="toggleDarkMode" class="hover:scale-110">
              <i v-if="!darkMode" class="fa-solid fa-moon hover:text-neutral-700" title="Dark Mode"></i>
              <i v-else class="fa-solid fa-sun hover:text-neutral-100" title="Light Mode"></i>
            </button>
          </li>
        </ul>
      </div>
      <div class="md:hidden text-neutral-400">
        <button @click="isMenuOpen = !isMenuOpen">
          <svg v-if="!isMenuOpen" class="hover:text-neutral-700 hover:dark:text-neutral-100 w-8 h-8 transition-transform duration-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
          <svg v-else class="hover:text-neutral-700 hover:dark:text-neutral-100 w-8 h-8 transition-transform duration-500 transform rotate-90" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
          </svg>
        </button>
        <transition name="fade">
          <ul v-if="isMenuOpen" class="flex flex-col text-xl hover:cursor-pointer text-neutral-400">
            <li @click="scrollTo('skills')" class="hover:text-neutral-700 hover:dark:text-neutral-100">
              <a>Skills</a>
            </li>
            <li @click="scrollTo('portfolio')" class="hover:text-neutral-700 hover:dark:text-neutral-100">
              <a>Portfolio</a>
            </li>
            <li @click="scrollTo('contact')" class="hover:text-neutral-700 hover:dark:text-neutral-100">
              <a>Contact</a>
            </li>
            <li>
              <button @click="toggleDarkMode">
                <i v-if="!darkMode" class="fa-solid fa-moon hover:text-neutral-700" title="Dark Mode"></i>
                <i v-else class="fa-solid fa-sun hover:text-neutral-100" title="Light Mode"></i>
              </button>
            </li>
          </ul>
        </transition>
      </div>
    </nav>
  </div>
</template>

<script>
import { ref } from 'vue';
import Cookies from 'js-cookie'


export default {
  name: 'Navbar',
  setup() {
    const isMenuOpen = ref(false);
    return { isMenuOpen };
  },

  data() {
    return {
      darkMode: Cookies.get('darkMode') === 'true',
    }
  },

  methods: {
    toggleDarkMode() {
      this.darkMode = !this.darkMode;
      if (this.darkMode) {
        document.documentElement.classList.add('dark');
      } else {
        document.documentElement.classList.remove('dark');
      }
      Cookies.set('darkMode', this.darkMode);
    },

    scrollTo(sectionId) {
      this.$emit('scroll-to', sectionId);
    }
  },

  mounted() {
    if (this.darkMode) {
      document.documentElement.classList.add('dark');
    } else {
      document.documentElement.classList.remove('dark');
    }
  }

};
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
}
</style>
