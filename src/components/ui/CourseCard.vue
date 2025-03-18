<template>
  <div 
    class="card group overflow-hidden flex flex-col h-full" 
    data-aos="fade-up"
    :data-aos-delay="delay"
  >
    <!-- Course Image -->
    <div class="relative overflow-hidden">
      <img 
        :src="course.image || 'https://placehold.co/600x400/e2e8f0/1e293b?text=Course+Image'" 
        :alt="course.title"
        class="w-full h-48 object-cover transition-transform duration-500 group-hover:scale-110"
        crossorigin="anonymous"
      >
      <div class="absolute top-4 right-4 bg-primary-600 text-white text-xs font-bold px-2 py-1 rounded">
        {{ course.level }}
      </div>
    </div>
    
    <!-- Course Content -->
    <div class="p-6 flex-grow flex flex-col">
      <div class="mb-4">
        <span class="text-xs font-semibold text-primary-600 bg-primary-50 px-2 py-1 rounded">{{ course.category }}</span>
        <span class="text-xs font-semibold text-secondary-600 bg-secondary-100 px-2 py-1 rounded ml-2">
          <i class="bi bi-clock mr-1"></i>{{ course.duration }}
        </span>
      </div>
      
      <h3 class="text-xl font-bold mb-2 line-clamp-2">{{ course.title }}</h3>
      <p class="text-secondary-600 mb-4 line-clamp-3">{{ course.description }}</p>
      
      <!-- Instructor -->
      <div class="flex items-center mb-4 mt-auto">
        <img 
          :src="`https://placehold.co/100/4f46e5/ffffff?text=${course.instructor.charAt(0)}`" 
          :alt="course.instructor"
          class="w-8 h-8 rounded-full mr-2"
          crossorigin="anonymous"
        >
        <span class="text-sm text-secondary-700">{{ course.instructor }}</span>
      </div>
      
      <!-- Rating & Students -->
      <div class="flex justify-between items-center mb-4">
        <div class="flex items-center">
          <div class="flex mr-1">
            <i class="bi bi-star-fill text-yellow-400 text-sm"></i>
            <span class="ml-1 text-sm font-medium">{{ course.rating }}</span>
          </div>
          <span class="text-xs text-secondary-500">({{ course.reviews }})</span>
        </div>
        <div class="text-sm text-secondary-500">
          <i class="bi bi-people-fill mr-1"></i>{{ formatNumber(course.students) }} students
        </div>
      </div>
      
      <!-- Price & CTA -->
      <div class="flex justify-between items-center">
        <div>
          <span class="text-xl font-bold text-secondary-900">${{ course.price }}</span>
          <span class="text-sm text-secondary-500 line-through ml-2">${{ course.originalPrice }}</span>
        </div>
        <button class="btn btn-primary py-2 px-4">Enroll Now</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CourseCard',
  props: {
    course: {
      type: Object,
      required: true
    },
    delay: {
      type: Number,
      default: 0
    }
  },
  methods: {
    formatNumber(num) {
      if (num >= 1000) {
        return (num / 1000).toFixed(1) + 'k';
      }
      return num;
    }
  }
}
</script>
