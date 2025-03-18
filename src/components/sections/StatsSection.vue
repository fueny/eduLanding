<template>
  <section class="section bg-white">
    <div class="container">
      <div class="bg-gradient-to-r from-primary-700 to-primary-500 rounded-xl shadow-xl overflow-hidden" data-aos="fade-up">
        <div class="grid grid-cols-2 md:grid-cols-4">
          <StatCard 
            v-for="(stat, index) in stats" 
            :key="index"
            :icon="stat.icon"
            :value="stat.value"
            :label="stat.label"
            :delay="index * 100"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import StatCard from '../ui/StatCard.vue'

export default {
  name: 'StatsSection',
  components: {
    StatCard
  },
  data() {
    return {
      stats: [
        {
          icon: 'bi-people-fill',
          value: '50K+',
          label: 'Students'
        },
        {
          icon: 'bi-collection-play-fill',
          value: '300+',
          label: 'Courses'
        },
        {
          icon: 'bi-person-video3',
          value: '120+',
          label: 'Instructors'
        },
        {
          icon: 'bi-award-fill',
          value: '98%',
          label: 'Success Rate'
        }
      ]
    }
  }
}
</script>
