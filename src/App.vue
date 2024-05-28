
<template>
  <div class="oveflow-auto">
    <Navbar @scroll-to="scrollTo"/>
    <div id="profile"><Profile/></div>
    <div id="skills"><Skills/></div>
    <Footer/>
  </div>
</template>

<script>
import Footer from './components/Footer.vue';
import Navbar from './components/Navbar.vue';
import Profile from './components/Profile.vue';
import Skills from './components/Skills.vue';

export default {
  components: {
    Navbar,
    Profile,
    Skills,
    Footer,
  },

  methods: {
    scrollTo(sectionId) {
      const section = document.getElementById(sectionId);
      if (section) {
        section.scrollIntoView({ behavior: 'smooth'});
      }
    }
  }

};

</script>

<style scoped>
</style>
