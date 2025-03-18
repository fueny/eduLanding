<template>
  <div 
    class="p-8 text-center text-white border-r border-b border-primary-400/30 last:border-r-0 md:even:border-r-0 md:last:border-r md:nth-child-3:border-b-0 md:nth-child-4:border-b-0"
    data-aos="fade-up"
    :data-aos-delay="delay"
  >
    <i :class="[icon, 'text-4xl mb-4 text-primary-100']"></i>
    <div class="text-3xl md:text-4xl font-bold mb-2">{{ value }}</div>
    <div class="text-primary-100">{{ label }}</div>
  </div>
</template>

<script>
export default {
  name: 'StatCard',
  props: {
    icon: {
      type: String,
      required: true
    },
    value: {
      type: String,
      required: true
    },
    label: {
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
