<template>
<section class="bg-emerald-light text-emerald-dark py-24 px-6 text-center">
    <div class="max-w-4xl mx-auto">

<p class="text-sm mb-4 text-emerald font-bold bg-emerald-pale inline-block px-3 py-1 rounded-md font-['Plus_Jakarta_Sans']">
  #1 CRM for Growing Teams
</p>

      <h1 class="text-5xl md:text-6xl font-black leading-tight text-[#064e3b] font-['Plus_Jakarta_Sans']">
        Manage Contacts. <br> Close Deals. 
      </h1> 
      <h1 class="text-5xl md:text-6xl font-black leading-tight mb-6 text-emerald font-['Plus_Jakarta_Sans']">
        Grow Revenue. 
      </h1> 

      <p class="text-lg text-emerald max-w-2xl mx-auto mb-10">
       Streamline your sales pipeline with smart contact <br> management, real-time analytics, and team <br> collaboration tools.
      </p>

      <div class="flex flex-col md:flex-row justify-center gap-4 max-w-xl mx-auto">

        <input
          v-model="email"
          type="email"
          placeholder="Enter your email"
          class="bg-white text-black px-5 py-4 rounded-xl w-full outline-none"
        />

        <button
          @click="submitEmail"
          class="bg-black hover:bg-gray-900 transition px-8 py-4 rounded-xl font-semibold"
        >
          Start Free
        </button>

      </div>

      <p
        v-if="submitted"
        class="mt-6 text-green-300 font-medium"
      >
        Thanks! Your email has been submitted.
      </p>

    </div>

  </section>
</template>

<script>
export default {
  name: 'HeroSection',

  data() {
    return {
      email: '',
      submitted: false,
    }
  },

  methods: {
    submitEmail() {
      if (this.email.trim() !== '') {
        this.submitted = true
        console.log('Submitted Email:', this.email)
      }
    },
  },
}
</script>