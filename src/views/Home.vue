<template>
  <div>
    <!-- Hero Section -->
    <HeroSection />
    
    <!-- Features Section -->
    <FeaturesSection />
    
    <!-- Courses Section -->
    <CoursesSection />
    
    <!-- Course Finder Section -->
    <CourseFinderSection />
    
    <!-- Testimonials Section -->
    <TestimonialsSection />
    
    <!-- Stats Section -->
    <StatsSection />
    
    <!-- Pricing Section -->
    <PricingSection />
    
    <!-- CTA Section -->
    <CtaSection />
    
    <!-- Contact Section -->
    <ContactSection />
  </div>
</template>

<script>
import HeroSection from '../components/sections/HeroSection.vue'
import FeaturesSection from '../components/sections/FeaturesSection.vue'
import CoursesSection from '../components/sections/CoursesSection.vue'
import CourseFinderSection from '../components/sections/CourseFinderSection.vue'
import TestimonialsSection from '../components/sections/TestimonialsSection.vue'
import StatsSection from '../components/sections/StatsSection.vue'
import PricingSection from '../components/sections/PricingSection.vue'
import CtaSection from '../components/sections/CtaSection.vue'
import ContactSection from '../components/sections/ContactSection.vue'

export default {
  name: 'Home',
  components: {
    HeroSection,
    FeaturesSection,
    CoursesSection,
    CourseFinderSection,
    TestimonialsSection,
    StatsSection,
    PricingSection,
    CtaSection,
    ContactSection
  }
}
</script>
