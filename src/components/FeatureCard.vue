<template>
  <div class="group bg-emerald-surface rounded-2xl p-8 border-2 border-emerald-pale hover:-translate-y-2 transition duration-300">
    <div class="w-14 h-14 rounded-xl bg-emerald flex items-center justify-center mb-6 text-white">
      <component :is="icon" :size="30" />
    </div>

    <h3 class="text-2xl text-emerald-dark font-bold mb-4">
      {{ title }}
    </h3>

    <p class="text-emerald-medium leading-relaxed">
      {{ description }}
    </p>
  </div>
</template>

<script>
export default {
  name: 'FeatureCard',

  props: {
    icon: Object,
    title: String,
    description: String,
  },
}
</script>