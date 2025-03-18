<template>
  <div 
    class="card p-6 hover:translate-y-[-8px]" 
    data-aos="fade-up"
    :data-aos-delay="delay"
  >
    <div class="bg-primary-100 w-14 h-14 rounded-lg flex items-center justify-center mb-5">
      <i :class="[icon, 'text-primary-600 text-2xl']"></i>
    </div>
    <h3 class="text-xl font-bold mb-3">{{ title }}</h3>
    <p class="text-secondary-600">{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: 'FeatureCard',
  props: {
    icon: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    },
    delay: {
      type: Number,
      default: 0
    }
  }
}
</script>
