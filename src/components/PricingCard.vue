<template>
  <div class="relative group bg-emerald-surface text-emerald-dark rounded-2xl shadow-lg p-8 border-2 border-emerald-pale text-center hover:bg-emerald hover:text-white hover:scale-105 transition duration-300">
    <div v-if="plan.badge" class="absolute -top-4 left-1/2 -translate-x-1/2 bg-emerald-dark text-white text-sm font-semibold px-4 py-1 rounded-full shadow-md"    >
      {{ plan.badge }}
    </div>

    <h3 class="text-2xl font-bold mb-2">
      {{ plan.name }}
    </h3>

    <p class="text-emerald group-hover:text-white mb-6 ">
      {{ plan.description }}
    </p>

    <div class="text-5xl font-bold mb-8">
      ${{ finalPrice }}
      <span class="text-lg group-hover:text-white font-normal">
        /mo
      </span>
    </div>

<ul class="text-left space-y-3 mb-6 font-['Plus_Jakarta_Sans']">
  <li 
    v-for="(feature, index) in plan.features" 
    :key="index" 
    class="text-gray-500 group-hover:text-white text-sm flex items-center gap-2 transition-colors duration-300"
  >
    <span class="text-emerald group-hover:text-white font-bold">✓</span>
    <span>{{ feature }}</span>
  </li>
</ul>

    <button
      @click="$emit('choose-plan', plan.name)"
      class="text-emerald bg-white border-3 border-emerald hover:text-emerald px-6 py-3 rounded-xl w-full font-semibold"
    >
      Get Started
    </button>
  </div>
</template>

<script>
export default {
  name: 'PricingCard',

  props: {
    plan: Object,
    yearly: Boolean,
  },

  computed: {
    finalPrice() {
      return this.yearly ? this.plan.yearly : this.plan.monthly
    },
  },

  emits: ['choose-plan'],
}
</script>