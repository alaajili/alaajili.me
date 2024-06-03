<template>
  <div id="contact" class="p-4 font-ubuntu bg-neutral-100">
    <h1 class="font-ubuntu text-2xl font-extrabold text-center py-4">Contact.</h1>
    <hr class="w-1/2 border-b border-neutral-300 mx-auto">
    <form data-aos="fade-up" data-aos-once="true" data-aos-duration="1000" data-aos-delay="100" @submit.prevent="submitForm" class="w-2/3 md:w-1/2 mx-auto py-8">
      <div class="mb-4">
        <label for="name" class="block text-gray-700 text-sm font-bold mb-2">Name</label>
        <input type="text" id="name" v-model="name" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
      </div>
      <div class="mb-4">
        <label for="email" class="block text-gray-700 text-sm font-bold mb-2">Email</label>
        <input type="email" id="email" v-model="email" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline">
      </div>
      <div class="mb-4">
        <label for="message" class="block text-gray-700 text-sm font-bold mb-2">Message</label>
        <textarea id="message" v-model="message" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"></textarea>
      </div>
      <div class="bg-blue-400 hover:bg-blue-600 text-center rounded hover:cursor-pointer">
        <button type="submit" class="text-white  font-bold py-2">Send</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      message: ''
    }
  },
  methods: {
    submitForm() {
      // Handle form submission here
      console.log(this.name, this.email, this.message);
    }
  }
}
</script>

<style scoped>
</style>