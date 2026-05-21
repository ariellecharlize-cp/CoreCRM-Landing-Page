<template>
  <section class="py-24 px-6 bg-white">
    <div class="max-w-6xl mx-auto text-center">

      <h2 class="text-4xl font-bold mb-4">
        Simple, transparent pricing
      </h2>

      <p class="text-gray-500 mb-10">
        No hidden fess, Cancel anytime.
      </p>

      <button
        @click="toggleBilling"
        class="mb-12 bg-emerald-surface hover:bg-emerald hover:text-white px-6 py-3 rounded-full font-semibold"
      >
        {{ yearly ? 'Monthly' : 'Annual' }}
      </button>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

        <PricingCard
          v-for="(plan, index) in plans"
          :key="index"
          :plan="plan"
          :yearly="yearly"
          @choose-plan="selectPlan"
        />

      </div>

    </div>
  </section>
</template>

<script>
import PricingCard from './PricingCard.vue'

export default {
  name: 'PricingSection',

  components: {
    PricingCard,
  },

  data() {
    return {
      yearly: false,

      plans: [
        {
          name: 'Starter',
          description: 'For individuals',
          monthly: 9,
          yearly: 12,

          // Added features 
          features: [
            '250 contacts',
            'Basic pipeline',
            'Email support'
          ]
        },
        
        {
          name: 'Pro',
          description: 'For growing teams.',
          monthly: 29,
          yearly: 35,
          
          // Added features 
          features: [
            'Unlimited contacts',
            'Advanced pipeline',
            'Automations',
            'Priority support'
          ]
        },
        {
          name: 'Enterprise',
          description: 'For large orgs',
          monthly: 79,
          yearly: 109,

          // Added features 
          features: [
            'Everything in Pro',
            'Custom integrations',
            'Dedicated manager',
            'SSO & audit logs'
          ]
        },
      ],
    }
  },

  methods: {
    toggleBilling() {
      this.yearly = !this.yearly
    },

    selectPlan(planName) {
      alert(`You selected the ${planName} plan.`)
    },
  },
}
</script>