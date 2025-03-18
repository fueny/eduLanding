<template>
  <section id="testimonials" class="section bg-primary-50">
    <div class="container">
      <!-- Section Header -->
      <div class="text-center max-w-3xl mx-auto mb-16" data-aos="fade-up">
        <h2 class="text-3xl md:text-4xl font-bold mb-4">
          What Our <span class="gradient-text">Students Say</span>
        </h2>
        <p class="text-lg text-secondary-600">
          Hear from our students about how EduVista has transformed their learning experience and career paths.
        </p>
      </div>
      
      <!-- Testimonials Grid -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <TestimonialCard 
          v-for="(testimonial, index) in testimonials" 
          :key="index"
          :testimonial="testimonial"
          :delay="index * 100"
        />
      </div>
      
      <!-- Video Testimonial -->
      <div class="mt-16 bg-white rounded-xl shadow-custom overflow-hidden" data-aos="fade-up">
        <div class="grid grid-cols-1 lg:grid-cols-2">
          <div class="p-8 flex flex-col justify-center">
            <h3 class="text-2xl font-bold mb-4">Success Story: From Beginner to Professional</h3>
            <p class="text-secondary-600 mb-6">
              "I started with zero coding knowledge, and within 6 months of taking courses on EduVista, I landed my dream job as a front-end developer at a tech startup. The structured curriculum and hands-on projects gave me the confidence and skills I needed to succeed."
            </p>
            <div class="flex items-center">
              <img 
                src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80" 
                alt="James Wilson" 
                class="w-12 h-12 rounded-full mr-4 object-cover"
                crossorigin="anonymous"
              >
              <div>
                <p class="font-bold text-secondary-900">James Wilson</p>
                <p class="text-sm text-secondary-500">Front-end Developer, TechNova</p>
              </div>
            </div>
          </div>
          <div class="relative h-80 lg:h-auto">
            <div class="absolute inset-0 flex items-center justify-center bg-primary-900/20">
              <button class="w-16 h-16 rounded-full bg-white/90 flex items-center justify-center shadow-lg hover:bg-white transition-colors">
                <i class="bi bi-play-fill text-primary-600 text-3xl"></i>
              </button>
            </div>
            <img 
              src="https://images.unsplash.com/photo-1515378791036-0648a3ef77b2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80" 
              alt="Student success story" 
              class="w-full h-full object-cover"
              crossorigin="anonymous"
            >
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import TestimonialCard from '../ui/TestimonialCard.vue'

export default {
  name: 'TestimonialsSection',
  components: {
    TestimonialCard
  },
  data() {
    return {
      testimonials: [
        {
          content: "The courses on EduVista are incredibly well-structured and engaging. I've learned more in 3 months than I did in a year of self-study.",
          name: "Emily Chen",
          role: "UX Designer",
          company: "Creative Solutions",
          image: "https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1770&q=80",
          rating: 5
        },
        {
          content: "As someone transitioning careers, EduVista provided me with the perfect roadmap to gain the skills I needed. The instructors are top-notch professionals who truly care about student success.",
          name: "Marcus Johnson",
          role: "Data Analyst",
          company: "DataTech Inc.",
          image: "https://images.unsplash.com/photo-1500648767791-00dcc994a43e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=774&q=80",
          rating: 5
        },
        {
          content: "The interactive projects and real-world applications make learning on EduVista both practical and enjoyable. I can immediately apply what I learn to my current job.",
          name: "Sophia Rodriguez",
          role: "Marketing Manager",
          company: "Global Brands",
          image: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=928&q=80",
          rating: 4
        },
        {
          content: "The community aspect of EduVista sets it apart from other platforms. Being able to connect with fellow learners and instructors has been invaluable for my growth.",
          name: "David Park",
          role: "Software Engineer",
          company: "InnovateTech",
          image: "https://images.unsplash.com/photo-1492562080023-ab3db95bfbce?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1748&q=80",
          rating: 5
        },
        {
          content: "I've taken courses on multiple platforms, but EduVista's curriculum is by far the most comprehensive and up-to-date with industry standards.",
          name: "Olivia Thompson",
          role: "Product Manager",
          company: "TechSolutions",
          image: "https://images.unsplash.com/photo-1544005313-94ddf0286df2?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=776&q=80",
          rating: 5
        },
        {
          content: "The flexibility of learning at my own pace while still having structured milestones helped me balance my studies with a full-time job. Highly recommend!",
          name: "Alex Rivera",
          role: "Business Analyst",
          company: "ConsultCorp",
          image: "https://images.unsplash.com/photo-1552058544-f2b08422138a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=798&q=80",
          rating: 4
        }
      ]
    }
  }
}
</script>
