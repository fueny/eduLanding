<template>
  <section id="features" class="section bg-gradient-to-b from-white to-primary-50">
    <div class="container">
      <!-- Section Header -->
      <div class="text-center max-w-3xl mx-auto mb-16" data-aos="fade-up">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Why Choose <span class="gradient-text">EduVista</span>
        </h2>
        <p class="text-lg text-secondary-600">
          Our platform offers a unique learning experience with features designed to maximize your educational journey.
        </p>
      </div>
      
      <!-- Features Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <FeatureCard 
          v-for="(feature, index) in features" 
          :key="index"
          :icon="feature.icon"
          :title="feature.title"
          :description="feature.description"
          :delay="index * 100"
        />
      </div>
    </div>
  </section>
</template>

<script>
import FeatureCard from '../ui/FeatureCard.vue'

export default {
  name: 'FeaturesSection',
  components: {
    FeatureCard
  },
  data() {
    return {
      features: [
        {
          icon: 'bi-person-video3',
          title: 'Expert Instructors',
          description: 'Learn from industry professionals with years of experience in their respective fields.'
        },
        {
          icon: 'bi-laptop',
          title: 'Interactive Learning',
          description: 'Engage with interactive content, quizzes, and hands-on projects to reinforce your learning.'
        },
        {
          icon: 'bi-clock-history',
          title: 'Flexible Schedule',
          description: 'Study at your own pace with lifetime access to course materials and on-demand video lectures.'
        },
        {
          icon: 'bi-award',
          title: 'Certification',
          description: 'Earn industry-recognized certificates upon completion to showcase your new skills.'
        },
        {
          icon: 'bi-people',
          title: 'Community Support',
          description: 'Join a community of learners and instructors for discussions, networking, and support.'
        },
        {
          icon: 'bi-graph-up',
          title: 'Progress Tracking',
          description: 'Monitor your learning progress with detailed analytics and personalized recommendations.'
        }
      ]
    }
  }
}
</script>
