<template>
  <div 
    :class="[
      'card p-6 border-2 transition-all relative',
      isPopular ? 'border-primary-500 transform md:-translate-y-4' : 'border-transparent hover:border-primary-200'
    ]"
    data-aos="fade-up"
    :data-aos-delay="delay"
  >
    <!-- Popular Badge -->
    <div v-if="isPopular" class="absolute top-0 right-0 bg-primary-500 text-white text-xs font-bold px-3 py-1 rounded-bl-lg rounded-tr-lg">
      Most Popular
    </div>
    
    <!-- Plan Name -->
    <h3 class="text-xl font-bold mb-2">{{ plan.name }}</h3>
    <p class="text-secondary-600 mb-6">{{ plan.description }}</p>
    
    <!-- Price -->
    <div class="mb-6">
      <div class="flex items-end">
        <span class="text-4xl font-bold text-secondary-900">
          ${{ billingCycle === 'monthly' ? plan.monthlyPrice.toFixed(2) : plan.annualPrice.toFixed(2) }}
        </span>
        <span class="text-secondary-500 ml-2">
          / {{ billingCycle === 'monthly' ? 'month' : 'year' }}
        </span>
      </div>
      <p v-if="billingCycle === 'annual'" class="text-sm text-primary-600 mt-1">
        Save ${{ (plan.monthlyPrice * 12 - plan.annualPrice).toFixed(2) }} annually
      </p>
    </div>
    
    <!-- Features -->
    <ul class="space-y-3 mb-8">
      <li v-for="(feature, index) in plan.features" :key="index" class="flex items-start">
        <i class="bi bi-check-circle-fill text-primary-500 mt-1 mr-2"></i>
        <span class="text-secondary-700">{{ feature }}</span>
      </li>
    </ul>
    
    <!-- CTA -->
    <button 
      :class="[
        'w-full btn',
        isPopular ? 'btn-primary' : 'btn-secondary'
      ]"
    >
      Get Started
    </button>
  </div>
</template>

<script>
export default {
  name: 'PricingCard',
  props: {
    plan: {
      type: Object,
      required: true
    },
    isPopular: {
      type: Boolean,
      default: false
    },
    billingCycle: {
      type: String,
      default: 'monthly'
    },
    delay: {
      type: Number,
      default: 0
    }
  }
}
</script>
