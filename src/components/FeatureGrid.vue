<template>
  <section class="py-24 px-6 bg-white">
    <div class="max-w-6xl mx-auto text-center">

     <p class="text-sm mb-4 text-emerald font-bold bg-emerald-light inline-block px-5 py-2 rounded-full">
        FEATURES
     </p>
      <h2 class="text-4xl text-emerald-dark font-bold mb-4">
        Everything you need to close deals
      </h2>

      <p class="text-emerald mb-10">
        Powerful tools, simple interface. Built for teams that move.
      </p>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-left">
      <FeatureCard
        v-for="(feature, index) in features" 
        :key="index"
        :icon="feature.icon"
        :title="feature.title"
        :description="feature.description"
      />
    </div>
  </section>
</template>

<script>
import FeatureCard from './FeatureCard.vue'

import { Mail, Shield, Zap, Users, ChartColumn } from 'lucide-vue-next'

export default {
  components: {
    FeatureCard
  },

  data() {
    return {
      features: [
        {
          icon: Users,
          title: 'Contact Management',
          description: 'Organize all yuour contacts in one place. Tags, notes, and activity history.'
        },  
        {
          icon: ChartColumn,
          title: 'Pipeline Tracking',
          description: 'Visual drag-and-drop pipeline. See eevry deal stage at a glaance.'
        },  
        {
          icon: Mail,
          title: 'Email integration',
          description: 'Sync your inbox. Auto-log emails and track opens and clicks.'
        },      
        {
          icon: Zap,
          title: 'Automations',
          description: 'Set up triggers and workflows. Automate follow-ups and'
        },
        {
          icon: Users,
          title: 'Team Collaboration',
          description: 'Share contacts, asssign tasks, and collaborate with your tam in real-time.'
        },
        {
          icon: Shield,
          title: 'Data Security',
          description: 'Enterprise-grade encryption. GDPR compliant. Your data stays yours.'
        },      
      ]
    }
  }
}
</script>