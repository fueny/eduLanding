<template>
  <div 
    class="card p-6" 
    data-aos="fade-up"
    :data-aos-delay="delay"
  >
    <!-- Rating -->
    <div class="flex mb-4">
      <i v-for="i in 5" :key="i" :class="[
        'bi',
        i <= testimonial.rating ? 'bi-star-fill text-yellow-400' : 'bi-star text-gray-300'
      ]"></i>
    </div>
    
    <!-- Content -->
    <p class="text-secondary-600 mb-6">{{ testimonial.content }}</p>
    
    <!-- Author -->
    <div class="flex items-center">
      <img 
        :src="testimonial.image || 'https://placehold.co/100/4f46e5/ffffff?text=User'" 
        :alt="testimonial.name"
        class="w-12 h-12 rounded-full mr-4 object-cover"
        crossorigin="anonymous"
      >
      <div>
        <p class="font-bold text-secondary-900">{{ testimonial.name }}</p>
        <p class="text-sm text-secondary-500">{{ testimonial.role }}, {{ testimonial.company }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TestimonialCard',
  props: {
    testimonial: {
      type: Object,
      required: true
    },
    delay: {
      type: Number,
      default: 0
    }
  }
}
</script>
