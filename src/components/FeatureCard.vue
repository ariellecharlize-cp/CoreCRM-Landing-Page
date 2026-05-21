<template>
  <div class="bg-white rounded-2xl shadow-md p-8 hover:-translate-y-2 transition duration-300 border border-gray-100">
    <div class="w-14 h-14 rounded-xl bg-blue-100 flex items-center justify-center mb-6 text-blue-600">
      <component :is="icon" :size="30" />
    </div>

    <h3 class="text-2xl font-bold mb-4">
      {{ title }}
    </h3>

    <p class="text-gray-500 leading-relaxed">
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