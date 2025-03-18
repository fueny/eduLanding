<template>
  <section id="pricing" class="section bg-primary-50">
    <div class="container">
      <!-- Section Header -->
      <div class="text-center max-w-3xl mx-auto mb-16" data-aos="fade-up">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          Simple, Transparent <span class="gradient-text">Pricing</span>
        </h2>
        <p class="text-lg text-secondary-600">
          Choose the plan that fits your learning goals and budget. All plans include access to our community and basic support.
        </p>
      </div>
      
      <!-- Pricing Toggle -->
      <div class="flex justify-center mb-12" data-aos="fade-up">
        <div class="bg-white rounded-full p-1 inline-flex shadow-sm">
          <button 
            @click="billingCycle = 'monthly'"
            :class="[
              'px-6 py-2 rounded-full text-sm font-medium transition-all',
              billingCycle === 'monthly' 
                ? 'bg-primary-600 text-white shadow-sm' 
                : 'bg-transparent text-secondary-700 hover:text-primary-600'
            ]"
          >
            Monthly
          </button>
          <button 
            @click="billingCycle = 'annual'"
            :class="[
              'px-6 py-2 rounded-full text-sm font-medium transition-all',
              billingCycle === 'annual' 
                ? 'bg-primary-600 text-white shadow-sm' 
                : 'bg-transparent text-secondary-700 hover:text-primary-600'
            ]"
          >
            Annual <span class="text-xs text-primary-600 font-bold">Save 20%</span>
          </button>
        </div>
      </div>
      
      <!-- Pricing Cards -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <PricingCard 
          v-for="(plan, index) in plans" 
          :key="plan.id"
          :plan="plan"
          :is-popular="index === 1"
          :billing-cycle="billingCycle"
          :delay="index * 100"
        />
      </div>
      
      <!-- Enterprise -->
      <div class="mt-16 bg-white rounded-xl shadow-custom p-8 text-center" data-aos="fade-up">
        <h3 class="text-2xl font-bold mb-4">Enterprise Plan</h3>
        <p class="text-secondary-600 mb-6 max-w-2xl mx-auto">
          Need a custom solution for your organization? We offer tailored learning programs for teams and businesses of all sizes.
        </p>
        <a href="#contact" class="btn btn-secondary">
          Contact Sales
          <i class="bi bi-arrow-right ml-2"></i>
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import PricingCard from '../ui/PricingCard.vue'

export default {
  name: 'PricingSection',
  components: {
    PricingCard
  },
  data() {
    return {
      billingCycle: 'monthly',
      plans: [
        {
          id: 'basic',
          name: 'Basic',
          description: 'Perfect for individual learners getting started',
          monthlyPrice: 19.99,
          annualPrice: 191.90,
          features: [
            'Access to 50+ basic courses',
            'Basic course materials',
            'Course completion certificates',
            'Community access',
            '24/7 email support'
          ]
        },
        {
          id: 'pro',
          name: 'Professional',
          description: 'Ideal for dedicated learners seeking comprehensive education',
          monthlyPrice: 39.99,
          annualPrice: 383.90,
          features: [
            'Access to 200+ premium courses',
            'Advanced course materials',
            'Course completion certificates',
            'Priority community access',
            '24/7 email & chat support',
            'Downloadable resources',
            'Group study sessions'
          ]
        },
        {
          id: 'premium',
          name: 'Premium',
          description: 'For serious learners who want the complete experience',
          monthlyPrice: 79.99,
          annualPrice: 767.90,
          features: [
            'Access to all 300+ courses',
            'Premium course materials',
            'Accredited certificates',
            'VIP community access',
            '24/7 priority support',
            'Downloadable resources',
            '1-on-1 mentoring sessions',
            'Career coaching',
            'Job placement assistance'
          ]
        }
      ]
    }
  }
}
</script>
