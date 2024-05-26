
<template>
  <div class="oveflow-auto">
    <Navbar/>
    <Profile/>
    <Skills/>
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
  }
};

</script>

<style scoped>
</style>
