<template>
<div class="bg-white border-b border-emerald-pale">
  <div class="max-w-6xl mx-auto px-6 py-4 flex items-center justify-between">
   
   <!--icon-->
    <div class="flex items-center gap-2">
      <div class="w-8 h-8 bg-emerald rounded-lg flex items-center justify-between p-1.5 text-white font-black text-center">
        C
      </div>
      <span class="text-xl font-black text-emerald-dark tracking-tight"> CoreCRM</span>
    </div>

    <nav class="hidden md:flex items-center gap-8 text-sm font-semibold text-emerald ml-auto mr-8">
      <a href="#" class="hover:text-emerald-dark transition">Features</a>
      <a href="#" class="hover:text-emerald-dark  transition">Pricing</a>
      <a href="#" class="hover:text-emerald-dark  transition">About Us</a>
    </nav>

    <div class="flex items-center gap-3">
      
      <a href="#" target="_blank" class="bg-emerald text-white text-sm font-bold hover:bg-emerald-dark transition px-4 py-2.5 rounded-xl inline-flex items-center gap-1.5 shadow-sm" >
        <span>Get started</span>
      </a>
    </div>

  </div>
</div>

<section class="bg-emerald-light text-emerald-dark py-24 px-6 text-center">
    <div class="max-w-4xl mx-auto">

<p class="text-sm mb-4 text-emerald font-bold bg-emerald-pale inline-block px-3 py-1 rounded-full font-['Plus_Jakarta_Sans']">
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

      <div class="flex md:flex-row justify-center gap-4 max-w-xl mx-auto">

        <input
          v-model="email"
          type="email"
          placeholder="Enter your work email..."
          class="bg-white text-gray-500 px-5 py-4 rounded-xl w-full border-2 border-emerald-faint"
        />

        <button
          @click="submitEmail"
          class="bg-emerald text-white hover:bg-emerald-dark transition px-10 py-4 rounded-xl font-semibold whitespace-nowrap" >
          Start Free
        </button>
      </div>

      <p class="text-sm mt-5 text-gray-400"> Free 14-day trial. No credit card required</p>

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