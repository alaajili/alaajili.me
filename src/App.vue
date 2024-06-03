
<template>
  <div class="oveflow-auto">
    <Navbar @scroll-to="scrollTo"/>
    <Profile id="profile"/>
    <Skills id="skills"/>
    <Portfolio id="portfolio"/>
    <Contact id="contact"/>
    <Footer/>
  </div>
</template>

<script>
import Footer from './components/Footer.vue';
import Navbar from './components/Navbar.vue';
import Profile from './components/Profile.vue';
import Skills from './components/Skills.vue';
import Portfolio from './components/Portfolio.vue';
import Contact from './components/Contact.vue';

export default {
  components: {
    Navbar,
    Profile,
    Skills,
    Portfolio,
    Contact,
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
