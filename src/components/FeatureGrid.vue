<script>
import FeatureCard from './FeatureCard.vue'

import { Mail, Shield, Zap } from 'lucide-vue-next'

export default {
  components: {
    FeatureCard
  },

  data() {
    return {
      features: [
        {
          icon: Mail,
          title: 'Email',
          description: 'Send emails easily'
        },
        {
          icon: Shield,
          title: 'Security',
          description: 'Secure platform'
        },
        {
          icon: Zap,
          title: 'Fast',
          description: 'Fast performance'
        }
      ]
    }
  }
}
</script>